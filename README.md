# RealTime_Data_Streaming_Pipeline_Kafka_S3_Athena

## Project Overview: 
This project builds a real-time data streaming pipeline using AWS services. Kafka producers send high-throughput data streams, while Kafka consumers process and push the data to S3 for storage. EC2 hosts the Kafka brokers and consumer applications. AWS Glue Crawlers infer the schema of the data in S3 and populate the Glue Data Catalog. Athena is used to query the data directly from S3 for efficient, serverless SQL-based analysis.

## Key Features:

**Real-Time Data Streaming with Kafka on EC2:** Kafka producers send real-time data, and Kafka consumers process it. Kafka is hosted on EC2 instances to handle the high-throughput data streams, ensuring smooth and continuous data flow.

**Data Storage in S3:** Processed data from Kafka is stored in Amazon S3, which is cost-effective and easily accessible for further processing or analysis.

**Automatic Schema Detection with Glue:** AWS Glue Crawlers automatically detect the structure of data stored in S3, eliminating the need to manually define schemas.

**Easy Data Querying with Athena:** Athena allows you to run SQL queries directly on the data stored in S3, enabling fast analysis without managing infrastructure.

## Architecture:
![project architecture](kafka_ETL_data.jpg)

## Technology Used:
1.Programming Language - Python

2.Amazon Web Service (AWS)

3.S3 (Simple Storage Service)

4.Athena

5.Glue Crawler

6.Glue Catalog

7.EC2

8.Apache Kafka

## Steps to Set Up:

### 1.Launch EC2 Instance and Set up Apache Kafka:

-Create EC2 Instance And Start the EC2 Instance.

-Connect Via SSH Client.

-Follow The Steps and Command According to **command_kafka.txt** for setup Kafka and to create Producer And Consumer.

### 2.Create Python Script to Create kakfa Producer and Consumer and Stream The Data form Dataset In Loop:

-Create 2 Python Note books **kafka_producer.ipynb** & **kafka_consumer.ipynb**

-In this python notebooks we create producer and consumer which produce the data form dataset in loop with delay of 1 sec to get real time data flow replica and consumer counsumes data in json format and pass to s3 bucket

### 3.Create S3 Bucket,Crawler,Data Catalog:

-To Store the Data in RealTime Create S3 Bucket and In **kafka_consumer.ipynb** give path to consumer of s3 bucket to save the data.

-Create glue Crawler and give Name to it and set data source of our s3 bucket And start The Crawler.

-Once Crawler stop and get Successed Meassage the our table  is created in Database.

-Go to athena open query editor andunder database you get table and you can see the real time data and now we can run query on that data and do analysis.
