# Cockpit dashboard for manufacturing plant
[![Python Package using Conda](https://github.com/ANGELOANTU7/nest-data-hackathon/actions/workflows/python-package-conda.yml/badge.svg?branch=master)](https://github.com/ANGELOANTU7/nest-data-hackathon/actions/workflows/python-package-conda.yml)

## Problem Statement
As a manufacturing plant for ABC corporation operating at Kerala, we are trying to implement a cockpit dashboard which collects data from various systems connected to the manufacturing plat to get a good visibility of what is going on in the plant on a day-to-day basis. As a start we want to address two use cases mentioned below :

1. Our MES(Manufacturing Execution System) generates lot of data in different formats and it needs to be collected, cleaned, processed and reports need to be generated from it. This is currently made available in AWS S3 buckets as daily data dumps and the can be consumed by the data processing applications.
2. We have IoT enabled temperature sensors placed in machineries to collect temperature values at regular intervals. This data is continuously streamed to a message bus (Kafka) in JSON format. This data also needs to be collected and made available for real-time reporting dashboard to continuously monitor real-time temperature variations of respective components.

## Objective
The objective of the project is to develop a cockpit dashboard that can collect data from various systems connected to the manufacturing plant, clean and process the data, and generate real-time and historical reports. The dashboard provides a comprehensive view of the plant's operations, including machine utilization, production rates, quality control metrics, and real-time temperature variations of machinery components.

## Scope
The scope of this project includes the development of a cockpit dashboard that can collect and process data from the MES and IoT-enabled temperature sensors. The dashboard displays real-time and historical data in a user-friendly format and provide alerts and notifications for any anomalies or issues detected. Additionally, the project scope includes the development of data pipelines to collect, clean and process the data from different sources.

## Data Sources
1. Manufacturing Execution System (MES) data is available in AWS S3 buckets as daily data dumps in different formats such as Parquet, CSV, and JSON.

2. IoT enabled temperature sensor data is continuously streamed to a message bus (Kafka) in JSON format.

## Medallion Architecture
A medallion architecture is a data design pattern used to logically organise data in a lake house, with the goal of incrementally and progressively improving the structure and quality of data as it flows through each layer of the architecture (from Bronze ⇒ Silver ⇒ Gold layer tables). Medallion architectures are sometimes also referred to as "multi-hop" architectures.



### Data Sources Layer
This layer includes all the raw data that is ingested into the data lake. This can include data from various sources such as databases, APIs, and file systems.

### Ingestion Layer
This layer includes all the processes and tools used to ingest data from the various sources into the data lake. This can include data extraction, data validation, and data transformation.

### Meta Data Layer
This layer includes all the information about the data in the data lake. This can include information about the data structure, data lineage, and data quality.

### Processing Layer
This layer includes all the processes and tools used to transform and analyze the data in the data lake. This can include data cleaning, data integration, and data modeling.

### Service Layer
This layer is responsible for providing an API for external systems to access the processed data and perform various operations on it such as querying and visualizing the data.

## Technologies used

This project utilizes a variety of technologies to collect, process, and analyze data from manufacturing systems. These include:

### PySpark
PySpark is an open-source library for Python that allows for data processing and analysis using the Spark framework. It allows for the handling of large datasets and the ability to perform complex data operations.
### DataLake
A data lake is a centralized repository that allows for the storage of raw, unstructured data at any scale. It provides a single source of truth for all data in the manufacturing plant.
### Databricks
Databricks is a cloud-based platform for data engineering, machine learning, and analytics. It allows for the creation of data pipelines and the ability to run PySpark scripts.
### PowerBI
Power BI is a business intelligence tool that allows for the creation of interactive visualizations and reports. It allows for the representation of data in a user-friendly format.

![power_bi](https://ibb.co/xF383Vt)

### Kafka
Kafka is an open-source message broker that allows for the real-time processing of data streams. It allows for the integration of data from various sources in real-time.
### Python
Python is a programming language that is used for data processing and analysis. It allows for the creation of scripts and the ability to work with various libraries such as PySpark and Pandas.



