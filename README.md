# Azure End-to-End Data Engineering Project

This project demonstrates a comprehensive data pipeline solution utilizing various Azure services for data ingestion, transformation, and reporting, culminating in a Power BI dashboard that provides actionable business insights.

## Table of Contents

- [Project Overview](#project-overview)
- [Architecture](#architecture)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Azure Services Used](#azure-services-used)
- [Implementation Details](#implementation-details)
- [Contributing](#contributing)

## Project Overview

This project showcases an end-to-end data pipeline implemented on Microsoft Azure. It involves extracting data from a CSV file, processing it through various Azure services, and visualizing the results in Power BI.

## Architecture

The data pipeline consists of the following key components:

1. **Data Ingestion:** Data is extracted from a CSV file and loaded into Azure SQL Server, then moved to Azure Data Lake Storage (ADLS) using Azure Data Factory (ADF).

2. **Data Transformation:** Azure Databricks is used for data cleaning and transformation, implementing Slowly Changing Dimension (SCD) Type 2 to create dimensions and fact tables. The data is organized into Bronze, Silver, and Gold layers, representing raw, cleansed, and aggregated data, respectively.

3. **Data Loading and Reporting:** The transformed data is loaded into Power BI. A dashboard is then used to visualize the insights derived from the data.

## Features

- **End-to-End Data Pipeline:** From data ingestion to visualization.
- **Layered Data Architecture:** Bronze (raw), Silver (cleansed), and Gold (aggregated) layers.
- **Data Transformation:** Implementation of SCD Type 2 for dimension tables.
- **Interactive Reporting:** Power BI dashboard for data visualization.

## Prerequisites

Before running this project, ensure you have:

- An active Azure subscription.
- Access to Azure services: Azure Data Factory, Azure Data Lake Storage Gen2, Azure Databricks and Power BI.
- Basic knowledge of SQL and Python.


## Azure Services Used

- **Azure Data Factory (ADF)**: For orchestrating data movement and transformation.
- **Azure Data Lake Storage (ADLS)**: For storing raw and processed data.
- **Azure Databricks**: For data transformation and processing.
- **Azure SQL Server**: For data warehousing, SQL-based analytics and as a helper for incremental loading.
- **Power BI**: For data visualization and reporting.
- **Azure Key Vault**: For securely managing credentials and secrets.

![Architecture](https://raw.githubusercontent.com/KacperFu/Azure-DE-Project/refs/heads/main/DE%20Pipeline.png)



## Implementation Details

### Data Ingestion

- Data is extracted from a CSV file and loaded into Azure SQL Server.
- Azure Data Factory moves the data from Azure SQL Server to Azure Data Lake Storage (ADLS).

### Data Transformation

- **Bronze to Silver:** Raw data is cleaned and enriched using Azure Databricks.
- **Silver to Gold:** Analytical datasets are created, implementing SCD Type 2 for dimension tables.


![Databrick Flow](https://raw.githubusercontent.com/KacperFu/Azure-DE-Project/refs/heads/main/PySpark%20Cluster.png)



### Data Loading and Reporting

- A Power BI dashboard is created to visualize the insights derived from the data.

# Contributing

Feel free to fork this repository and make changes. Contributions are welcome!



