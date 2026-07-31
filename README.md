# MRI-Xplain: An Agentic AI Framework for Faithful Explanations in Brain Tumour MRI Classification

**Imane Belbachir**  
MSc Computer Science with Artificial Intelligence  
Abertay University | 2026

---

## Overview

MRI-Xplain is a multi-agent explainable AI framework for brain tumour 
MRI classification. Rather than applying a single fixed explanation 
method to every scan, the framework iteratively selects and validates 
the most spatially faithful XAI configuration for each individual image 
using a three-agent pipeline orchestrated via LangGraph.

The system integrates:
- **EfficientNet-B0** for brain tumour classification (99.80% accuracy)
- **Agent 1 — XAI Selector**: searches six gradient-based CAM 
  configurations across multiple EfficientNet-B0 layer depths
- **Agent 2 — LLM Vision Judge**: evaluates explanation plausibility 
  using LLaVA-NeXT (4-bit quantised) with a YOLO-IoU spatial override
- **Agent 3 — Clinical Reporting Agent**: generates structured natural 
  language summaries with human-in-the-loop review
- **YOLOv8n spatial proxy**: provides inference-time tumour localisation 
  without ground-truth masks

**Key result:** The adaptive pipeline achieves a +53.3% relative 
improvement in spatial faithfulness (GT-IoU) over a fixed Grad-CAM 
baseline (0.295 vs 0.192, Wilcoxon p < 0.001).

> **Research demonstration only. Outputs are not clinical diagnoses.**

---

## Repository Structure
