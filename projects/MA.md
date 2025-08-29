---
layout: default
title: "Master Thesis: Graph-Aware Next Event Prediction via GNN-Augmented Large Language Models"
permalink: /projects/MA.html
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

<div class="main-content">

**Time:** **June 2025 - present**  
**Location:** **Munich, Germany**

# Master Thesis: Graph-Aware Next Event Prediction via GNN-Augmented Large Language Models

## 1. Background

Process mining is a discipline that sits at the intersection of data science and business process management. It aims to discover, monitor, and improve real processes by extracting knowledge from event logs readily available in today's information systems.

In business processes, predicting the next activity is crucial for proactive decision-making, resource allocation, and process optimization. While people often expect process flows to be straightforward and linear, reality is much more complex. Unexpected events, deviations, and exceptions frequently occur, making accurate next event prediction both challenging and valuable. In practice, the idealized process—a simple, linear progression—is rarely observed. Instead, actual processes are full of twists, turns, and unpredictability, reflecting the gap between expectation and reality.

<!-- Insert a process mining overview illustration here -->
![Expectation vs. Reality](../images/ppm_comparision.png)

---

## 2. Project Overview: Next Event Prediction with LLM & GNN
This project aims to advance next event prediction in business processes by leveraging the complementary strengths of Large Language Models (LLMs) and Graph Neural Networks (GNNs). In complex business environments, event logs contain rich semantic information—such as activity names, descriptions, and contextual data—as well as intricate structural relationships between events.

<div style="text-align: center;">
  <img src="../images/MA1.png" alt="描述" style="max-width: 90%; border-radius: 8px;">
</div>

LLMs are employed to extract and understand the semantic content embedded in event logs, capturing nuanced meanings, dependencies, and contextual cues that traditional models may overlook. Meanwhile, GNNs are utilized to model the underlying process structure, learning from the graph-based relationships and dependencies among activities, cases, and resources.

By integrating LLMs and GNNs, the project seeks to build a unified predictive framework that can simultaneously reason about both semantic and structural aspects of business processes. This approach enables more accurate and robust predictions of the next activity, even in the presence of process deviations, exceptions, and complex event patterns. Ultimately, the goal is to provide actionable insights for process owners, supporting proactive decision-making and process optimization in dynamic, real-world scenarios.

---

## 3. Methodology
The proposed approach integrates both semantic and structural information from business process event logs to enhance next event prediction. The methodology consists of two main branches:
<table style="width:100%; table-layout:fixed;">
  <tr>
    <td style="width:50%; vertical-align:middle; text-align:center;"><img src="../images/MA2.png" alt="示意图" style="max-width:100%; border-radius:8px;"></td>
    <td style="width:50%; vertical-align:middle;">Event logs contain rich textual information, such as activity names, descriptions, and contextual attributes. In this branch, advanced language models are used to process and encode these textual elements, extracting meaningful semantic representations for each event. By leveraging the capabilities of large language models, the approach can capture subtle relationships, dependencies, and patterns within the process data that may be missed by traditional methods. This enables a deeper understanding of the context and intent behind each activity, supporting more informed and accurate predictions.</td>
  </tr>
</table>

<table style="width:100%; table-layout:fixed;">
  <tr>
    <td style="width:50%; vertical-align:middle;">Beyond textual content, business processes exhibit complex structural relationships, such as the order of activities, frequency of transitions, and time intervals between events. In this branch, the event log is transformed into a graph structure, where nodes represent activities and edges capture the connections, transition frequencies, and temporal dynamics. Graph neural networks are then applied to learn from these structural dependencies, enabling the model to reason about the overall process flow, detect recurring patterns, and account for variations in process execution. This structural perspective complements the semantic information, providing a holistic view of the process for next event prediction.</td>
    <td style="width:50%; vertical-align:middle; text-align:center;"><img src="../images/MA3.png" alt="示意图" style="max-width:100%; border-radius:8px;"></td>
  </tr>
</table>

The semantic and structural representations are then combined and fed into a unified predictive framework. This architecture allows the model to reason jointly about process semantics and structure, supporting more accurate and robust next event predictions.
---

## 4. Results & Discussion
- **Prediction Performance**
- **Case Studies**
- **Limitations and Future Work**

</div>
