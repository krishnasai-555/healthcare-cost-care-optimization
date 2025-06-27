# 🏥 Cost & Care Optimization in Healthcare

## 📊 Project Summary

This project uses synthetic Electronic Health Record (EHR) data to analyze real-world business problems in U.S. healthcare. It focuses on identifying chronic disease burden, ER overuse, care gaps, and patient safety issues — with the goal of helping healthcare payers and providers make smarter, value-based decisions.

---

## 🎯 Business Objective

> The U.S. healthcare system spends billions on avoidable care, inefficient treatment plans, and unmanaged chronic diseases.  
> This project uses synthetic patient records to identify cost drivers, care gaps, and preventable resource waste — helping healthcare payers and providers make smarter decisions.

---

## 🔍 Key Questions Answered

1. **Cost Analysis**
   - What are the costliest procedures and encounter types?
   - Are there high-cost patients that may be avoidable (e.g., repeat ER users)?

2. **Care Gaps**
   - Are diabetic patients getting regular HbA1c tests?
   - Are medications being prescribed to allergic patients?
   - Are patients with chronic care plans receiving related medications?

3. **Business Value**
   - How can these insights guide targeted interventions and cost reduction?

---

## 🧪 Dataset

- **Source:** [Synthea](https://synthea.mitre.org/downloads)
- **Type:** Public, privacy-safe synthetic EHR data
- **Format:** CSV files — patients.csv, conditions.csv, encounters.csv, observations.csv, allergies.csv, medications.csv, careplans.csv
- **Note:** This project only uses selected columns with **non-null, high-quality data**. Columns with excessive missingness are excluded, and no imputation or outlier treatment has been applied.

---

## 🛠️ Tools & Technologies

- Python (Pandas, NumPy)
- Seaborn, Matplotlib
- Exploratory Data Analysis (EDA), Domain-Driven Feature Engineering
- Healthcare subject matter expertise

---

### 🧪 Methodology
This is a goal-driven analysis — we only cleaned and transformed what we needed to answer specific questions.

Resource	Purpose	Key Actions
patients.csv	Demographics, age, income, insurance	Age calculation, selected columns, merged with chronic flags
conditions.csv	Identify chronic illnesses	Tagged using keyword-based chronic condition detection
encounters.csv	Analyze ER use & top costs	Segmented emergency visits, total cost by procedure, repeat user analysis
observations.csv	Lab tests (HbA1c)	Extracted only diabetes-related results
allergies.csv	Patient allergy info	Cross-checked against medications for safety issues
medications.csv	Medication history	Filtered for chronic meds, linked to allergies and careplans
careplans.csv	Chronic care plans	Mapped care plan patients to related medication activity

Merge Strategy: All datasets linked by PATIENT ID
Missing Data: No imputation; only essential nulls removed
EDA: Focused on medically relevant aggregations, not generic statistics

--
## 📈 Key Findings & Insights

### 1. 🧬 Chronic Condition Prevalence
- **75% of patients** have at least one chronic condition.
- Identifying chronic populations helps with proactive care and population health management.

### 2. 🚑 ER Cost Analysis
- Chronic patients incur **3× higher ER costs** ($12,334 vs. $3,866).
- Just **25 patients with ≥3 ER visits** accounted for **57.79%** of all ER costs.

### 3. 💰 Top Cost Drivers (by Procedure)
- Top 3 costliest procedures:
  - *Check-up encounters* — $3.7M
  - *Prenatal visits* — $2.9M
  - *Outpatient procedures* — $2.5M

### 4. 🧪 Preventive Care Gap (HbA1c Testing)
- Out of 18 diabetic patients, **94.4%** received an HbA1c test.
- **1 patient (5.6%)** missed testing — a measurable quality gap with population health implications.

### 5. 💊 Medication Safety: Allergy Conflicts
- **0 allergy-medication conflicts** were detected across 18 patients with documented allergies.
- This confirms safe prescribing practices in the dataset.

### 6. 📉 Medication Adherence to Care Plans
- Out of 77 patients with chronic care plans, only 58 received relevant chronic medications.
- **25% (19 patients)** didn’t receive recommended treatment — suggesting a care coordination or follow-up issue.


---

## 📂 File Structure

text
/healthcare-cost-care-optimization/
│
├── data/                            # resource csv data
├── Healthcare_Analysis.ipynb        # Full Jupyter notebook with all analysis 
├── README.md                        # Project documentation
