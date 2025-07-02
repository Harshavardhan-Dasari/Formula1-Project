# 🏎️ Formula 1 Data Engineering Project

This project demonstrates a complete data engineering workflow using **Azure Databricks** and **Apache Spark**, focused on building an analytics pipeline for historical Formula 1 racing data.

---

## 📌 Project Overview

The goal of this project is to design and implement a scalable, end-to-end data pipeline to ingest, transform, and analyze Formula 1 racing data.  
The pipeline follows a medallion architecture (Bronze, Silver, Gold layers) and delivers clean, enriched datasets ready for business insights.

---

## 🛠️ Technologies Used

- Azure Databricks (Spark)
- Delta Lake
- SQL & PySpark
- Azure Data Lake Storage (ADLS)
- Notebook Workflows
- DBFS (Databricks File System)

---

## 📁 Project Structure

<pre> <code> 
  Formula1/
├── raw/ # Scripts to create raw ingestion tables (Bronze Layer)
│ └── 1.create_raw_tables.sql
│
├── trans/ # Transformation layer (Silver + Gold Layer)
│ ├── 0.create_presentation_database.sql
│ ├── 1.race_results.py
│ ├── 2.driver_standings.py
│ ├── 3.constructor_standings.py
│ └── 4.calculated_race_results.py
│
├── analysis/ # SQL scripts for analytics queries and insights
│ └── 1.find_dominant_drivers.sql
│
├── includes/ # Reusable utility functions
│ ├── common_functions.py
│ └── configuration.py
│
└── manifest.mf # Project metadata
  
  </code> </pre>
---

## ⚙️ Data Pipeline Architecture

1. **Ingestion Layer (Bronze)**  
   - Ingest raw JSON/CSV data using SQL scripts  
   - Load into Delta tables with appropriate schema

2. **Transformation Layer (Silver)**  
   - Clean and normalize race results, drivers, and constructors  
   - Compute driver and constructor standings using PySpark

3. **Presentation Layer (Gold)**  
   - Perform advanced analytics like calculating race winners and determining dominant drivers  
   - Prepare tables for dashboarding or downstream consumption

---

## 📊 Key Features

- Modular ETL scripts using PySpark and SQL
- Reusable config and helper functions for scalability
- Layered approach for raw, transformed, and aggregated data
- Insightful queries to find top performers, team performance, and race metrics

---

## 📈 Example Analytics

- Dominant drivers per decade
- Yearly constructor performance
- Race-by-race driver win ratio
- Points distribution among top teams

---

## 🚀 How to Run

1. Upload the dataset files into Databricks DBFS or mount Azure Data Lake Storage  
2. Open and run the SQL scripts in the `raw/` folder to create ingestion tables  
3. Run the Python scripts in `trans/` folder to transform and enrich the data  
4. Run SQL queries from the `analysis/` folder for insights

---

## 🧠 Skills Demonstrated

- Data ingestion & transformation using Spark
- Data modeling using star schema
- Writing efficient PySpark jobs and SQL analytics
- Building a maintainable pipeline using modular code


