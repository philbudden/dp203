---
title: "Azure Hadoop"
tags: ["data","azure","dp203"]
---

# Azure Hadoop

- Azure implementation of the open-source [hadoop][hadoop] framework

- The technology stack includes:
    - [Apache Hive][hive]
    - [Apache HBase][hbase]
    - [Apache Spark][spark]
    - [Apache Kafka][kafka]

- [Hadoop][hadoop] stores data in a file system ([HDFS][hdfs]) and [Spark][spark] stores data in memory. This makes Spark about 100x faster

- Uses Java and Python to process big data

- Mapper consumes and analzes input data and emits tuples that can be analyzed by Reducer

- Reducer runs summary operations to create a samller combined result set

[hadoop]: ./apache_hadoop.md
[hbase]: ./apache_hbase.md
[spark]: ./apache_spark.md
[kafka]: ./apache_kafka.md
[hdfs]: ./hdfs.md
