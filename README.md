# Netflix End-to-End Data Engineering Project (Azure)

## 📺 Project Overview
This project is a production-level data engineering pipeline built on **Microsoft Azure**. It processes Netflix movie and TV show data through a **Medallion Architecture**,**Dynamic Parameterization**,**Delta Live Tables (DLT)** transforming raw data into business-ready insights.

## 🏗️ Architecture
The project follows a modern **Lakehouse Architecture**:

![Architecture Diagram](https://github.com/user-attachments/assets/1fb3572b-0f5e-473b-a754-77f0a2be862e)

1. **Ingestion:** Data is ingested from GitHub using **Azure Data Factory (ADF)**.
2. **Raw Storage (Bronze):** Incremental ingestion into **ADLS Gen2** using Databricks **Auto Loader**.
3. **Refinement (Silver):** Data cleaning and schema enforcement using **PySpark** in parameterized Databricks notebooks.
4. **Aggregation (Gold):** Business-level transformations and quality checks using **Delta Live Tables (DLT)**.
5. **Serving:** Data is pushed to **Azure Synapse Analytics** and visualized in **Power BI**.

## 🛠️ Tech Stack
* **Orchestration:** Azure Data Factory (ADF) & Databricks Workflows
* **Storage:** Azure Data Lake Storage (ADLS) Gen2
* **Processing:** Azure Databricks (PySpark)
* **Data Format:** Delta Lake
* **Framework:** Delta Live Tables (DLT)
* **Security:** Azure Key Vault (Secret Management)
* **Visualization:** Power BI / Azure Synapse Analytics

## 🚀 Key Features
* **Auto Loader:** Implemented Databricks Auto Loader to automatically detect and process new files arriving in the data lake.
* **Medallion Architecture:** Followed the Bronze (Raw), Silver (Cleaned), and Gold (Aggregated) layer pattern.
* **Dynamic Parameterization:** Built reusable pipelines where table names and file paths are passed as parameters.
* **Delta Live Tables (DLT):** Used DLT to build declarative data pipelines with quality monitoring.

## 📂 Project Structure
* `ADF_Netflix_Azure_Data_Engineering_project/`: JSON exports of parameterized ADF pipelines.
* `Netflix Project/`: PySpark notebooks (Bronze, Silver, Gold).
* `DLT_GOLD/`: Delta Live Tables definitions.

## 📊 Pipeline Monitoring
Below is a screenshot of the successful pipeline orchestration:

![ADF Pipeline Run](images/adf_run.png)

![Databricks Workflow](images/databricks_workflow.png)

## 📈 Visualizations & Insights
The final data is visualized to show content trends and distribution.

![Power BI Dashboard](images/dashboard.png)

## 🛠️ Setup Instructions
1. **Azure Resources:** Set up ADLS Gen2, ADF, and Databricks.
2. **Secrets:** Store keys in Azure Key Vault.
3. **Ingestion:** Run the ADF pipeline to fetch data to the Bronze container.
4. **Transformation:** Execute Databricks Workflows for Silver and Gold layers.
5. **Dashboard:** Connect Power BI to the Databricks SQL Warehouse.

---

