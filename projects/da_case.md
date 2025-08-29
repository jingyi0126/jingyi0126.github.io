---
layout: clean
title: "Master Thesis: Graph-Aware Next Event Prediction via GNN-Augmented Large Language Models"
permalink: /projects/da_case.html
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

**Time:** **October 2023 - December 2023**  
**Location:** **Munich, Germany**

# Superstore Dashboard Analytics Case Study

## Objective
Build a single-screen executive dashboard (Tableau Superstore dataset) enabling rapid insight into sales, profit, orders, customers, product structure, and geographic performance with time comparison (current period vs prior year).

## Data Scope
<div class="data-scope">
  <div class="ds-section">
    <span class="ds-label">Dataset</span>
    <span class="ds-value">Tableau Superstore sample</span>
  </div>
  <div class="ds-section">
    <span class="ds-label">Core Fields</span>
    <span class="ds-value">Order Date · Sales · Profit · Quantity · Category · Sub-Category · Segment · Region · State · Customer ID</span>
  </div>
  <div class="ds-section">
    <span class="ds-label">Aggregation</span>
    <span class="ds-value">Year (drill to month)</span>
  </div>

</div>

<style>
  .data-scope {border:1px solid #e3e6ea; background:#fafbfc; padding:14px 18px 10px; border-radius:8px; font-size:0.9em; margin:4px 0 20px;}
  .data-scope .ds-section {display:flex; gap:10px; margin:4px 0 6px; align-items:flex-start;}
  .data-scope .ds-label {min-width:120px; font-weight:600; color:#444; letter-spacing:0.3px;}
  .data-scope .ds-value {flex:1; line-height:1.45;}
  @media (max-width:640px){
    .data-scope .ds-section{flex-direction:column;}
    .data-scope .ds-label{min-width:auto;}
  }
</style>


![Superstore 概览](../images/Super.png)

## KPI Overview
<table class="kpi-table">
  <thead>
    <tr>
      <th>KPI</th>
      <th>Interpreted Meaning</th>
      <th>Strategic Signal (Example)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Sales</td>
      <td>Gross revenue from orders</td>
      <td>Growth health &amp; scale</td>
    </tr>
    <tr>
      <td>Profit</td>
      <td>Absolute profitability</td>
      <td>Margin sustainability</td>
    </tr>
    <tr>
      <td>Orders</td>
      <td>Transaction volume</td>
      <td>Demand intensity</td>
    </tr>
    <tr>
      <td>Customers</td>
      <td>Active unique buyers</td>
      <td>Acquisition / retention mix</td>
    </tr>
    <tr>
      <td>Profit Margin</td>
      <td>Profit / Sales</td>
      <td>Pricing &amp; discount discipline</td>
    </tr>
  </tbody>
</table>

<style>
  .kpi-table {width:100%; border-collapse:collapse; margin:8px 0 18px;}
  .kpi-table th, .kpi-table td {border:1px solid #ddd; padding:8px 10px; font-size:0.9em;}
  .kpi-table th {background:#f8f9fa; text-align:left; font-weight:600;}
  .kpi-table tbody tr:nth-child(even){background:#fcfcfd;}
  @media (max-width:640px){
    .kpi-table th, .kpi-table td {font-size:0.78em; padding:6px 6px;}
  }
</style>

Mini trend lines show momentum; YoY color cues (e.g., green up / red down) allow instant variance scanning.

## Geographic Insights
Choropleth combined with proportional bubbles at state level separates scale, indicated by bubble size, from efficiency, indicated by color and margin tooltip. States with high scale but low margin become pricing and logistics review targets; states with low scale but high margin become expansion candidates.



## Tableau Public (Live Dashboard)
Primary (interactive) version deployed on Tableau Public:

👉 Live Link: <a href="https://public.tableau.com/views/SuperstoreOverview_17553537670110/Super?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link" target="_blank" rel="noopener noreferrer">Open Interactive Dashboard</a>


## Summary
The dashboard consolidates multi-dimensional retail levers (product, customer, region, time) into an actionable surface. Early findings emphasize defending margin in select furniture sub-categories, scaling profitable tech segments, and closing regional efficiency gaps while reigniting customer acquisition. Subsequent iterations will add variance decomposition, retention cohorts, and predictive modules for proactive planning.

