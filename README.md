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

<img src="https://iili.io/HYD8giN.md.png" alt="HYD8giN.md.png" height=30% width=80% border="0">

### Data Sources Layer
This contains a txt file with links to all the s3 buckets

### Ingestion Layer
Consists of the code that takes data from the s3 buckets and saves them as csvs in the storage layer. The 3 jupyter notebook files correspond to the conversion of parquets, csvs, and txts in the s3 buckets to csvs in the local file system.

### Meta Data Layer
Consists of the final tables formed after processing. The 2 files correspond to the operation management and supply chain final tables.

### Processing Layer
Processing refers to the merging and filtering of the several tables in the storage layer to a single table that contains all our necessary data. These files are located in the meta data layer.
Processing also contains the code for the creation of the reports. These are created from the tables in the meta data layer and saved in the serving layer.
As temperature data is live streamed, the data is obtained through kafka services and the reports are generated as it recieves data almost instantly (less than a second) published to a PubNub channel in the form of a dictionary containing all the values to be visualised.

### Service Layer
The reports generated are located here. 4 reports corresponding to the supply chain and 2 corresponding to operation management. The temperture data can be viewed through Power BI dashboard by subscribing to the PubNub channel mentioned in the temperature processing code in the processing layer. Unfortunately we cannot share our Power BI dashboard as it is limited to Pro users. So a reference image has been provided. Clicking on the link will redirect you to a video that shows the live changes.

## Technologies used

This project utilizes a variety of technologies to collect, process, and analyze data from manufacturing systems. These include:

### PySpark
PySpark is an open-source library for Python that allows for data processing and analysis using the Spark framework. It allows for the handling of large datasets and the ability to perform complex data operations.
### DataLake
A data lake is a centralized repository that allows for the storage of raw, unstructured data at any scale. It provides a single source of truth for all data in the manufacturing plant.
### PowerBI
Power BI is a business intelligence tool that allows for the creation of interactive visualizations and reports. It allows for the representation of data in a user-friendly format.



<img src="https://iili.io/HYDszNt.md.jpg" href="https://www.kapwing.com/videos/63c436e4afa29a01f82db53b" width=700 alt="HYD8giN.md.png">

### Kafka
Kafka is an open-source message broker that allows for the real-time processing of data streams. It allows for the integration of data from various sources in real-time.
### Python
Python is a programming language that is used for data processing and analysis. It allows for the creation of scripts and the ability to work with various libraries such as PySpark and Pandas.

###Changes to be implemented in the future

1. As the s3 buckets are updated daily, the extraction and processing can be scheduled to run periodically using azure databricks and the csv can be stored in the blob storage. This can help provide easy access to visualization of the 2 reports as we are already making use of Power BI to view temperature analytics.

