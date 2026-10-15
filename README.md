# End-to-End Underinsurance Detection and Coverage Optimization Platform

A production-grade **Data Engineering + Machine Learning** solution for identifying underinsured policies and recommending optimal insurance coverage using historical insurance data.

The platform leverages batch processing, advanced feature engineering, machine learning, and business intelligence dashboards to help insurers proactively identify coverage gaps, improve customer protection, and uncover premium growth opportunities.

---

## 📌 Problem Statement

Insurance providers often face challenges when customers purchase coverage that is significantly lower than the actual value of their insured assets. This condition, known as **underinsurance**, can lead to:

- Inadequate claim settlements
- Customer dissatisfaction
- Increased financial risk exposure
- Lost premium revenue opportunities

This project aims to identify potentially underinsured policies by analyzing policy, claims, customer, and asset data using machine learning and data engineering pipelines.

---

## 🏗️ Architecture Overview

### Pipeline Flow

```text
Source Systems
(Policies, Claims, Customer Data)
            │
            ▼
     Batch Data Ingestion
            │
            ▼
         Data Lake
      (AWS S3 / Local)
            │
            ▼
      PySpark ETL &
   Feature Engineering
            │
            ▼
      Data Warehouse
(PostgreSQL / Snowflake)
            │
            ▼
      ML Model Training
 (Underinsurance Risk Model)
            │
            ▼
      FastAPI Service
            │
            ▼
    Streamlit Dashboard
```

---

## 🛠️ Tech Stack

### Data Ingestion
- Python
- CSV Files
- Database Connectors

### Storage
- AWS S3
- Local Data Lake

### Data Processing
- PySpark

### Data Warehouse
- PostgreSQL
- Snowflake

### Machine Learning
- XGBoost
- Scikit-learn

### Workflow Orchestration
- Apache Airflow

### API Layer
- FastAPI

### Dashboard & Visualization
- Streamlit

---

## ✨ Key Features

- Batch ingestion of policy and claims datasets
- Automated ETL pipelines using PySpark
- Feature engineering for underinsurance detection
- Machine learning-based risk assessment
- Coverage adequacy recommendations
- Workflow orchestration with Airflow
- REST API for risk prediction
- Interactive dashboards and business insights
- Scalable architecture for enterprise insurance data

---

## 📊 Data Sources

The system integrates data from multiple insurance domains:

### Policy Data
- Policy number
- Coverage amount
- Policy type
- Renewal history

### Claims Data
- Claim frequency
- Claim amounts
- Claim severity

### Customer Data
- Customer demographics
- Occupation
- Risk category

### Asset Data
- Property value
- Vehicle value
- Replacement cost estimates
- Asset age

### External Data
- Geographic risk indicators
- Inflation indexes
- Market valuation datasets

---

## 🤖 Machine Learning

### Model

**XGBoost Classifier**

### Input Features

- Sum insured amount
- Estimated replacement value
- Claim frequency
- Average claim amount
- Claim severity
- Customer risk profile
- Property age
- Location risk score
- Inflation-adjusted asset valuation

### Output

```text
Underinsurance Risk Score (0 - 1)

0.00 – 0.30  → Low Risk
0.31 – 0.60  → Medium Risk
0.61 – 1.00  → High Risk
```

### Example Output

```json
{
  "policy_id": "POL12345",
  "underinsurance_score": 0.87,
  "risk_level": "High",
  "recommended_coverage": 1250000
}
```

---

## 🔄 Batch ETL Workflow

### Daily Processing Pipeline

```text
1. Extract policy data
2. Extract claims data
3. Load raw datasets into Data Lake
4. Perform data cleansing and transformations
5. Generate underinsurance risk features
6. Load curated datasets into Data Warehouse
7. Train or refresh ML model
8. Generate risk scores
9. Publish dashboard metrics
```

---

## 📅 Apache Airflow Orchestration

The workflow is orchestrated using Airflow DAGs.

```text
extract_policy_data
          ↓
extract_claim_data
          ↓
load_to_data_lake
          ↓
spark_feature_engineering
          ↓
load_to_warehouse
      
