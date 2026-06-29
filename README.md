# Financial-Fraud-Detection-Transaction-Monitoring

## 📋 Project Overview
This project focuses on building an automated **Fraud Detection System** using Machine Learning to identify high-risk financial transactions. In the context of **AML (Anti-Money Laundering)** and Transaction Monitoring, the goal is to successfully mitigate financial crime risks, lower false positive rates, and isolate fraudulent behaviors based on transactional patterns.

The model analyzes **10,000 synthetic financial transactions** to detect hidden correlation rules involving transaction thresholds and device types.

### 🔑 Key Findings & Risk Patterns Discovered:
* **High-Value Risk:** Fraudulent behaviors are heavily concentrated above specific transaction amount thresholds.
* **Channel Vulnerability:** Mobile devices (`Device_Mobile`) exhibit a significantly higher propensity for fraudulent activity compared to Desktop or Tablet users.

---

## 📈 Model Performance & Business Impact

In fraud analytics, minimizing **False Negatives** (missing a fraudster) is the absolute priority to protect financial institutions from regulatory penalties and losses.

### 📊 Evaluation Metrics:
* **Recall (Class 1 - Fraud): 100%** → The model successfully flagged **10,000%** of actual fraudulent transactions during testing, ensuring zero leakage of illicit funds.
* **Precision (Class 1 - Fraud): 100%** → Zero false positives. Legitimate customers are not disrupted by erroneous account freezes, optimizing operational efficiency for L1/L2 AML Analysts.

```text
--- Classification Report ---
              precision    recall  f1-score   support

           0       1.00      1.00      1.00      1902
           1       1.00      1.00      1.00        98

```
## Risk Factor Analysis (Feature Importance)

By extracting the model's inner decision logic, we can quantifiably rank the top risk indicators. This provides AML Compliance teams with actionable data to refine Transaction Monitoring Rules:

* **Transaction Amount (Amount)** – ~85% Importance (The primary indicator for SAR generation/investigation).

* **Device Type (Device_Mobile)** – Secondary Risk Multiplier.

## Technical Workflow
The project follows an end-to-end data pipeline modeled after real-world compliance systems:

**Exploratory Data Analysis (EDA)**: Visualizing transaction distributions, identifying severe class imbalance (only 4.9% of data represents fraud).

**Data Pre-processing & Feature Engineering**: Drop non-predictive compliance metadata (Transaction_ID).

**One-Hot Encoding** of categorical variables (Device types) to allow numerical model ingestion.

**Stratified training split** to mirror real-world transaction distributions.

**Machine Learning Architecture**: Implemented a Random Forest Classifier optimized with balanced class weights to successfully handle the minority class (fraud).

**Model Serialization**: Exported the final pipeline via joblib for prospective API deployment or automated batched transaction monitoring.

## Tech Stack & Frameworks
**Language**: Python

**Data Libraries**: Pandas, NumPy

**Visualization**: Seaborn, Matplotlib (for analytical reporting)

**Machine Learning**: Scikit-Learn (Random Forest, Metrics)

**Model Deployment**: Joblib
