# 🚀 14 Days AI Challenge -- Databricks Lakehouse + Apache Spark + NLP

This repository documents my hands-on journey through the **14 Days AI
Challenge**, focused on building an **enterprise-grade Databricks
Lakehouse architecture** for large-scale ecommerce data ingestion,
transformation, and AI/NLP analytics.

The project demonstrates: - Real-world **data engineering workflows** -
**Unity Catalog + Volumes** based ingestion - **Bronze → Silver → Gold**
architecture - **Apache Spark (PySpark) fundamentals** - Preparation for
**NLP, Sentiment Analysis & Power BI integration**

------------------------------------------------------------------------

## 📌 Project Objectives

-   Build a **Lakehouse architecture** using Databricks\
-   Ingest **large ecommerce datasets (5GB+)**\
-   Use **Unity Catalog + Volumes** for governed storage\
-   Practice **Apache Spark transformations**\
-   Prepare data for **NLP, sentiment analysis & BI**\
-   Maintain **Git-based version control** using Databricks Repos +
    GitHub

------------------------------------------------------------------------

## 🏗️ Architecture Overview (Lakehouse Pattern)

    Source (CSV / ZIP files)
            ↓
    Bronze Layer (Raw data in Volumes)
            ↓
    Silver Layer (Cleaned & validated data)
            ↓
    Gold Layer (Aggregations, KPIs, Features)
            ↓
    BI / NLP / ML Models

------------------------------------------------------------------------

## 📂 Repository Structure

    14-Days-AI-Challenge/
    │
    ├── Day 1 - Databricks & Lakehouse Basics
    ├── Day 2 - Apache Spark
    ├── ingestion/
    ├── bronze/
    ├── silver/
    ├── gold/
    ├── nlp/
    ├── schema_volume_setup/
    └── README.md

------------------------------------------------------------------------

## 🧰 Tech Stack

-   **Databricks (Apache Spark)**
-   **Unity Catalog & Volumes**
-   **Python / PySpark**
-   **SQL**
-   **NLP (Sentiment, Topic Modeling, BERT -- upcoming)**
-   **GitHub (Version Control)**
-   **Power BI (Downstream consumption -- upcoming)**

------------------------------------------------------------------------

# 📅 Day 1 -- Databricks & Lakehouse Fundamentals

Topics: - Databricks vs Pandas/Hadoop - Lakehouse architecture - Unity
Catalog & Volumes - Industry use cases (Netflix, Comcast, Shell)

------------------------------------------------------------------------

# 📅 Day 2 -- Apache Spark Fundamentals (10th Jan 2026)

Covered: - Notebook magic commands (%python, %sql, %fs) - DataFrames vs
RDDs - Reading CSV, Parquet, JSON - Select, Filter, GroupBy, WithColumn,
Distinct, OrderBy - Writing Parquet, CSV, Tables

------------------------------------------------------------------------

## 👤 Author

**Venkat Billa**\
Databricks \| Apache Spark \| NLP \| Power BI \| AI Pipelines\
GitHub: https://github.com/venkatbilla2008
