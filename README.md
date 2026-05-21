**
End-to-End Insurance Fraud Detection Platform
**

This project demonstrates a **production-grade Data Engineering + Machine Learning system** for detecting fraudulent insurance claims in real time.

The pipeline ingests streaming and batch data, processes it using distributed systems, trains ML models, and serves predictions via an API with monitoring dashboards.

---

##  Problem Statement

Insurance companies face significant losses due to fraudulent claims.  
This system identifies high-risk claims using real-time analytics and machine learning.

---

##  Architecture Overview

**Pipeline Flow:**

Data Sources → Kafka (Streaming) / Batch → Data Lake → Spark Processing → Data Warehouse → ML Model → FastAPI → Dashboard

---

##  Tech Stack

| Layer            | Tools Used                          |
|------------------|----------------------------------|
| Ingestion        | Kafka, Python                    |
| Storage          | AWS S3 / Local Data Lake         |
| Processing       | PySpark                          |
| Data Warehouse   | PostgreSQL / Snowflake           |
| ML Model         | XGBoost, Scikit-learn            |
| Orchestration    | Apache Airflow                   |
| API              | FastAPI                          |
| Dashboard        | Streamlit                        |

---

##  Key Features

✅ Real-time data ingestion using Kafka  
✅ Batch ETL pipelines using PySpark  
✅ Feature engineering for fraud detection  
✅ ML model with high precision (XGBoost)  
✅ REST API for real-time predictions  
✅ Workflow orchestration using Airflow  
✅ Interactive dashboard for fraud insights  

---

##  Machine Learning

- Model: **XGBoost Classifier**
- Features:
  - Claim frequency
  - Average claim amount
  - Claim anomalies
  - Customer risk profile
- Output: Fraud probability score (0–1)

---

##  API Endpoint

### Predict Fraud

```http
POST /predict
