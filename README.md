# Simulating Annotator Disagreement with LLM Persona Prompting

This repository contains the code, datasets, and experimental results for the Master's thesis titled **"Simulating Annotator Disagreement with LLM Persona Prompting"** submitted to the **University of St. Gallen (HSG)**.

## 📝 Overview

This research investigates the capability of Large Language Models (LLMs) to simulate human annotator disagreement through **Persona Prompting**. The project focuses on whether models can move beyond surface-level stylistic changes to produce semantically consistent argumentative texts that align with specific philosophical ideologies.

### Key Research Questions
* **Fidelity:** To what extent can LLMs simulate distinct personas at lexical and semantic levels?
* **Granularity:** How does the prompt context (Claim, Premise, Argument) affect persona adherence?
* **Consistency:** Is persona sensitivity consistent across different architectures (GLM vs. Llama-4)?
* **Reasoning Stability:** How does the model's reasoning stability change when simulating logically contradictory personas?

## 🛠 Technical Stack

### Models Evaluated
1. **GLM-3-Turbo**: A high-alignment commercial model used to test if persona prompts can override safety constraints.
2. **LLaMA-4-Maverick (17B Active)**: A MoE architecture with 128 experts, specialized for deep task performance.
3. **LLaMA-4-Scout (17B Active)**: A MoE architecture with 16 experts, optimized for long-context reasoning.

### Philosophical Personas
To minimize demographic bias, four normative reasoning frameworks were selected:
* **Rawlsian Philosopher**: Prioritizing fairness, justice, and the interests of the least advantaged.
* **Libertarian Economist**: Emphasizing negative liberty, self-ownership, and property rights.
* **Utilitarian Ethicist**: Aiming for the maximization of aggregate social utility.
* **Conservative Political Theorist**: Valuing tradition, social order, and institutional continuity.

## 📊 Evaluation Metrics
* **Stance Flip Rate (SFR)**: Measures how much the model deviates from its default neutral stance.
* **Semantic Drift**: Calculated using cosine distance in embedding space via `all-MiniLM-L6-v2`.
* **Lexical Distinctiveness**: TF-IDF based keyword extraction and Jaccard similarity analysis.
* **LLM-as-a-Judge**: Logic contradiction scoring (1-10) using Llama-3-70B.

## 🚀 Repository Structure
```text
├── datasets/             # Data based on iDebate with 30 argumentative topics
├── glm-3-turbo/          # Zero-shot and One-shot experiment scripts for GLM
├── llama-4-maverick/     # Experimental runs for the Maverick variant
├── llama-4-scout/        # Experimental runs for the Scout variant
└── analysis/             # Python scripts for visualization and statistical testing
