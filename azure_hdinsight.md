---
title: "Azure HDInsight"
tags: ["data","azure","dp203"]
---

# Azure HDInsight

- A collection of technologies for ingest, process and analysis of big data.

- Supports:
    - Batch processing
    - Data warehousing
    - IoT
    - Data Science

- The technology stack consists of:
    - [Apache Hadoop][hadoop]
        - [Apache Spark][spark]
        - [Apache Kafka][kafka]
        - [Apache Hbase][hbase]
    - [Apache Storm][storm]
    - Interactive Query

- Uses [Hive][hive]:
    - Ingest data
    - Run ETL operations

- [Hive][hive] queries can be orchestrated with [Azure Data Factory][factory]

[hadoop]: ./azure_hadoop.md
[spark]: ./apache_spark.md
[kafka]: ./apache_kafka.md
[hbase]: ./apache_hbase.md
[storm]: ./apache_storm.md
[factory]: ./azure_data_factory
