# 🚀 14 Days AI Challenge – Databricks Lakehouse + AI & ML Pipeline

This repository contains my hands-on work from the **14 Days AI Challenge**, focused on building an **enterprise-grade Databricks Lakehouse architecture** for large-scale ecommerce data ingestion, processing, and AI & ML-based analytics.

The project demonstrates how to ingest large datasets, structure them using **Unity Catalog + Volumes**, apply **Bronze → Silver → Gold** transformations, and prepare data for **sentiment analysis, topic modeling, and BI consumption**.

---

## 📌 Project Objectives

- Build a **Lakehouse architecture** using Databricks
- Ingest large ecommerce datasets (5GB+ CSV files)
- Use **Unity Catalog + Volumes** for governed storage
- Design **Bronze, Silver, Gold** layers
- Enable **AI & ML pipelines**
- Prepare data for **Power BI / Analytics consumption**
- Maintain **Git-based version control** using Databricks Repos

---

## 🏗️ Architecture Overview

Source (CSV / ZIP files)
↓
Bronze Layer (Raw data in Volumes)
↓
Silver Layer (Cleaned & validated data)
↓
Gold Layer (Aggregations, KPIs, Features)
↓
BI / AI & ML Models

---

## 🧰 Tech Stack

- **Databricks (Apache Spark)**
- **Unity Catalog & Volumes**
- **Python / PySpark**
- **SQL**
- **AI & ML**
- **GitHub (Version Control)**
- **Power BI (Downstream consumption – planned)**

---

## 📊 Dataset

- Monthly ecommerce event data (e.g., `2019-Oct.csv`, `2019-Nov.csv`)
- Large files (~5GB+)
- Stored and managed using:

---

## 🔄 Data Flow

1. **Upload ZIP files into Volume**
2. **Unzip using Databricks shell**
3. **Move CSVs into ecommerce volume**
4. **Load into Spark DataFrames**
5. **Convert to Parquet for performance**
6. **Apply transformations (Silver)**
7. **Create aggregations / features (Gold)**
8. **Prepare for AI & ML**

---

## 🤖 AI & ML (In Progress)

- Sentiment Analysis on customer interactions
- Topic Modeling on feedback / reviews
- Emotion detection & intent classification
- Feature engineering for ML models

---

## 🏢 Real-World Relevance

This project mirrors real enterprise use cases from companies like:
- **Netflix** – content & user behavior analytics
- **Comcast** – customer support AI & ML churn prediction
- **Shell** – large-scale data processing & forecasting

---

## 🎯 Why This Project Matters

This repository demonstrates:
- **Modern data engineering practices**
- **Lakehouse architecture design**
- **Scalable data ingestion**
- **AI-readiness of data pipelines**
- **Production-style structure (not toy examples)**

---

## 👤 Author

**Venkat Murali**  
Program Manager - Analytics | AI & ML | Power BI | AI Pipelines

GitHub: https://github.com/venkatbilla2008

---

## 📌 Next Steps

- Implement Silver & Gold transformations
- Add full AI & ML pipeline 

