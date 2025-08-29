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
Dataset: Tableau Superstore sample (Orders + Returns not used here). Core fields: Order Date, Sales, Profit, Quantity, Discount, Category, Sub-Category, Segment, Region, State, Customer ID. Aggregation: Monthly (with drill to day). Derived metrics: YoY delta, Profit Margin (Profit / Sales), Top-N contribution.

<div style="text-align:center; margin:24px 0;">
  <img src="../images/dashboard.png" alt="Superstore Overview Dashboard" style="width:100%; border:1px solid #ddd; border-radius:8px;">
  <div style="font-size:0.75em; color:#666; margin-top:6px;">Figure: Consolidated executive dashboard (expanded full-width view).</div>
</div>


## KPI Overview
| KPI | Interpreted Meaning | Strategic Signal (Example) |
|-----|---------------------|----------------------------|
| Sales | Gross revenue from orders | Growth health & scale |
| Profit | Absolute profitability | Margin sustainability |
| Orders | Transaction volume | Demand intensity |
| Customers | Active unique buyers | Acquisition / retention mix |
| Profit Margin | Profit / Sales | Pricing & discount discipline |

Mini trend lines show momentum; YoY color cues (e.g., green up / red down) allow instant variance scanning.

## Geographic Insights
Choropleth + proportional bubbles (State level) separate scale (bubble size) from efficiency (color / margin tooltip). High scale–low margin states become pricing / logistics review targets; low scale–high margin states become expansion candidates.



## Tableau Public (Live Dashboard)
Primary (interactive) version deployed on Tableau Public:

👉 Live Link: <a href="https://public.tableau.com/views/SuperstoreOverview_17553537670110/Super?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link" target="_blank" rel="noopener noreferrer">Open Interactive Dashboard</a>


## Summary
The dashboard consolidates multi-dimensional retail levers (product, customer, region, time) into an actionable surface. Early findings emphasize defending margin in select furniture sub-categories, scaling profitable tech segments, and closing regional efficiency gaps while reigniting customer acquisition. Subsequent iterations will add variance decomposition, retention cohorts, and predictive modules for proactive planning.

