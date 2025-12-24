# ML-project
# **Loan Approval Prediction & Credit Risk Analysis**

Retail Credit Risk Analytics | Portfolio
Project



---
## Business Problem
The bank receives thousands of personal loan applications every month. Each application contains demographic, financial, and credit-related information.  

---

## Dataset Overview
- Source: Historical loan application data
- Records: ~20,000 applications
- Target Variable: `LoanApproved`
  - 1 → Approved
  - 0 → Declined

Features include applicant demographics, income and debt metrics, credit history indicators, and loan request details.

---

## Approach & Methodology
1. Data quality checks and validation
2. Bank-style exploratory data analysis
3. Feature preprocessing using sklearn pipelines
4. Model development using:
   - K-Nearest Neighbors
   - Decision Tree
   - Random Forest
5. Model comparison using ROC-AUC and classification metrics
6. Interpretability through feature importance and partial dependence



---
**1. Executive Summary & Project Context**:

As part of the Retail Credit Risk team, our objective is to automate the initial phase of the personal loan underwriting process.

Currently, manual review of thousands of applications monthly creates a bottleneck. This project builds a predictive engine to:

Identify high-risk applicants early.

Streamline approvals for low-risk profiles.

Quantify the impact of financial behaviors (DTI, Credit Score, Defaults) on approval outcomes.

**2. Data Cleaning & Integrity Governance**
A rigorous cleaning process was followed to ensure the dataset meets bank-grade data quality standards.

**Data Cleaning Log:**
Missing Values: No missing values were found in the dataset.
**Duplicates**: No duplicate application records were detected, ensuring unique observations.

**Validation**:

**Data Cleaning Log:**

**Missing Values:** No missing values were found in the dataset.

**Duplicates**: No duplicate application records were detected, ensuring unique observations.

**Validation**:

**Age**: Verified all applicants are between 18 and 80 years old.

**Credit Score:** Validated that scores fall within the standard industry range.

**Financials**: Performed sanity checks on income vs. debt payments; records with zero income but high debt were scrutinized (none found).

**Feature Engineering:** The ApplicationDate was reviewed; however, as the focus is on profile-based risk rather than macroeconomic trends, it was excluded from the primary model to prevent overfitting to specific dates.

**3. Exploratory Data Analysis (EDA)**
The following visualizations highlight the key drivers behind current underwriting decisions.

**1. Loan Approval Landscapes**
The bank currently approves approximately 23.9% of all applicants, reflecting a conservative risk appetite aimed at minimizing defaults.

**Categorical Drivers of Approval**

The bank currently approves approximately 23.9% of all applicants, reflecting a conservative risk appetite aimed at minimizing defaults.

Employment,education, and Home Ownership show distinct patterns in approval probability, however insights from purpose does not show any sharp diffrence in catagories but we can conclude that

**Loans** for "Education" and "Home Improvement" show slightly higher approval rates compared to "Debt Consolidation," suggesting the bank favors "productive" debt..

**Employment Status**: Employed applicants have a significantly higher success rate compared to those with unstable income sources.

**Education Level:** Higher education levels (Master's/PhD) correlate with higher approval rates, likely due to their association with career stability.

**Home Ownership:** Applicants who own their homes or have mortgages are viewed more favorably than renters, signaling asset-backed stability.

**Risk Metrics:**
**Credit Score & DTI**
Credit Score: There is a sharp threshold effect where applicants below a certain score are almost universally declined.
There is a "safe zone" for credit scores above 650. Below 550, even high-income earners face significant rejection rates, highlighting the importance of credit history over raw income.

**Debt-To-Income (DTI):**

As DTI increases, approval probability drops exponentially.

**Prior Defaults are a Hard Stop:**

Any history of previous loan defaults reduces the probability of approval, indicating the bank's low tolerance for recidivism in credit behavior.

**Income Stability:**

Employment status is a prerequisite; "Unemployed" or "Self-Employed" statuses with high DTI are flagged immediately as high-risk segments.

**Loan Purpose Sensitivity:**

Loans for "Education" and "Home Improvement" show slightly higher approval rates compared to "Debt Consolidation," suggesting the bank favors "productive" debt.

---

## Key Insights
- Credit score is the strongest driver of loan approval decisions
- Prior defaults significantly reduce approval likelihood
- High debt-to-income ratios indicate elevated credit risk
- Stable employment and home ownership improve approval odds
- Income supports approval only after credit quality thresholds are met

---

## 4.Final Model Performance
- Selected Model: Random Forest
- Reason: Strong predictive power, stability, and lower false approvals
- Metric Used for Selection: ROC-AUC and confusion matrix analysis

---
