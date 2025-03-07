# Bookings Data Pipeline using Kafka, Hadoop, Sqoop & Hive

## Overview
This project involves building a scalable, real-time data pipeline that ingests clickstream events and booking data, processes it, and stores it efficiently in a Hadoop ecosystem. The pipeline uses various tools, including Kafka for data streaming, Hadoop for distributed storage, Sqoop for data migration, and Hive for data analysis. The solution ensures high reliability, data accessibility, and improved query performance.

## Key Features
- **Real-Time Data Ingestion**: Ingests 100K+ clickstream events per hour from Kafka into Hadoop with 99.9% reliability using Spark Streaming.
- **Efficient Data Migration**: Migrates 5M+ records from AWS RDS to Hadoop using Sqoop, optimising data ingestion time by 40%.
- **Optimised Query Performance**: Implements Hive tables to analyse 1M+ daily bookings, reducing report generation time by 50%.
- **Automated Data Aggregation**: Uses PySpark for ETL processing, reducing manual processing time by 60% and improving business intelligence accessibility.

## Tools & Technologies Used
- **Kafka**: Real-time data streaming for clickstream events.
- **Spark Streaming**: To ingest and process real-time data.
- **Hadoop**: Distributed storage system for managing large-scale data.
- **Sqoop**: Tool for migrating data from AWS RDS to Hadoop.
- **Hive**: Data warehousing solution for SQL-like querying and analysis.
- **PySpark**: Used for the ETL process to aggregate and process data.

## Setup Instructions

### Prerequisites
- Java 8 or higher
- Apache Kafka
- Hadoop 3.x or later
- Apache Hive 2.x or later
- Apache Sqoop 1.4.x
- Python 3.x
- PySpark
- AWS RDS for data source (optional)

### 1. Clone the repository
```bash
git clone <repository_url>
cd bookings-data-pipeline
```

### 2. Install dependencies
- Set up a Kafka cluster for real-time data streaming.
- Configure Hadoop and Hive on your system.
- Install PySpark using pip:
  ```bash
  pip install pyspark
  ```

### 3. Kafka Configuration
- Configure Kafka for streaming clickstream events.
- Create Kafka topics to ingest events and bookings data.

### 4. Sqoop Configuration for Data Migration
- Use Sqoop to migrate records from AWS RDS to Hadoop.
  Example:
  ```bash
  sqoop import --connect jdbc:mysql://<aws_rds_host>:3306/bookings_db --username <username> --password <password> --table bookings --target-dir /path/to/hadoop/directory --num-mappers 4
  ```

### 5. Hive Table Setup
- Create Hive tables to store and query booking data:
  Example:
  ```sql
  CREATE TABLE bookings (
    booking_id INT,
    user_id INT,
    timestamp STRING,
    amount DECIMAL(10,2)
  ) STORED AS ORC;
  ```

### 6. PySpark ETL Process
- Use the provided PySpark script to aggregate booking data and perform ETL processing. It will reduce manual processing time and improve data accessibility.

### 7. Running the Spark Streaming Job
- Submit the Spark Streaming job to process the incoming Kafka events:
  ```bash
  spark-submit --class <MainClass> --master yarn <path_to_your_jar>
  ```

## Results
- **Clickstream Event Ingestion**: 100K+ events ingested per hour with 99.9% reliability.
- **Data Migration**: 5M+ records migrated from AWS RDS to Hadoop with 40% improvement in ingestion time.
- **Query Optimization**: Improved query performance by 30% and reduced report generation time by 50%.
- **ETL Automation**: Reduced manual processing time by 60% using PySpark-based aggregation.

## Future Enhancements
- Integrate machine learning models for predictive analytics on booking trends.
- Implement more efficient partitioning strategies in Hive for faster query processing.
- Scale the pipeline to handle more than 1M daily bookings.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements
- Special thanks to the developers of Apache Kafka, Hadoop, Sqoop, and Hive for providing the tools used in this project.
```

This `README.md` provides a clear, concise explanation of the project, how to set it up, and the outcomes. You can adjust the setup instructions and any other details based on your actual project configuration and deployment.
