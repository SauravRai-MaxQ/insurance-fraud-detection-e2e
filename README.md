End-to-End Underinsurance Detection Platform (Batch Processing)

This project demonstrates a production-grade Data Engineering + Machine Learning system for identifying underinsured customers and assets using historical policy and claims data.

The platform processes batch data, engineers risk features, trains machine learning models, and serves recommendations through APIs and business dashboards.

Problem Statement

Insurance companies often face revenue leakage and customer risk exposure due to underinsurance, where customers purchase coverage that is significantly lower than the actual value of their assets or risk profile.

This system identifies policies that are potentially underinsured and recommends coverage adjustments using data analytics and machine learning.

Architecture Overview
Pipeline Flow
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
      (Underinsurance Risk)
            │
            ▼
      FastAPI Service
            │
            ▼
   Streamlit Dashboard

Tech Stack
Layer	Tools UsedData Ingestion	Python, CSV, Database Connectors
Storage	AWS S3 / Local Data Lake
Processing	PySpark
Data Warehouse	PostgreSQL / Snowflake
ML Model	XGBoost, Scikit-learn
Orchestration	Apache Airflow
API	FastAPI
Dashboard	Streamlit
Key Features

✅ Batch ingestion of policy, claims, and customer datasets

✅ Automated ETL pipelines using PySpark

✅ Underinsurance risk feature engineering

✅ Machine learning-based risk scoring

✅ Coverage adequacy recommendations

✅ Workflow orchestration using Airflow

✅ Interactive business dashboard

✅ REST API for policy risk assessment

Data Sources

The platform combines:

Policy information
Asset/property values
Claims history
Customer demographics
Geographic risk indicators
Inflation and market valuation data
Machine Learning
Model

XGBoost Regressor / Classifier

Key Features
Sum insured amount
Estimated replacement value
Historical claim frequency
Claim severity
Customer segment
Property age
Location risk score
Inflation-adjusted asset valuation
Output
Underinsurance Risk Score: 0 – 1

0.00 – 0.30 → Low Risk
0.31 – 0.60 → Medium Risk
0.61 – 1.00 → High Risk

Example
{
  "policy_id": "POL12345",
  "underinsurance_score": 0.87,
  "risk_level": "High",
  "recommended_coverage": 1250000
}

Batch ETL Workflow
Daily Pipeline
1. Extract policy data
2. Extract claims data
3. Load data into Data Lake
4. Transform using PySpark
5. Generate risk features
6. Load curated data into Warehouse
7. Train/Refresh ML model
8. Store risk scores
9. Publish dashboard metrics

Airflow Orchestration

DAG Tasks:

extract_policy_data
        ↓
extract_claim_data
        ↓
load_to_data_lake
        ↓
spark_feature_engineering
        ↓
load_to_warehouse
        ↓
train_model
        ↓
generate_scores
        ↓
update_dashboard

API Endpoint
Assess Underinsurance Risk

POST /predict

Request:

{
  "policy_id": "POL12345",
  "insured_amount": 800000,
  "estimated_asset_value": 1500000,
  "claim_count": 4,
  "location_risk": "Medium"
}


Response:

{
  "underinsurance_score": 0.87,
  "risk_level": "High",
  "recommended_coverage": 1250000
}

Dashboard Metrics

The Streamlit dashboard can provide:

Total policies analyzed
High-risk underinsured policies
Coverage gap distribution
Risk by geography
Risk by customer segment
Recommended additional premium opportunity
Monthly trend of underinsurance exposure
Business Benefits
Reduce claim settlement disputes
Increase premium revenue through accurate coverage
Improve customer protection
Identify high-risk portfolios proactively
Support underwriting decisions with data-driven insights

Project Title:

End-to-End Underinsurance Detection and Coverage Optimization Platform

This topic is highly relevant to insurance analytics and can be implemented entirely using batch processing with PySpark, Airflow, PostgreSQL/Snowflake, XGBoost, FastAPI, and Streamlit, without requiring Kafka or real-time streaming infrastructure.
