# Azure-Data-Engineering-ETL-Driven-Car-Sales-Insights

This project showcases a comprehensive data engineering workflow built on the Medallion Architecture. It processes the AdventureWorks dataset, hosted on GitHub, utilizing various Azure services. The pipeline spans from raw data ingestion to delivering final insights through Power BI dashboards, offering a well-structured and scalable ETL solution.

![image](https://github.com/user-attachments/assets/a200e788-ce3f-490b-91d7-311c810cc55d)

# Medallion Architecture Layers

![image](https://github.com/user-attachments/assets/a40bc94f-791d-4548-ae2f-fa39f6b95028)

Bronze Layer: Raw data is imported into the Azure Data Lake via pipelines created using Azure Data Factory (ADF). A Linked Service is configured for both GitHub (using an HTTP Linked Service) and the Azure Data Lake to access the dataset. Dynamic pipelines leverage LookUp and ForEach activities to ingest multiple CSV files (10 files in total for this project).

Silver Layer: Data transformation is carried out in Azure Databricks, where processes such as data cleansing, validation, and enrichment are performed. The refined data is then stored in a dedicated Silver container for further processing.

Gold Layer: Azure Synapse Analytics is utilized to define an external table schema within a Gold layer. Data stored in the Silver container is made queryable as traditional tables using the OPENROWSET() function. This stage stores aggregated, analytics-ready data in the Gold container for advanced analysis.

Visualization: Power BI is integrated with Azure Synapse Analytics to enable visualization of the analytics-ready data. Interactive dashboards provide key insights, such as sales trends and performance, based on the AdventureWorks dataset.

# Architecture Diagram

The workflow follows the Medallion Architecture pattern:

![image](https://github.com/user-attachments/assets/df7fb385-4307-41cb-a2db-4e6a7d533702)

#Technical Stack

The project utilizes the following technologies:

Azure Data Factory: For Data Ingestion and Pipeline Creation. Azure Data Lake: For Data Storage in Bronze, Silver, and Gold containers. Azure Databricks: For Data Transformation and enrichment. Azure Synapse Analytics: For querying and managing external tables. Power BI: For Data Visualization and Reporting.

AdventureWorks Dataset: https://www.kaggle.com/datasets/ukveteran/adventure-works/data Source: GitHub Type: CSV files (10 files ingested) Description: Contains sales data used for reporting and analysis.

# ETL Pipeline

# Data Ingestion:

ADF dynamically ingests CSV files from GitHub into the Bronze container. Uses parameterized pipelines for scalability.

![image](https://github.com/user-attachments/assets/a9300d1b-4e1c-4b66-8d90-12a7c09769da)

# Data Transformation

Databricks performs cleaning and transformations. Data is saved in the Silver container for further analysis.

![image](https://github.com/user-attachments/assets/adc0f2ff-3ed7-4858-9a95-fc2b2848306d)

# Data Preparation for Analytics

Synapse Analytics enables querying of data from the Silver container. Finalized analytics ready data is saved in the Gold container.

![image](https://github.com/user-attachments/assets/39b75b03-83c7-4731-8521-815c944cf761)

# Visualization

Power BI connects to Synapse to create interactive dashboards for insights.

![image](https://github.com/user-attachments/assets/29552c7a-8ba2-404f-9a08-96ffee8ec739)

# Solution Highlights

Dynamic Pipelines: Parameterized Azure Data Factory pipelines streamline and automate the data ingestion process. Efficient Transformations: Azure Databricks ensures data integrity and quality through robust transformation logic. Seamless Querying: Azure Synapse Analytics facilitates straightforward data access with the OPENROWSET() function. Interactive Dashboards: Power BI provides an intuitive and user-friendly visualization layer for creating reports and insights.

# Key Features

Implements the Medallion Architecture to enable structured and organized data processing. Leverages multiple Azure services for a comprehensive, end-to-end data solution. Builds a scalable and flexible framework for processing and analyzing large volumes of data. Utilizes Power BI to visualize actionable sales data insights through interactive dashboards.











