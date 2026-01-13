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

------------------------------------------------------------------------

## 📂 Repository Structure

    14-Days-AI-Challenge/
    │
    ├── Day 1 - Databricks & Lakehouse Basics
    ├── Day 2 - Apache Spark
    ├── Day 3 - Advanced Spark Analytics
    ├── Day 4 - Delta Lake, Unity Catalog & Data Governance
    ├── Day 5 - Incremental Pipelines & Delta Operations
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
-   **Delta Lake**
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

# 📅 Day 5 -- Incremental Pipelines & Delta Lake Operations (13th Jan 2026)

Day 5 focused on building **production-style incremental pipelines** and
handling real-world failures and fixes using Delta Lake.

### Topics & Work Completed

#### 1. Incremental MERGE (Upsert Pattern)

``` sql
MERGE INTO workspace.ecommerce.events_oct AS target
USING updates_view AS source
ON target.user_session = source.user_session
AND target.event_time = source.event_time
AND target.product_id = source.product_id
WHEN MATCHED THEN UPDATE SET *
WHEN NOT MATCHED THEN INSERT *
```

-   Designed correct **business keys for MERGE**
-   Handled update + insert in a single operation

------------------------------------------------------------------------

#### 2. Schema Alignment in MERGE

-   Resolved **column mismatch issues**
-   Added missing columns like `source_system` before MERGE
-   Learned why schema alignment is critical for safe upserts

------------------------------------------------------------------------

#### 3. Timestamp Normalization

``` python
to_timestamp(col("event_time"), "dd-MM-yyyy HH:mm")
```

-   Fixed **CAST_INVALID_INPUT** errors
-   Normalized timestamps to avoid pipeline failures

------------------------------------------------------------------------

#### 4. Delta Time Travel (Audit & Debugging)

``` sql
DESCRIBE HISTORY workspace.ecommerce.events_oct;
SELECT * FROM workspace.ecommerce.events_oct VERSION AS OF 0;
```

-   Queried historical versions
-   Understood rollback & audit use cases

------------------------------------------------------------------------

#### 5. Performance Optimization

``` sql
OPTIMIZE workspace.ecommerce.events_oct ZORDER BY (user_id, event_time);
```

-   Practiced **file compaction**
-   Used **ZORDER** for query performance

------------------------------------------------------------------------

#### 6. Storage Cleanup

``` sql
VACUUM workspace.ecommerce.events_oct RETAIN 168 HOURS;
```

-   Managed old files safely
-   Understood retention and cleanup strategies

------------------------------------------------------------------------

### Key Learnings from Day 5

-   Incremental pipelines require **correct business keys**
-   Schema alignment is mandatory for MERGE
-   Timestamp normalization is essential for reliability
-   Delta Lake provides **versioning, auditing, and rollback**
-   OPTIMIZE & VACUUM are critical for **performance and cost control**
-   These concepts are foundational for **AI & ML feature pipelines**

------------------------------------------------------------------------

## 🚀 Why This Project Matters

This repository demonstrates: - Modern data engineering practices -
Enterprise Lakehouse architecture - Scalable ingestion of large
datasets - AI & ML ready pipelines - Production-style structure

------------------------------------------------------------------------

## 🤖 AI & ML Use Cases (Upcoming)

-   Sentiment Analysis\
-   Topic Modeling\
-   Emotion detection\
-   Feature engineering\
-   BERT embeddings

------------------------------------------------------------------------

## 📌 Next Steps (Day 6 Preview)

-   Sessionization (time-based user journeys)
-   Drop-off & retention analysis
-   Gold feature table design
-   Feature store concepts

------------------------------------------------------------------------

## 👤 Author

**Venkat Murali**\
Databricks \| Apache Spark \| Delta Lake \| AI & ML \| Power BI

GitHub: https://github.com/venkatbilla2008

------------------------------------------------------------------------

## ⭐ If you find this useful, feel free to star the repo!
