# 🚀 14 Days AI Challenge -- Databricks Lakehouse + Apache Spark + AI & ML

This repository documents my hands-on journey through the **14 Days AI
Challenge**, focused on building an **enterprise-grade Databricks
Lakehouse architecture** for large-scale ecommerce data ingestion,
transformation, and **AI & ML analytics**.

The project demonstrates: - Real-world **data engineering workflows** -
**Unity Catalog + Volumes** based ingestion - **Bronze → Silver → Gold**
architecture - **Apache Spark (PySpark) fundamentals** - Preparation for
**AI, ML & Power BI integration**

------------------------------------------------------------------------

## 📌 Project Objectives

-   Build a **Lakehouse architecture** using Databricks\
-   Ingest **large ecommerce datasets (5GB+)**\
-   Use **Unity Catalog + Volumes** for governed storage\
-   Practice **Apache Spark transformations**\
-   Prepare data for **AI, ML & BI use cases**\
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
    BI / AI / ML Models

<<<<<<< Updated upstream
This architecture follows **industry best practices** used in companies
like Netflix, Comcast, and Shell.

=======
>>>>>>> Stashed changes
------------------------------------------------------------------------

## 📂 Repository Structure

    14-Days-AI-Challenge/
    │
    ├── Day 1 - Databricks & Lakehouse Basics
    ├── Day 2 - Apache Spark
    ├── Day 3 - Advanced Spark Analytics
    ├── Day 4 - Delta Lake, Unity Catalog & Data Governance
    │
    ├── ingestion/
    ├── bronze/
    ├── silver/
    ├── gold/
    ├── ai_ml/
    ├── schema_volume_setup/
    └── README.md

------------------------------------------------------------------------

## 🧰 Tech Stack

-   **Databricks (Apache Spark)**
-   **Unity Catalog & Volumes**
-   **Python / PySpark**
-   **SQL**
<<<<<<< Updated upstream
=======
-   **Delta Lake**
>>>>>>> Stashed changes
-   **AI & ML (Sentiment, Classification, Embeddings -- upcoming)**
-   **GitHub (Version Control)**
-   **Power BI (Downstream consumption -- upcoming)**

------------------------------------------------------------------------

## 📊 Dataset

-   Monthly ecommerce event data (e.g., `2019-Oct.csv`, `2019-Nov.csv`)\
-   Large files (\~5GB+)\
-   Managed using:

```{=html}
<!-- -->
```
    /Volumes/workspace/ecommerce/ecommerce_data/

------------------------------------------------------------------------

# 📅 Day 1 -- Databricks & Lakehouse Fundamentals

Topics: - Databricks vs Pandas/Hadoop - Lakehouse architecture (Bronze,
Silver, Gold) - Workspace structure - Unity Catalog & Volumes - Industry
use cases: Netflix, Comcast, Shell

------------------------------------------------------------------------

# 📅 Day 2 -- Apache Spark Fundamentals (10th Jan 2026)

Topics: - Spark Architecture -- Driver, Executors, DAG - Lazy
evaluation - DataFrames vs RDDs - Notebook magic commands (%python,
%sql, %fs) - Reading CSV, Parquet, JSON - Core transformations - Writing
Parquet & tables

------------------------------------------------------------------------

# 📅 Day 3 -- Advanced Spark Analytics (11th Jan 2026)

Topics: - Parquet reads from Volumes - Window functions (running
totals) - Funnel analysis (view → cart → purchase) - Conversion without
pivot - Catalyst & lazy evaluation deep dive - Databricks chat
discussions on DAGs, shuffles, execution planning

------------------------------------------------------------------------

# 📅 Day 4 -- Delta Lake, Unity Catalog & Data Governance (12th Jan 2026)

Topics: - saveAsTable and managed Delta tables - Unity Catalog governed
storage - DESCRIBE DETAIL for physical location - CTAS (Create Table As
Select) pattern - Schema enforcement testing - Schema evolution using
mergeSchema - Databricks chat deep dives on data protection & governance

------------------------------------------------------------------------

## 🚀 Why This Project Matters

-   Modern data engineering practices
-   Enterprise Lakehouse architecture
-   Scalable ingestion of large datasets
-   AI & ML ready pipelines
-   Production-style structure

------------------------------------------------------------------------

## 🤖 AI & ML Use Cases (Upcoming)

-   Sentiment Analysis\
-   Topic Modeling\
-   Emotion detection\
-   Feature engineering\
-   BERT embeddings

------------------------------------------------------------------------

## 📌 Next Steps (Day 5 Preview)

-   Sessionization
-   OPTIMIZE & ZORDER
-   Data quality checks
-   Feature store design

------------------------------------------------------------------------

## 👤 Author

<<<<<<< Updated upstream
**Venkat M**
Data Engineering \| Databricks \| Apache Spark \| AI & ML \| Power BI \|
Analytics Pipelines
=======
**Venkat Billa**\
Databricks \| Apache Spark \| Delta Lake \| AI & ML \| Power BI
>>>>>>> Stashed changes

GitHub: https://github.com/venkatbilla2008

------------------------------------------------------------------------

## ⭐ If you find this useful, feel free to star the repo!
