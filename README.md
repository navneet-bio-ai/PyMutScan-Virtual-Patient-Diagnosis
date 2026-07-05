# PyMutScan-Virtual-Patient-Diagnosis
A Streamlit-powered web app for virtual patient diagnosis using mutation scanning and genomic data analysis.
# 🧬 PyMutScan — Virtual Patient Diagnosis

**Gene Panel Analysis · Cancer Staging · Risk Management · Clinical Recommendations**

PyMutScan Virtual Patient Diagnosis is a Streamlit-based, AI-assisted oncology risk assessment simulator. It takes a virtual patient's profile, presenting symptoms, and mutated gene panel (from simulated NGS/sequencing results) and generates a full computational oncology diagnostic workflow — from differential diagnosis and cancer staging to a risk management plan and a downloadable clinical report.

🔗 **Live Demo:** []

---

## ✨ Features

- **Patient Profile Management** — Capture Patient ID, age, and biological sex for each virtual patient case.
- **Clinical History Tracking** — Record symptom duration, family history of cancer, and smoking status.
- **Symptom Input Module** — Select from 16 presenting symptoms (e.g., unexplained weight loss, persistent fatigue, chronic cough, abnormal bleeding, nipple discharge, PSA elevation) across multiple organ systems.
- **Red Flag Modifiers** — Flag high-risk indicators: rapid symptom progression, multiple organ involvement, and prior malignancy history.
- **Gene Panel Selection (NGS-Style Input)** — Select detected pathogenic/likely-pathogenic variants from a 24-gene panel spanning tumor suppressors and oncogenes:
  - **Tumor Suppressors:** TP53, BRCA1, BRCA2, RB1, PTEN, APC, CDKN2A (p16), MLH1/MSH2 (Lynch), VHL
  - **Oncogenes:** EGFR, KRAS, HER2 (ERBB2), BRAF, PIK3CA, MYC, ALK, BCL2, FGFR2/FGFR3
  - Each gene is tagged with its functional category (e.g., DNA Repair, RTK, GTPase, Lipid Kinase) and includes an info tooltip.
  - **Selected Gene Summary** panel expands each chosen gene with a brief functional description.
- **Diagnosis & Staging Dashboard**
  - **Primary Diagnosis** card: cancer type, clinical stage, overall risk level, and 5-year survival estimate
  - **Cancer Staging Assessment**: stage (I–IV), metastatic status, survival rate, and clinical urgency, with a visual stage-severity gauge
  - **Differential Diagnosis — Cancer Probability Ranking**: relative risk scoring bar chart across candidate cancer types (e.g., Breast, Ovarian, Prostate, Brain, Leukemia)
  - **Cancer Formation Pathway**: mechanistic narrative of oncogenesis (driver mutations → uncontrolled proliferation → apoptosis evasion → angiogenesis → invasion → metastasis)
  - **Mutational Profile**: visual chip list of all screened genes, flagged pathogenic vs. wild-type/benign
- **Risk Management Plan** — Auto-generated, risk-tiered action plan covering:
  - Emergency multidisciplinary tumor board review
  - Immunotherapy / precision therapy eligibility (PD-L1, MSI-H, TMB)
  - Clinical trial enrollment screening
  - Palliative + curative dual-track care
  - Intensive biomarker monitoring (ctDNA, imaging cadence)
  - Holistic/supportive care coordination
  - Advance care planning
- **Recommended Screening Protocol** — Cancer-type-specific follow-up screening guidance (e.g., annual mammography + MRI, BRCA testing, clinical breast exam cadence for breast cancer).
- **Clinical Diagnostic Report Generator**
  - Auto-compiles a structured, timestamped report: Primary Diagnosis, Differential Diagnoses, Presenting Symptoms, Mutational Gene Profile, Cancer Staging Assessment, Risk Management Plan, and Recommended Next Steps
  - One-click **Download Clinical Report (.md)** for record-keeping or further review
- **Configurable Analysis Options** — Toggle visibility of signaling pathways, therapeutic targets, and screening protocols to tailor report depth.

---

## 🖥️ App Structure (Tabs)

| Tab | Purpose |
|---|---|
| 📋 **Symptom Input** | Select presenting symptoms and red flag modifiers |
| 🧬 **Gene Panel** | Select mutated genes from NGS/sequencing results |
| 🔍 **Diagnosis & Staging** | View computed diagnosis, staging, differential ranking, and mutational profile |
| 📊 **Clinical Report** | Generate and download the full diagnostic report |

---

## 🧪 How It Works

1. **Set up the patient** in the sidebar: Patient ID/Name, Age, Biological Sex.
2. **Enter clinical history**: symptom duration (months), family history of cancer, smoking status.
3. Go to **Symptom Input** and check all symptoms the patient currently presents with, plus any red flag modifiers (rapid progression, multi-organ involvement, prior malignancy).
4. Go to **Gene Panel** and select all genes reported as mutated/pathogenic from the (simulated) NGS panel.
5. Open **Diagnosis & Staging** to view:
   - The predicted primary diagnosis and stage
   - A relative-risk ranking across differential cancer types
   - The mechanistic cancer formation pathway
   - The full mutational profile
6. Review the **Risk Management Plan** and **Recommended Screening Protocol** generated for the assigned risk tier.
7. Navigate to **Clinical Report** to generate the full diagnostic write-up and download it as a `.md` file.

---

## 📄 Sample Output

For a 55-year-old male patient (VPD-2024-001) presenting with unexplained weight loss (6 months) and pathogenic TP53 + BRCA1 mutations, PyMutScan generated:

- **Primary Diagnosis:** Breast Cancer — Stage IV
- **Risk Level:** Critical | **5-Year Survival:** 10–25%
- **Top Differential Diagnoses:** Breast (100%), Ovarian (100%), Prostate (48%), Brain (33.3%), Leukemia (33.3%)
- **Recommended Next Steps:** Urgent oncology referral, full NGS panel (tumor + germline), PET-CT/MRI staging, tissue biopsy, multidisciplinary tumor board review, patient counseling.

---

## 🖥️ Tech Stack

- **Language:** Python
- **Web Framework:** Streamlit
- **Visualization:** Streamlit-native charts (horizontal bar charts for risk ranking, gauge visualization for stage severity)
- **Report Export:** Markdown (`.md`) report generation and download

---

## 📦 Installation

```bash
# Clone the repository
git clone https://github.com/<your-username>/PyMutScan-Virtual-Patient-Diagnosis.git
cd PyMutScan-Virtual-Patient-Diagnosis

# Create a virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate    # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run the app
streamlit run app.py
```

The app will be available at `http://localhost:8501`.

---

## 📁 Project Structure

```
PyMutScan-Virtual-Patient-Diagnosis/
│
├── app.py                     # Main Streamlit application
├── requirements.txt           # Python dependencies
├── README.md                  # Project documentation
└── ...                        # Supporting modules (staging logic, gene database, report generator, etc.)
```

---

## 🩺 Use Case

This module is designed to simulate a computational oncology risk-assessment pipeline for educational and research purposes:
- Demonstrate how symptom clusters, family history, and genomic mutation panels feed into a differential diagnosis
- Visualize how gene-level alterations (tumor suppressors vs. oncogenes) map to cancer risk pathways
- Illustrate a staged, risk-tiered clinical decision-support workflow (diagnosis → staging → management plan → screening)
- Practice generating structured, exportable clinical-style reports from computational analysis

---

## ⚠️ Disclaimer

This report is generated by an **AI-assisted bioinformatics tool for educational and research purposes only**. It does **NOT** constitute a clinical diagnosis. All findings must be validated by a qualified medical professional. Patient data used within the app is synthetic/virtual and entered solely for demonstration purposes.

---

## 👤 Author

**Navneet** © 2026
Built for Computational Oncology Research- interests in computational drug design and AI-driven diagnostics.

---

## 📄 License

[Add your preferred license here, e.g., MIT License]
