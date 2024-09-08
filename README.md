# Airbnb CDC Ingestion Pipeline

This project demonstrates a **CDC (Change Data Capture) ingestion pipeline** for Airbnb customer and booking data using various Azure resources such as **Azure Data Lake Storage (ADLS)**, **Azure CosmosDB**, **Azure Data Factory (ADF)**, and **Azure Synapse Analytics**. The pipeline processes customer data periodically and performs **SCD Type 1 (Slowly Changing Dimension Type 1)** updates, as well as ingesting booking data via **CosmosDB Change Feeds** to update the booking dimension.

## Project Overview

The **Airbnb CDC Ingestion Pipeline** automates the data ingestion and transformation processes using Azure resources. It periodically pulls customer data from ADLS, performs **SCD1** updates on the **Customer Dimension Table** in Synapse, and processes **Booking CDC events** from CosmosDB via **Change Feeds**. Data transformations are applied to the booking events, and the data is upserted into a target table in **Azure Synapse**. The pipeline is designed to be fully automated and scalable.

## Tech Stack

- **Azure Data Lake Storage (ADLS)**
- **Azure CosmosDB**
- **Azure Data Factory (ADF)**
- **Azure Synapse Analytics**
- **Python**
- **SQL**

## Pipeline Architecture

### 1. **Customer Data Processing:**
   - **Data Source**: Customer data is ingested periodically (hourly) from **ADLS**.
   - **Transformation**: **SCD Type 1** transformation is applied to the **Customer Dimension Table** in **Azure Synapse**.
   - **Automation**: The ingestion and transformation processes are automated via an **Azure Data Factory (ADF) Pipeline**.

### 2. **Booking Data Processing:**
   - **Data Source**: **CosmosDB Change Feeds** capture **CDC events** for bookings.
   - **Transformation**: Data transformations are applied to the booking events in **Azure Data Factory (ADF)**.
   - **Upsert Operation**: The transformed data is upserted into the target table in **Azure Synapse**.

### 3. **Pipeline Workflow:**
   - The entire process is orchestrated and automated using **Azure Data Factory**, which includes automated triggers and dependencies between various steps to ensure smooth execution.
### AirBnB CDC Ingestion PipelineDataFlow
![image](https://github.com/user-attachments/assets/4ea985eb-9a68-489e-801e-81d3a30eb73c)
### AirBnbCdcMain Pipeline
![image](https://github.com/user-attachments/assets/cd94bb49-f94b-4524-9f77-242d7646d6bf)
### LoadBookingFact Pipeline
![image](https://github.com/user-attachments/assets/56b8c002-ddbc-47e8-992e-39ede9bf922d)
### LoadCustomDim Pipeline
![image](https://github.com/user-attachments/assets/ccda1b76-a233-4a79-8a02-cf2448079266)


## Key Features

- **CDC Processing**: Efficient Change Data Capture for both customer and booking data using ADLS and CosmosDB.
- **SCD Type 1 Updates**: Applied to the **Customer Dimension Table** to reflect the latest state of customer data.
- **CosmosDB Change Feeds**: Captures booking data changes in real-time, ensuring up-to-date booking information.
- **Automated Workflow**: Fully automated using ADF pipelines, ensuring timely ingestion and transformation of data.
- **Upsert Operations**: Ensures data consistency in the target tables by performing upserts.
