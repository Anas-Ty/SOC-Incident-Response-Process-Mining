# SOC Incident Response Optimization via Process Mining

## 🛡️ Overview
This project applies **Process Mining** techniques to audit and optimize the incident response workflows of a Security Operations Center (SOC) facing authentication threats (Brute Force, Credential Stuffing, and Compromised Accounts). 

Developed as part of the Master's program in Intelligent Cybersecurity and Emerging Technologies (CITECH), this project bridges the gap between data science and cybersecurity operations. It reconstructs the *actual* behavior of SOC analysts from raw system logs, compares it against the theoretical compliance baseline, and leverages Machine Learning to predict SLA breaches.

## 🚀 Key Features & Methodology
1. **Data Engineering & Event Log Formatting:** Extraction and cleaning of raw CSV data into the standard `XES` format required for process mining.
2. **Process Discovery:** Utilization of the **Inductive Miner** algorithm to generate the Directly-Follows Graph (DFG) and discover the true operational process models (happy paths vs. exception loops).
3. **Conformance Checking:** Token-based replay analysis to measure how closely the SOC reality adheres to the theoretical standard operating procedure (SOP), calculating Fitness (90.3%) and Precision (85.6%).
4. **Performance & Bottleneck Analysis:** Granular calculation of cycle times and transition delays to pinpoint critical operational waste (e.g., redundant triage loops taking 10+ minutes).
5. **Cybersecurity Threat Analysis:** Identification of critical compliance deviations, such as high-risk incidents being closed without proper IP investigation.
6. **Predictive Process Mining (AI/ML):** A Random Forest classification model trained on early incident attributes to predict 60-minute SLA breaches in real-time with 83% accuracy.

## 🛠️ Tech Stack & Tools
* **Language:** Python
* **Process Mining Library:** [PM4Py](https://pm4py.fit.fraunhofer.de/)
* **Data Manipulation:** Pandas, NumPy
* **Machine Learning:** Scikit-Learn (Random Forest)
* **Modeling:** BPMN 2.0, Petri Nets (.pnml)

## 📊 Key Findings
* **Operational Waste:** Analysts frequently fall into rework loops during the `SOC_Triage` phase, increasing average incident resolution time from 51 minutes to almost 60 minutes.
* **Security Gaps:** Several `High` risk incidents involving Credential Stuffing were improperly closed without triggering the mandatory `IP_Investigated` control.
* **Predictive Insights:** The nature of the attack (`BruteForce` vs. `CredentialStuffing`) is the strongest predictor of whether an incident will breach the resolution SLA.

## 📁 Repository Structure
* `data/` : Contains the raw CSV logs and the generated `.xes` event logs.
* `models/` : Contains the theoretical and discovered Petri Net models (`.pnml`).
* `notebooks/` : Google Colab / Jupyter Notebooks containing the full PM4Py pipeline and ML models.

---
*Project completed for the CITECH Master's program at Université Mohammed V - Faculté des Sciences de Rabat.*
