# lakehouse-medallion-databricks
End-to-end Medallion Architecture (Bronze → Silver → Gold) built on Databricks using PySpark, Delta Lake &amp; Spark SQL | Lakehouse pattern for scalable, reporting-ready data pipelines
🏅 Medallion Architecture on Databricks

📐 Architecture Overview
Raw Source Data
      │
      ▼
┌─────────────┐
│   BRONZE    │  Raw ingestion — unmodified, append-only Delta tables
│  (Raw Zone) │  Parquet/JSON/CSV → Delta Lake
└──────┬──────┘
       │
       ▼
┌─────────────┐
│   SILVER    │  Cleansed & conformed — deduped, typed, validated
│(Cleansed    │  PySpark transformations + data quality checks
│   Zone)     │
└──────┬──────┘
       │
       ▼
┌─────────────┐
│    GOLD     │  Business-ready — Star Schema, aggregations
│ (Curated    │  Spark SQL + fact/dimension models → Power BI
│   Zone)     │
└─────────────┘


📈 Gold Layer — Star Schema Design
              ┌──────────────┐
              │  dim_customer │
              └──────┬───────┘
                     │
┌──────────┐   ┌─────┴──────────┐   ┌─────────────┐
│dim_product├───┤ fact_transactions├───┤  dim_date   │
└──────────┘   └─────┬──────────┘   └─────────────┘
                     │
              ┌──────┴───────┐
              │  dim_location │
              └──────────────┘

🗺️ Roadmap

 Bronze ingestion pipeline
 Silver cleansing & data quality
 Gold star schema build
 Incremental load pattern (watermark-based)
 Data quality reporting dashboard
 
