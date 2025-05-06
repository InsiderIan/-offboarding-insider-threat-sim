# -offboarding-insider-threat-sim
A simulation for insider threat triage and escalation during employee offboarding.
# Offboarding Insider Threat Simulation

This is a Python-based simulation that models the end-to-end workflow of an insider threat analyst investigating offboarding employees. The simulator includes realistic alert generation, behavioral analysis, risk scoring, escalation handling, and resolution paths.

The purpose is to reflect enterprise-grade workflows used in security teams, including collaboration with HR and Legal, while using synthetic data and modular Python scripts to simulate alert triage and investigative decisions.

---

## 🔁 Workflow Overview

1. **HR Integration:** Load a list of offboarding users from HR data (JSON or CSV format).
2. **Alert Generation:** Simulate synthetic security alerts during the 90-day lookback and 30-day post-offboarding windows, based on:
   - File transfers (SharePoint, OneDrive, Gmail)
   - Behavior anomalies (badge access, off-hours VPN, mobile app usage)
   - Suspicious keyword triggers (e.g. “resume,” “competitor,” “job offer”)
   - Mobile file sharing (e.g., O365 iOS app)
   - Mass deletions, excessive screenshots, unusual printing
3. **Alert Metadata Includes:**
   - Timestamp, user ID, device type
   - File details (name, extension, age, sensitivity)
   - Source system (SIEM, DLP, CASB, EDR, IAM)
4. **Triage & Escalation Logic:**
   - Determine false positives vs. true concerns
   - Apply weighted risk deltas based on role/project sensitivity
   - Simulate manager outreach, HR coordination, and employee interviews
   - Legal escalation path for IP or PII theft
5. **Resolution Phase:**
   - Simulate file deletion + employee compliance
   - Generate “Letter of Attestation”
   - Close the case and output a full case report
   - Conduct a simulated post-incident review


---


## 📁 Project Folder Structure

-offboarding-insider-threat-sim/
├── data/
│   ├── hr_offboarding_list.json
│   ├── alerts_generated.json
│   ├── sensitive_keywords.txt
├── reports/
│   └── case_001_report.json
├── scripts/
│   ├── alert_generator.py
│   ├── triage_engine.py
│   ├── escalation_flow.py
│   ├── generate_report.py
├── templates/
│   ├── manager_email.txt
│   ├── attestation_letter.txt
│   ├── investigation_report.md
└── requirements.txt

---

## 🧠 Logic & Design

- **Anchor Risk Score** is assigned based on:
  - Role type
  - Access to sensitive projects or intellectual property
  - Offboarding reason (e.g. termination vs. retirement)
- Each alert contributes a risk delta based on severity
- Simulated manager and employee responses reflect real-world workflows
- Legal review paths are triggered for PII, IP, or persistent noncompliance
- Reports can be generated for each case, including a final attestation if resolved

---

## 🛠️ Stack

- Python 3.9+
- JSON for user and alert data
- Markdown for templates and reports
- Optional: Streamlit or CLI dashboard for visualizing risk scores and case progress

---

## 💡 Purpose

This simulation is intended as a portfolio project or team training tool for insider threat practitioners. It mirrors real-world investigative logic, collaboration with HR and Legal, and post-incident reporting. All data is synthetic. No production systems or real user data are used.

---
