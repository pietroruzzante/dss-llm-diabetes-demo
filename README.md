# 💉 LLM-based Decision Support System for Type 1 Diabetes

### Master Thesis Project — University of Padua  
*Developed in collaboration with Prof. G. Cappon (Supervisor)*  
*Soon to be published as a paper*

---

## 🧠 Overview

This project presents a **Decision Support System (DSS)** for **Type 1 Diabetes (T1D)** management, built around a **local Large Language Model (LLM)** that analyzes real-time patient data and provides **personalized therapeutic recommendations**.

Unlike conventional clinical decision tools, this DSS leverages **digital twin simulations** — virtual patient replicas based on physiological models — to **evaluate and validate** therapeutic advice safely and objectively.

The system is designed for **integration into mobile or cloud-based healthcare platforms**, enabling scalable, AI-assisted diabetes care that is both **clinically grounded** and **technologically robust**.

---

## ⚙️ System Architecture

The DSS follows a modular architecture based on three main layers:

1. **Data Acquisition**  
   - Receives real-time patient data (e.g., CGM glucose, insulin delivery, meals, physical activity).  
   - Compatible with continuous glucose monitoring (CGM) devices following international standards (ISPAD/ADA).
   - An adaptive system is responsible for keeping memory of the past decisions made by the LLM for automatic CR/CF parameters adjusting

2. **Decision Layer (LLM Core)**

   - The DSS incorporates clinical reasoning based on:
      - **ISPAD 2022 Guidelines** — Insulin therapy, glycemic targets, and pediatric diabetes management.  
      - **ADA Standards of Care** — Self-management protocols and glucose goals.  
      - **Ambulatory Glucose Profile (AGP)** metrics — used to evaluate time-in-range (TIR), hypoglycemia, and variability.
     
   - Local LLM performs reasoning on patient context.  
   - Generates therapeutic suggestions (e.g., basal adjustment, bolus correction, carb ratio adaptation).  
   - Uses a domain-specific prompt structure and safety guardrails.
   
4. **Output**  
   - A second LLM summarizes first LLM's reasoning for providing a brief and clear explanation to the patient.
   - Guardrails layer is responsible for detecting anomalous or dnagerous answers from the LLM and correcting them

<img width="772" height="1000" alt="DSS_schema" src="https://github.com/user-attachments/assets/4e4b3132-bc0e-4df3-91c6-e3b8df9021cc" />


---

## Evaluation of performance
This project introduces a **closed-loop validation** using **digital twins**, allowing not only to *evaluate* AI decisions but also to *simulate their physiological impact*.
Performances have been evaluated on 480 glucose traces, within the *ReplayBG* framework, exploiting the concept of digital twin.

**Innovation highlights:**
- First DSS prototype to combine **LLMs** with **in-silico clinical validation**.  
- Enables safe experimentation and reinforcement of therapeutic reasoning.  
- Demonstrates **causal efficacy** of AI recommendations on virtual glucose traces.  
- Bridges the gap between **AI interpretability** and **clinical reliability**.

---


## 🧩 Technical Implementation

- **Framework:** Python, FastAPI, Docker  
- **Model:** Quantized local LLM (DeepSeek and Gemma family)
- **Digital Twin Simulation:** Based on the UVA/Padova T1D Simulator and ReplayBG
- **Evaluation Metrics:** ΔTIR and hypoglycemia events
- **Visualization:** Automated Ambulatory Glucose Profile (AGP) generation  

---

## 📈 Validation Through Digital Twins

To assess the clinical validity of LLM-generated decisions, a digital twin of each patient was simulated under different therapy scenarios:

| Scenario | Description | median TIR (Time in Range) |
|-----------|--------------|----------------------|
| Baseline | Standard clinical treatment | 63.93% |
| LLM Recommendation | Therapy adapted by DSS | 68.54% (+4.61%) |

> 🧪 Results show that the DSS consistently improved glucose control metrics across virtual cohorts, demonstrating **measurable physiological benefit**.

---

## 💡 Business & Integration Potential

This DSS represents a **turnkey innovation opportunity** for MedTech and digital health companies:

- 🩺 **Clinical Reliability** — built on validated ISPAD/ADA guidelines.  
- 📱 **Integration-Ready** — deployable as a backend API for mobile apps or wearable systems.  
- 🔒 **Privacy by Design** — runs locally, without cloud dependency.  
- ⚡ **Scalable Evaluation** — supports rapid testing of AI strategies through digital twin simulation.  
- 🤖 **Explainable AI** — LLM outputs are interpretable, auditable, and medically grounded.  

Potential use cases:
- Digital coaching and insulin dosing assistants  
- Automated therapy review tools for clinicians  
- Adaptive learning systems for diabetes management platforms  

---

## 🧭 Impact and Vision

This work lays the foundation for a new generation of **safe, data-driven decision systems** in diabetes care — combining **AI reasoning** with **physiological modeling** to create truly intelligent and reliable tools for clinicians and patients.

> *“A decision support system that doesn’t just suggest — it proves.”*

---

## 👥 Authors & Credits

**Author:** Pietro Ruzzante
**Supervisor:** Prof. Giacomo Cappon  
**Co-Supervisor:** Dott. Luca Cossu
**University:** University of Padua, Department of Information Engineering  
**Thesis:** “Development of a LLM-based Decision Support System for Type 1 Diabetes”

---

## 📚 References

- ISPAD Clinical Practice Consensus Guidelines 2022: *Glycemic targets, insulin therapy, and diabetes technology*.  
- ADA (2023). *Type 1 Diabetes Self-Care Manual*.  
- Czupryniak et al., 2022. *Ambulatory Glucose Profile (AGP) in Daily Care of Patients with Diabetes*.  
- UVA/Padova Type 1 Diabetes Simulator, FDA-accepted in-silico trial platform.  

---



