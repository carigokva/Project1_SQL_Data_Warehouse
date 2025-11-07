# Project1-SQL-Data-Warehouse
The Sales Data Warehouse project implements a scalable data warehousing pipeline using the Medallion Architecture framework.
This repository demonstrates the full lifecycle of building a data warehouse—from raw data ingestion to business-ready data.

# Building the Data Warehouse

## Project Requirements
Objective: Develop a modern data warehouse using SQL Server to consolidate sales data, enabling analytical reporting and informed decision-making.

Specifications
* Data Sources: Import data from two source systems (ERP and CRM) provided as CSV files.
* Data Quality: Cleanse and resolve data quality issues prior to analysis.
* Integration: Combine both sources into a single, user-friendly data model designed for analytical queries.
* Scope: Focus on the latest dataset only; historization of data is not required.
* Documentation: Provide clear documentation of the data model to support both business stakeholders and analytics teams.

![data architecture](https://github.com/carigokva/Project1_SQL_Data_Warehouse/blob/main/images/data_architecture.PNG)

## Project Walkthrough
### Building the Bronze Layer
Objective: Import raw data from the source systems into the bronze layer

Steps:
* Create and run DDL scripts to create tables that will contain the raw data from source systems. ([crm ddl](https://github.com/carigokva/Project1_SQL_Data_Warehouse/blob/main/bronze/bronze_crm_ddl), [erp ddl](https://github.com/carigokva/Project1_SQL_Data_Warehouse/blob/main/bronze/bronze_erp_ddl))
* Create and run DML scripts to insert raw data into tables under the bronze layer. ([crm dml](https://github.com/carigokva/Project1_SQL_Data_Warehouse/blob/main/bronze/bronze_crm_load), [erp dml](https://github.com/carigokva/Project1_SQL_Data_Warehouse/blob/main/bronze/bronze_erp_ddl))

### Building the Silver Layer
Objective: Clean and transform raw data from the Bronze layer by applying business logic and handling data quality issues.

Steps:
* Create and run scripts to perform quality check and data transformation on each table in the bronze layer. ([qc scripts](https://github.com/carigokva/Project1_SQL_Data_Warehouse/tree/main/bronze/qc))
* Create and run scripts to create tables, then insert refined data into Silver Layer tables. DDL: ([crm ddl](https://github.com/carigokva/Project1_SQL_Data_Warehouse/blob/main/silver/silver_crm_ddl), [erp ddl](https://github.com/carigokva/Project1_SQL_Data_Warehouse/blob/main/silver/silver_erp_ddl)). DML: ([crm load](https://github.com/carigokva/Project1_SQL_Data_Warehouse/blob/main/silver/silver_crm_load), [erp load](https://github.com/carigokva/Project1_SQL_Data_Warehouse/blob/main/silver/silver_erp_load)).

### Building the Gold Layer
Objective: To deliver curated, high-quality, and analytics-ready data by aggregating and structuring refined datasets from the Silver layer.

Steps:
* Explore and identify Business Objects.
  ![business objects](https://github.com/carigokva/Project1_SQL_Data_Warehouse/blob/main/images/business_objects.png)
* Identify Fact and Dimension Tables.
* Build the Data Model.
  ![data model](https://github.com/carigokva/Project1_SQL_Data_Warehouse/blob/main/images/data_model.png)
* Create and run scripts to create fact and dimension tables that are ready for data analysis. ([creating fact and dim tables](https://github.com/carigokva/Project1_SQL_Data_Warehouse/tree/main/gold))
