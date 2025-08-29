---
layout: clean
title: "Purchase-to-Pay Process"
permalink: /projects/sap.html
---
<!-- 顶部导航栏，只保留主页按钮 -->
<div style="background:#222; color:#fff; padding:16px 24px; display:flex; align-items:center; font-family:sans-serif;">
  <a href="/about.html" style="color:#fff; font-size:1.3em; font-weight:bold; text-decoration:none;">&#8962; Homepage</a>
</div>

<style>
  .main-content {
    max-width: 900px;
    margin: 32px auto;
    background: #fff;
    padding: 32px 40px;
    border-radius: 12px;
    box-shadow: 0 4px 24px rgba(0,0,0,0.08);
    font-family: 'Segoe UI', 'Helvetica Neue', Arial, 'Liberation Sans', sans-serif;
    font-size: 1.08em;
    color: #222;
  }
</style>

<div class="main-content" markdown="1">

**Time:** October 2024 - February 2025  
**Location:** Munich, Germany

# Purchase-to-Pay Process

## Project Overview

This project enhances a real-world purchase-to-pay (P2P) process where a single Purchase Requisition (PR) manager previously approved or rejected all requests—creating workload concentration, delay risk, and error propagation. We build on an existing on‑premise solution (Purchase Requisition app + Error Handling app) rather than rewriting from scratch.



### Goals
- Increase resilience and speed in PR approval/rejection
- Provide ubiquitous access to PR & error handling
- Streamline requester notification (approval/rejection feedback loop)
- Establish a structured, faster error resolution path


## Semantic Data Model
<table style="width:100%; table-layout:fixed; margin:16px 0;">
  <tr>
  <td style="width:55%; vertical-align:middle; padding-right:22px;">
The semantic data model normalizes core procurement entities to minimize redundancy and support consistent joins in CDS views. A Purchase Requisition captures business context and links to one or more line Items holding valuation price, price unit, quantity, delivery date and plant reference. Master data tables provide stable dimensions: Company Code, Purchase Organization and Purchase Group, Plant, Material, Vendor, Issuer, and Error. Cardinalities enforce business rules enabling clean aggregation, status tracking, and event emission. This structured semantic layer underpins the services, reduces transformation logic in the application layer, and enables precise filtering without denormalized duplication.
    </td>
    <td style="width:45%; vertical-align:middle; text-align:center;">
      <img src="../images/p2pdata.png" alt="Semantic Entity-Relationship Model" style="max-width:100%; border:1px solid #ddd; border-radius:6px;">
      <div style="font-size:0.75em; color:#666; margin-top:6px;">ER diagram of core entities & relationships.</div>
    </td>
  </tr>
</table>

## System Architecture

<div style="text-align:center; margin:18px 0;">
  <!-- 架构图占位：将文件命名为 p2p_architecture.png 放到 images 目录 -->
  <img src="../images/softArch.png" alt="Purchase-to-Pay System Architecture" style="max-width:95%; border:1px solid #ddd; border-radius:6px;">
  <div style="font-size:0.8em; color:#555;">High-level component & event flow architecture.</div>
</div>

**BTP Layer**
- UI: Purchase Requisition – Fiori Elements app for creating/reviewing PRs.
- UI: Error Handling – Fiori Elements app for surfacing & resolving technical / business errors.
- Purchase Requisition Service – CAP / CDS model exposing OData endpoints for PR data & status transitions.
- Error Service – CAP / CDS model persisting error events, classification, resolution metadata.
- Databases – Two SAP HANA schemas (logical separation for PR vs. error domain).
- Event Mesh – Central event backbone (decouples S/4HANA producers and BTP consumers; triggers incremental data fetch).

**S/4HANA System**
- Data Generator (sandbox / simulation) – UI5 frontend to seed / mutate transactional data.
- CDS Models – Expose PR domain & error-relevant artifacts as OData.
- DB – Underlying transactional persistence.
- Event Publisher – Emits domain or technical events (e.g., PR_CREATED, ERROR_DETECTED) to Event Mesh.

## ABAP Backend: Data Model & Service Layer

<table style="width:100%; table-layout:fixed;">
  <tr>
    <td style="width:45%; vertical-align:middle; text-align:center;">
      <img src="../images/abap.png" alt="ABAP Repository Overview" style="max-width:100%; border:1px solid #ddd; border-radius:6px;">
      <div style="font-size:0.75em; color:#666; margin-top:6px;">ABAP repository objects</div>
    </td>
    <td style="width:55%; vertical-align:middle;">
The ABAP backend defines semantic building blocks and normalized tables for master data plus transactional purchase requisitions. CDS views wrap these tables with joins, annotations and filtered projections for Fiori / OData consumption. A behavior implementation class enforces valid state transitions, encapsulates validations and emits lightweight events picked up by the BTP layer. A small seed class generates sample data for testing and integration, while the design separates master and transactional schemas to simplify delta fetch, keep business rules centralized, and support clean extensibility with minimal refactoring.
    </td>
  </tr>
</table>

## UI Screens (Results)

<figure style="margin:14px 0 30px;">
  <img src="../images/error.png" alt="Error Handling UI list view" style="width:100%; border:1px solid #ddd; border-radius:6px;">
  <figcaption style="font-size:0.75em; margin-top:6px; color:#555; text-align:left;">(a) Error Handling app – filtered list with timestamp, description, suggested action, status & criticality badges.</figcaption>
</figure>

<figure style="margin:0 0 12px;">
  <img src="../images/in progres.png" alt="Purchase Requisition detail screen" style="width:100%; border:1px solid #ddd; border-radius:6px;">
  <figcaption style="font-size:0.75em; margin-top:6px; color:#555; text-align:left;">(b) Purchase Requisition detail – header metadata + line items with contextual approval actions.</figcaption>
</figure>

The error handling interface consolidates heterogeneous technical and business issues into a single sortable, severity‑annotated list with actionable suggestions, reducing triage time. The PR detail screen surfaces all approval‑critical attributes (org context, issuer, valuation, supplier recommendations, item breakdown) beside immediate Accept / Reject (and Faulty Accept for test scenarios) controls, shortening decision latency while preserving traceability.

</div>
