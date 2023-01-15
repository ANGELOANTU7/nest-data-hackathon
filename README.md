# Cockpit dashboard for manufacturing plant
[![Python Package using Conda](https://github.com/ANGELOANTU7/nest-data-hackathon/actions/workflows/python-package-conda.yml/badge.svg?branch=master)](https://github.com/ANGELOANTU7/nest-data-hackathon/actions/workflows/python-package-conda.yml)

## Objective:
The objective of the project is to develop a cockpit dashboard that can collect data from various systems connected to the manufacturing plant, clean and process the data, and generate real-time and historical reports. The dashboard provides a comprehensive view of the plant's operations, including machine utilization, production rates, quality control metrics, and real-time temperature variations of machinery components.

## Scope:
The scope of this project includes the development of a cockpit dashboard that can collect and process data from the MES and IoT-enabled temperature sensors. The dashboard displays real-time and historical data in a user-friendly format and provide alerts and notifications for any anomalies or issues detected. Additionally, the project scope includes the development of data pipelines to collect, clean and process the data from different sources.

## Data Sources:
1. Manufacturing Execution System (MES) data is available in AWS S3 buckets as daily data dumps in different formats such as Parquet, CSV, and JSON.

2. IoT enabled temperature sensor data is continuously streamed to a message bus (Kafka) in JSON format.

## Architecture:

The project will be implemented using a data lakehouse architecture, which combines the best features of both data warehousing and data lakes to provide a centralized platform for storing, processing, and analyzing large amounts of structured and unstructured data.

### Data Sources Layer:
This layer includes all the raw data that is ingested into the data lake. This can include data from various sources such as databases, APIs, and file systems.

### Ingestion Layer:
This layer includes all the processes and tools used to ingest data from the various sources into the data lake. This can include data extraction, data validation, and data transformation.

### Meta Data Layer:
This layer includes all the information about the data in the data lake. This can include information about the data structure, data lineage, and data quality.

### Processing Layer:
This layer includes all the processes and tools used to transform and analyze the data in the data lake. This can include data cleaning, data integration, and data modeling.

### Service Layer:
This layer is responsible for providing an API for external systems to access the processed data and perform various operations on it such as querying and visualizing the data.

## Technologies used

This project utilizes a variety of technologies to collect, process, and analyze data from manufacturing systems. These include:

### PySpark:
PySpark is an open-source library for Python that allows for data processing and analysis using the Spark framework. It allows for the handling of large datasets and the ability to perform complex data operations.
### DataLake:
A data lake is a centralized repository that allows for the storage of raw, unstructured data at any scale. It provides a single source of truth for all data in the manufacturing plant.
### Databricks:
Databricks is a cloud-based platform for data engineering, machine learning, and analytics. It allows for the creation of data pipelines and the ability to run PySpark scripts.
### PowerBI:
Power BI is a business intelligence tool that allows for the creation of interactive visualizations and reports. It allows for the representation of data in a user-friendly format.
### Kafka:
Kafka is an open-source message broker that allows for the real-time processing of data streams. It allows for the integration of data from various sources in real-time.
### Python:
Python is a programming language that is used for data processing and analysis. It allows for the creation of scripts and the ability to work with various libraries such as PySpark and Pandas.



