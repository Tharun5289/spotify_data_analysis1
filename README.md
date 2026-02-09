# 🎵 Spotify Data Analysis using AWS

## 📌 Project Overview
This project focuses on building an end-to-end data pipeline to analyze Spotify data using AWS services. The pipeline ingests raw CSV files, performs data transformation and cleansing using AWS Glue Visual ETL, and enables querying and analysis through AWS Athena. The final processed data can be used for downstream analytics and visualization using BI tools such as Amazon QuickSight.

---

## 📂 Source Data
The project uses three CSV files as source data:

- **Artists.csv**  
  Contains artist-related details such as artist name, popularity, and associated albums.

- **Albums.csv**  
  Includes album-level information like album name, artist, number of tracks, and album popularity.

- **Tracks.csv**  
  Stores track-level details such as track name, duration, popularity, and album reference.

---

## 🏗️ Architecture Overview

### High-Level Architecture
![High Level Architecture](docs/architecture/high_level_architecture.png)

**Description:**  
This diagram represents the end-to-end flow of Spotify data from ingestion to analytics using AWS services.

---

### AWS Glue Visual ETL Workflow
![Glue Visual ETL Workflow](docs/architecture/glue_visual_etl_workflow.png)

**Description:**  
This diagram illustrates how data is extracted from Amazon S3, transformed using AWS Glue Visual ETL, and written back to the processed S3 layer.

---

### Query & Analytics Architecture
![Athena and Analytics Architecture](docs/architecture/query_analytics_architecture.png)

**Description:**  
Shows how AWS Glue Crawler catalogs the processed data and how Amazon Athena queries the metadata for downstream analytics and BI tools.

---

## 🔄 Data Transformation Process
- Null values are handled appropriately  
- Duplicate records are removed  
- Data types are validated and corrected  
- Transformations are applied visually using **AWS Glue Visual ETL**

The Visual ETL feature allows source and destination connections to be configured graphically, making the transformation logic easy to understand and maintain.

---

## 🔐 IAM & Security
- An **IAM Role** is created to grant AWS Glue permissions to:
  - Read raw data from the source S3 bucket
  - Write transformed data to the destination S3 bucket
- The role follows the principle of least privilege.

---

## 🕷️ Metadata & Querying
- After transformation, an **AWS Glue Crawler** is run on the processed S3 location
- The crawler creates metadata tables in the **AWS Glue Data Catalog**
- These tables are queried using **Amazon Athena** to perform analysis on Spotify data

---

## 📊 Analytics & Visualization
The processed and cataloged data can be consumed by:
- **Amazon QuickSight**
- Other BI and visualization tools  

This enables insights such as:
- Most popular artists
- Top albums by popularity
- Track-level popularity analysis

---

## 🛠️ AWS Services Used
- Amazon S3  
- AWS Glue  
- AWS Glue Visual ETL  
- AWS Glue Crawler  
- AWS IAM  
- Amazon Athena  
- Amazon QuickSight  

---

## 🚀 Key Takeaways
- Demonstrates an end-to-end AWS data engineering workflow  
- Uses serverless and scalable AWS services  
- Showcases real-world ETL, data cleansing, and analytics patterns  

---

## 📁 Repository Structure (Suggested)
```
├── data/
│   ├── raw/
│   └── processed/
├── docs/
│   └── architecture/
│       ├── high_level_architecture.png
│       ├── glue_visual_etl_workflow.png
│       └── query_analytics_architecture.png
├── scripts/
├── README.md
```
