# Cab-sharing-ETL-pipeline

The problem statement is to capture clickstream data from Kafka, load it into Hadoop using a stream processing framework, ingest booking data from AWS RDS to Hadoop, and create Hive tables for both datasets. Aggregates may need to be prepared by reading data from HDFS, processing it with Spark, and writing the results back to HDFS as a Hive table. The Hive tables serve as the final consumption tables for stakeholders to query and gain insights from the data.
