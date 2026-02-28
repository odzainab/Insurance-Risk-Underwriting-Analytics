# Insurance Risk & Underwriting Analytics

_Analysis of high-risk policyholders, claims, premiums, and underwriting effectiveness for the DataBuzz February Challenge._

---

## Quick Look

- **Dataset:** Insurance policies, claims, health indicators, driving behavior, income bands, and regional data  
- **Goal:** Identify high-risk policyholders, evaluate underwriting effectiveness, and assess pricing adequacy  
- **Tools Used:** Power Query, Power BI (DAX, data visualization)    
- **Total Policies Analyzed:** 50,000  
- **Total Premiums:** $3.67 billion  
- **Overall Loss Ratio:** 174.59%
- **Full Analysis & Storytelling:** [Read on Medium](https://medium.com/@odzainab1/risk-assessment-and-pricing-strategies-in-insurance-portfolios-identifying-high-risk-policyholders-f737a1dadf17?postPublishedType=repub)  
  

---

## Introduction

This dataset from the **DataBuzz February Challenge** covers a wide range of insurance-related data, including:

- Policyholder demographics  
- Risk scores and risk categories  
- Premiums and claims history  
- Health indicators and driving behavior  
- Income bands and regional segmentation  

It provides a complete view of the insurance lifecycle, from **policy issuance** to **risk assessment, claims, and loss evaluation**.

---

## Business Use Case

The analysis aims to help the insurance provider:

1. **Identify High-Risk Policyholders:** Determine which customers pose higher risks.  
2. **Evaluate Underwriting Effectiveness:** Ensure premiums are aligned with risk levels.  
3. **Assess Pricing Adequacy:** Compare premiums with claims for proper pricing.  
4. **Support Data-Driven Decisions:** Optimize risk management, pricing strategies, and underwriting.

---

## Analysis Areas

- **Risk Score Distribution:** Variation across age groups, income bands, and regions.  
- **High-Risk vs Other-Risk Policyholders:** Impact on overall portfolio.  
- **Claims Frequency & Severity:** Effect on loss ratios.  
- **Health & Driving Behavior:** Influence on insurance risk.  
- **Regional Risk Analysis:** Identification of high-risk concentrations.  
- **Pricing Adequacy:** Premium vs claims evaluation.  
- **Customer Risk Profiles:** Individualized risk segmentation.

---

## Tools Used

- **Power Query:** Data cleaning and preparation  
- **Power BI:** Data modeling, metrics, and interactive visualizations  

---

## Key Dataset Contents

### 1. DIM_CUSTOMERS (Customer Dimension)
- **CustomerID:** Unique customer identifier  
- **Age, Gender, Region, IncomeBand:** Demographics and classification  

### 2. DIM_HEALTH (Health Dimension)
- **CustomerID:** Links to DIM_CUSTOMERS  
- **BMI, Smoker, ChronicCondition:** Health indicators  

### 3. DIM_DRIVING (Driving Behavior Dimension)
- **CustomerID:** Links to DIM_CUSTOMERS  
- **DrivingExperienceYears, AccidentsLast5Years, TrafficViolations:** Driving metrics  

### 4. FACT_RISK_PREMIUM (Fact Table)
- **PolicyID, CustomerID**  
- **ClaimsCount, ClaimAmount, RiskScore, RiskCategory**  
- **AnnualPremium, Region, IncomeBand**  

---

## Methodology: Data Cleaning & Preparation

**Fact_Risk_Premium Table Transformations:**

1. **Change Data Types:**  
   - `PolicyID, CustomerID, ClaimsCount, ClaimAmount, RiskScore, AnnualPremium` → Integer  
   - `RiskCategory, Region, IncomeBand` → Text  

2. **Trim Text:** Clean extra spaces in `RiskCategory`.  

3. **Duplicate Column:** Create `RiskCategoryLogic` for grouped classification.  

4. **Replace Values:** “Medium Risk” and “Low Risk” → “Other Risk”.  

**Data Quality Checks:**

- No duplicates in dimension tables  
- No missing values in critical analytical fields  
- Validated relationships between fact and dimension tables  

---

## Data Visualization
<img width="1400" height="757" alt="Screenshot 2026-03-01 020414" src="https://github.com/user-attachments/assets/ba53e9e3-0b36-42b8-b824-60c88f420e87" />
<img width="1369" height="757" alt="Screenshot 2026-03-01 020939" src="https://github.com/user-attachments/assets/e9cc32ae-d214-4a2e-a014-bfe5a9a6fbbb" />
<img width="1368" height="756" alt="Screenshot 2026-03-01 021654" src="https://github.com/user-attachments/assets/6e25b8de-82f8-4300-ba12-369812ad2792" />
<img width="936" height="752" alt="Screenshot 2026-03-01 031148" src="https://github.com/user-attachments/assets/403d20e0-34e7-4cee-968f-4999e7cd677c" />


**Interactive dashboard visualizations include:**  

- Overview of total policies, premiums, and high-risk segments  
- Claims severity and frequency breakdown  
- Risk score distribution by income, age, and driving experience  
- Regional drill-downs for targeted insights  



---

## Key Insights

1. **High-Risk Concentration:** 52.08% of policies categorized as high-risk; total risk score ~2 million.  
2. **Income Band Analysis:** Medium-income group carries highest average risk (45.76), followed by low-income (42.02) and high-income (35.10).  
3. **Age Band Risk:** Age 61–70 has the highest high-risk policies (0.41M). Age 18–20 has the least (0.03M).  
4. **Regional Loss Ratios:** West region highest (312.28%), East lowest (57.22%).  
5. **Gender Insights:** West region shows female-heavy high-risk policies.  
6. **Driving Experience:** Amateur drivers (4–7 years) highest risk score (41.37), veterans (21+ years) lowest (40.89).  
7. **Premium vs Claims:** High-risk policies generate $6.1B in premiums vs $0.7B in claims, yet loss ratios remain high in certain regions.  
8. **Top High-Risk Customers:** Highest risk score = 99; priority for targeted mitigation.

---

## Data Governance & Security

- **Row-Level Security (RLS):** Applied per region (North, South, East, West)  
- **View As Role:** Ensured accurate filtering in Power BI

---

## Conclusion & Recommendations

1. Implement region-specific adjustments, especially in the West.  
2. Refine underwriting models considering income, health, and driving factors.  
3. Segment underwriting by claims history and risk behaviors.  
4. Prioritize high-risk policy monitoring and pricing adjustments.  
5. Use interactive dashboards for continuous risk management.

---


 
