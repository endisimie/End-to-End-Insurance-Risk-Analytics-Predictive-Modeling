# End-to-End-Insurance-Risk-Analytics-Predictive-Modeling

This project focuses on analyzing an insurance dataset to uncover patterns in risk exposure, profitability, and claim behavior across various customer and vehicle segments. It includes data quality checks, statistical exploration, visual insights, and loss ratio computation.


## 📌 Objectives

- Explore insurance data for statistical trends and financial patterns.
- Calculate and visualize key metrics like **Loss Ratio (TotalClaims / TotalPremium)**.
- Detect outliers and missing data that may affect performance.
- Perform temporal and geographical trend analysis.
- Automate the workflow with **GitHub Actions (CI/CD)**.

---

## 🛠️ Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/insurance-risk-eda.git
cd insurance-risk-eda
 ## Create and Activate a Virtual Environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

## Install Dependencies
pip install -r requirements.txt

```
# Reproducible and Auditable Data Pipeline using DVC

This project demonstrates how to establish a **reproducible and auditable data pipeline** using **Data Version Control (DVC)**—a critical best practice in regulated industries such as **finance** and **insurance**.

DVC ensures data inputs are version-controlled just like code, supporting compliance, auditability, debugging, and reproducibility of all data science workflows.

---

## 📌 Objectives

- Ensure all data and models are fully versioned and auditable.
- Enable reproducibility of results for regulators, stakeholders, or debugging purposes.
- Provide a local remote storage setup to simulate data sharing and collaboration.

---

## 🔧 Requirements
```bash
- Python (>=3.6)
- Git
- [DVC](https://dvc.org/doc/install) (Data Version Control)

---

## 🚀 Setup Instructions

### 1. Install DVC

Install DVC via pip:


pip install dvc
 
 ```
## Statistical Validation of Risk Drivers – Hypothesis Testing
🔍 Objective
The goal of this task is to statistically validate or reject key hypotheses about risk drivers to inform a new segmentation strategy. We quantify risk using:
Claim Frequency: Proportion of policies with at least one claim.
Claim Severity: Average claim amount, given a claim occurred.
Margin: TotalPremium - TotalClaims

🧪 Null Hypotheses Tested

| Hypothesis ID | Null Hypothesis                                                  |
| ------------- | ---------------------------------------------------------------- |
| H₀₁           | There are no risk differences across provinces                   |
| H₀₂           | There are no risk differences between postal codes               |
| H₀₃           | There are no significant margin differences between postal codes |
| H₀₄           | There are no significant risk differences between Women and Men  |


✅ Methodology
1. Metric Selection
We selected the following KPIs for statistical testing:

Claim Frequency (binary metric)

Claim Severity (continuous metric)

Margin (continuous metric)

2. Data Preparation
Handled missing values by dropping rows with critical nulls.
Filtered subsets of data for specific hypotheses (e.g., only claims > 0 for severity).
Created binary indicators for claim occurrence and gender groups.

3. Segmentation for A/B Testing
For each hypothesis:
Group A (Control): Baseline group (e.g., province 1, male)
Group B (Test): Comparison group (e.g., province 2, female)

4. Statistical Tests Applied

| Data Type       | Test Used          | Purpose                           |
| --------------- | ------------------ | --------------------------------- |
| Binary outcome  | Chi-Square Test    | Compare claim frequency rates     |
| Continuous mean | Independent T-Test | Compare severity and margin means |

Results Summary

| Hypothesis | p-value  | Result             | Interpretation                                          |
| ---------- | -------- | ------------------ | ------------------------------------------------------- |
| H₀₁        | `< 0.05` | ❌ Rejected         | Significant risk differences across provinces           |
| H₀₂        | `< 0.05` | ❌ Rejected         | Risk significantly varies across postal codes           |
| H₀₃        | `< 0.05` | ❌ Rejected         | Margins differ significantly between postal code groups |
| H₀₄        | `> 0.05` | ✅ Failed to reject | No significant risk difference between Women and Men    |


🧩 Business Implications
Province & Postal Code show significant segmentation opportunities based on risk and margin.
Gender is not a statistically justified segmentation feature.
Margin insights can feed directly into pricing strategy refinement.
Results support a region-driven pricing model as a next step in modeling.

