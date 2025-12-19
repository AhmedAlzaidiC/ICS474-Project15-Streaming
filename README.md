# ICS 474 – Real-Time Streaming Data Pipeline (Project 15)

## Team Members
- Rashed Alghamdi
- Ahmed Alzaidi
- Ahmed Al Zuabi

## Project Overview
This project demonstrates an end-to-end real-time data streaming pipeline using modern big data technologies. The system ingests streaming data, processes it in real time, stores the processed data, and provides monitoring and visualization of the pipeline execution.

The pipeline integrates Apache Kafka for messaging, Spark Structured Streaming for processing, Apache Cassandra for storage, and Apache Airflow for orchestration. The entire system is containerized using Docker and Docker Compose.

## Original Project Source
This project is based on and adapted from the following open-source repository:

https://github.com/supakunz/Streaming-Data-Pipeline

Modifications and adaptations were made to support deployment, execution, configuration, and documentation requirements for the ICS 474 course project.

## System Architecture
The architecture of the system follows a real-time streaming workflow:

- Data events are generated and published to Kafka topics
- Spark Structured Streaming consumes the Kafka streams and processes the data
- Processed data is written to Cassandra for scalable storage
- Apache Airflow orchestrates and schedules the streaming jobs
- Monitoring and visualization are provided using Kafka Control Center and Spark Web UI

## Technology Stack

### Programming Languages
- Python
- SQL

### Streaming, Processing, and Orchestration
- Apache Kafka
- Apache Spark Structured Streaming
- Apache Airflow

### Storage and Infrastructure
- Apache Cassandra
- Docker
- Docker Compose

### Visualization and Monitoring
- Confluent Control Center (Kafka monitoring)
- Spark Web UI (job execution and cluster monitoring)

## Dockerized Services
The system is deployed using Docker Compose and includes the following services:

- Zookeeper
- Kafka Broker
- Schema Registry
- Confluent Control Center
- Apache Airflow (Webserver, Scheduler, PostgreSQL)
- Spark Master and Spark Worker
- Apache Cassandra
- Jupyter (supporting environment)
- Kafka Producer

## Data Ingestion
A Kafka producer continuously generates real-time events and publishes them to Kafka topics. These events are consumed by Spark Structured Streaming for processing. Kafka Control Center is used to monitor topic activity, message production, and consumption rates.

## Streaming Processing and Storage
Spark Structured Streaming processes incoming Kafka events, applies transformations, and writes the processed data into Cassandra tables. Cassandra provides scalable and fault-tolerant storage for the streaming output.

## Workflow Orchestration
Apache Airflow orchestrates the pipeline using a DAG named `spark_streaming_dag`. The DAG triggers the Spark streaming job, monitors execution, and ensures controlled scheduling and execution of tasks.

## Monitoring and Visualization
- Kafka message flow, topic health, and throughput are monitored using Confluent Control Center
- Spark job execution and cluster health are monitored using Spark Web UI
- Airflow provides execution history and task status monitoring

## Setup and Execution

### 1. Clone the repository
```bash
git clone https://github.com/supakunz/Streaming-Data-Pipeline.git
