# Azure End-to-End Data Engineering Project
This project is a data engineering pipeline solution to a made-up business problem, created to aid in my learning and understanding of data pipelining.

## Project Overview

This project addresses a critical business need by building a comprehensive data pipeline on Azure. The goal is to extract data, transform it in the cloud, and generate actionable insights through a Power BI dashboard.


## Solution Overview

To meet these requirements, the solution is broken down into the following components:

1. **Data Ingestion**: 
    - Extract data from an CSV file (Big Table).
	- Load data to Azure SQL Server and move it to Azure Data Lake Storage (ADLS) using Azure Data Factory (ADF)

2. **Data Transformation**:
    - Use Azure Databricks to clean and transform the data. Implement SCD Type 2 to create dimensions and fact table.
    - Organize the data into Bronze, Silver, and Gold layers for raw, cleansed, and aggregated data respectively.

3. **Data Loading and Reporting**:
    - Load the transformed data into Power BI to visualize the data.

4. **Automation**:
    - Schedule the pipeline to run daily, ensuring that the data and reports are always up-to-date.

## Technology Stack

- **Azure Data Factory (ADF)**: For orchestrating data movement and transformation.
- **Azure Data Lake Storage (ADLS)**: For storing raw and processed data.
- **Azure Databricks**: For data transformation and processing.
- **Azure SQL Server**: For data warehousing, SQL-based analytics and as a helper for incremental loading.
- **Power BI**: For data visualization and reporting.
- **Azure Key Vault**: For securely managing credentials and secrets.


![Architecture](https://raw.githubusercontent.com/KacperFu/Azure-DE-Project/refs/heads/main/DE%20Pipeline.png)


## Setup Instructions

### Step 1: Azure Environment Setup

1. **Create Resource Group**: Set up a new resource group in Azure.
2. **Provision Services**:
   - Create an Azure Data Factory instance.
   - Set up Azure Data Lake Storage with `bronze`, `silver`, and `gold` containers.
   - Set up an Azure Databricks workspace and Azure SQL Server workspace.
   - Configure Azure Key Vault for secret management.

### Step 2: Data Ingestion

1. **Ingest Data with ADF**: Create pipelines in ADF to copy data from GitHub to the SQL Server and move it to `bronze` layer in ADLS.

### Step 3: Data Transformation

1. **Mount Data Lake in Databricks**: Configure Databricks to access ADLS.
2. **Transform Data**: Use Databricks notebooks to clean and aggregate the data, moving it from `bronze`.
3. **Create SCD Type 2**: Maintain historical data when ingesting incremental data

![Databrick Flow](https://raw.githubusercontent.com/KacperFu/Azure-DE-Project/refs/heads/main/PySpark%20Cluster.png)

### Step 4: Data Loading and Reporting

1. **Load Data into Power BI**: Connect to Power BI and create visualizations based on business requirements.

### Step 5: Automation and Monitoring

1. **Schedule Pipelines**: Use ADF to schedule the data pipelines to run daily.
2. **Monitor Pipeline Runs**: Use the monitoring tools in ADF and Synapse to ensure successful pipeline execution.

### Step 6: Security and Governance

1. **Manage Access**: Set up role-based access control (RBAC) using Azure Entra ID (formerly Active Directory).

### Step 7: End-to-End Testing

1. **Trigger and Test Pipelines**: Insert new records into the SQL database and verify that the entire pipeline runs successfully, updating the Power BI dashboard.
