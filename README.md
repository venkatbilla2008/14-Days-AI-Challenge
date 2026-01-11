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

This architecture follows **industry best practices** used in companies
like Netflix, Comcast, and Shell.

------------------------------------------------------------------------

## 📂 Repository Structure

    14-Days-AI-Challenge/
    │
    ├── Day 1 - Databricks & Lakehouse Basics
    ├── Day 2 - Apache Spark
    ├── Day 3 - Advanced Spark Analytics
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

**Focus:** Understanding Databricks platform, Lakehouse architecture,
workspace structure, and enterprise use cases.

### Topics Covered

-   Why **Databricks vs Pandas/Hadoop**
-   **Lakehouse architecture** (Bronze, Silver, Gold layers)
-   **Databricks workspace structure**
-   **Unity Catalog & Volumes**
-   Industry use cases:
    -   **Netflix** -- content & recommendation analytics\
    -   **Comcast** -- customer support analytics\
    -   **Shell** -- sensor data & forecasting pipelines

### Key Learnings

-   Databricks unifies **Data Engineering + Analytics + AI** on one
    platform\
-   Lakehouse removes the need for separate data lake and warehouse\
-   Volumes provide **governed, enterprise-grade storage**\
-   Architecture designed for **scalability, security, and AI
    readiness**

------------------------------------------------------------------------

# 📅 Day 2 -- Apache Spark Fundamentals (10th Jan 2026)

Day 2 focused on building strong foundations in **Apache Spark using
Databricks**, covering notebook magic commands, DataFrames vs RDDs,
reading data, transformations, and exporting results.

### Topics Covered

-   Notebook magic commands: **%python, %sql, %fs**
-   **Spark Architecture** -- Driver, Executors, DAG
-   **Lazy evaluation** and execution flow
-   **DataFrames vs RDDs**
-   Reading **CSV, Parquet, JSON**
-   Core transformations: select, filter, groupBy, withColumn, distinct,
    orderBy
-   Writing data to **Parquet and Lakehouse tables**

### Key Learnings

-   DataFrames with **Catalyst optimization** significantly outperform
    RDDs\
-   Lazy evaluation becomes clearer when working with real
    transformations\
-   Parquet improves performance via column pruning & predicate
    pushdown\
-   Strong foundation built for advanced analytics patterns

------------------------------------------------------------------------

# 📅 Day 3 -- Advanced Spark Analytics (11th Jan 2026)

Day 3 focused on applying Spark concepts to **real-world analytics
patterns** using Databricks. This included hands-on work and deep
technical discussions via Databricks chat.

### Topics & Work Completed

#### 1. Reading Optimized Parquet from Volumes

``` python
df_oct = spark.read.parquet("/Volumes/workspace/ecommerce/ecommerce_data/parquet/oct/")
```

#### 2. Window Functions -- Running Totals per User

``` python
from pyspark.sql import Window, functions as F

window = Window.partitionBy("user_id").orderBy("event_time")

df_with_running_total = df_oct.withColumn(
    "cumulative_events",
    F.count("*").over(window)
)
```

#### 3. Funnel Analysis (view → cart → purchase)

``` python
funnel_df = df_oct.groupBy("category_code").agg(
    F.sum(F.when(F.col("event_type") == "view", 1).otherwise(0)).alias("views"),
    F.sum(F.when(F.col("event_type") == "cart", 1).otherwise(0)).alias("carts"),
    F.sum(F.when(F.col("event_type") == "purchase", 1).otherwise(0)).alias("purchases")
).withColumn(
    "view_to_cart_rate", (F.col("carts") / F.col("views")) * 100
).withColumn(
    "cart_to_purchase_rate", (F.col("purchases") / F.col("carts")) * 100
).withColumn(
    "view_to_purchase_rate", (F.col("purchases") / F.col("views")) * 100
)
```

#### 4. Conversion Rate Without Pivot (Enterprise-Safe Pattern)

``` python
conversion_df = df_oct.groupBy("category_code").agg(
    F.sum(F.when(F.col("event_type") == "view", 1).otherwise(0)).alias("views"),
    F.sum(F.when(F.col("event_type") == "purchase", 1).otherwise(0)).alias("purchases")
).withColumn(
    "conversion_rate", (F.col("purchases") / F.col("views")) * 100
)
```

#### 5. Catalyst Optimization & Lazy Evaluation (Conceptual Deep Dive)

-   Observed how **Catalyst optimizer** rewrites query plans for
    performance
-   Understood how **lazy evaluation** builds the DAG before execution
-   Discussed **shuffles, aggregations, and execution planning** via
    Databricks chat

### Key Learnings from Day 3

-   Window functions are powerful for **user-level analytics**
-   Funnel analysis is critical for **ecommerce & product analytics**
-   Conditional aggregation is preferred over pivot in enterprise setups
-   Seeing Catalyst & lazy evaluation in action **changes how you think
    about performance**
-   These patterns directly map to **ecommerce, call center, and
    healthcare analytics pipelines**

------------------------------------------------------------------------

## 🚀 Why This Project Matters

This repository demonstrates: - **Modern data engineering practices** -
**Enterprise Lakehouse architecture design** - **Scalable ingestion of
large datasets** - **AI & ML ready data pipelines** - **Production-style
project structure (not toy examples)**

------------------------------------------------------------------------

## 🤖 AI & ML Use Cases (Upcoming)

-   Sentiment Analysis on customer interactions\
-   Topic Modeling on feedback / reviews\
-   Emotion detection & intent classification\
-   Feature engineering for ML models\
-   BERT-based embeddings & clustering

------------------------------------------------------------------------

## 📌 Next Steps (Day 4 Preview)

-   Joins & Window functions (advanced)
-   Sessionization (time-based analytics)
-   Text preprocessing for AI pipelines
-   Performance tuning & optimization

------------------------------------------------------------------------

## 👤 Author

**Venkat M**
Data Engineering \| Databricks \| Apache Spark \| AI & ML \| Power BI \|
Analytics Pipelines

GitHub: https://github.com/venkatbilla2008

------------------------------------------------------------------------

## ⭐ If you find this useful, feel free to star the repo!
