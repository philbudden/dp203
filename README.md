# DP203 Certification

My notes for the DP-203: Data Engineering on Microsoft Azure certification

## Key services overview 

|Storage Type|Key Features|Data Ingestion|Queries|Data Security|
|------------|------------|--------------|-------|-------------|
|[Azure Blob][blob]|Cheap|[Azure Data Factory][factory], [Storage Explorer][storageexplorer], [AzCopy tool][azcopy], [Powershell][powershell], [Visual Studio][visualstudio]|Not supported|[Encryption at Rest][encryption], [RBAC][rbac]|
|[Azure Data Lake][datalake]|Hierarchical namespace, Unlimited size and scalability, Geo redundant storage |[Azure Data Factory][factory], [Apache Sqoop][sqoop], [Storage Explorer][storageexplorer], [AzCopy tool][azcopy], [Powershell][powershell], [Visual Studio][visualstudio]|Azure Blob Storage API, Azure Data Lake System API|[Encryption at rest][encryption], [Active Directory][activedirectory], [RBAC][rbac], Firewall|
|[Azure Cosmos DB][cosmosdb]|Multimodal, Globally distributed, Highly available|[Azure Data Factory][factory], JSON document upload, Direct document editing|Stored procedures, Triggers, User-defined functions (UDFs), JavaScript query API, [Data Explorer][explorer]|[Encryption at rest and in transit][encryption], Firewall, Access from Virtual Networks, Token authentication, [RBAC][rbac]|
|[Azure SQL Database][sqldb]|Dynamically scaling, OLTP |SDKs, T-SQL, [Azure Data Factory][factory]|T-SQL|[Encryption at rest][encryption], Advanced Threat Protection, SQL Database auditing, [Active Directory][activedirectory], Multifactor Authentication, Compliance certification|
|[Azure Synapse Analytics][synapse]|Massively Parallel Processing, Only pay for computation you use|[Polybase][polybase], bcp, SQLBulkCopy API|T-SQL|SQL Server Authentication, Multifactor Authentication| 
|[Azure Stream Analytics][stream]| |[IoT Hub][iothub], [Event Hub][eventhub], [Blob Storage][blob]|Stream Analytics query language|[Encrypted in transit][encryption]|
|[Azure HDInsight][hdinsight]|[Hadoop][hadoop], [Spark][spark], [HBase][hbase], [Storm][storm], [Interactive Query][interactivequery]|[Hive][hive], [Azure Data Factory][factory]|[Pig][pig], [HiveQL][hive], [SparkSQL][spark]|[Encryption][encryption], Secure Shell, Shared Access Signatures, [Active Directory][azure_active_dirctory]|
|[Databricks][databricks]|Fully managed [Spark][spark] clusters, interactive workspace| |R, Python, Scala, SQL|[Active Directory][azure_active_directory], Databricks Enterprise-grade security|

[blob]: ./azure_blob_storage.md
[files]: ./azure_files.md
[queue]: ./azure_queue.md
[table]: ./azure_table.md
[datalake]: ./azure_datalake.md
[hdinsight]: ./azure_hdinsight.md
[factory]: ./azure_data_factory.md
[storageexplorer]: ./azure_storage_explorer.md
[azcopy]: ./azure_azcopy.md
[powershell]: ./powershell.md
[visualstudio]: ./visualstudio.md
[encryption]: ./azure_encryption.md
[rbac]: ./rbac.md
[sqoop]: ./azure_sqoop.md
[activedirectory]: ./azure_active_directory.md
[cosmosdb]: ./azure_cosmos_db.md
[explorer]: ./azure_data_explorer.md
[sqldb]: ./azure_sql_database.md
[synapse]: ./azure_synapse_analytics.md
[polybase]: ./azure_polybase.md
[stream]: ./azure_stream_analytics.md
[iothub]: ./azure_iot_hub.md
[eventhub]: ./azure_event_hub.md
[hadoop]: ./azure_hadoop.md
[spark]: ./apache_spark.md
[hbase]: ./apache_hbase.md
[storm]: ./apache_storm.md
[interactivequery]: 
[pig]: 
[hive]: ./hadoop_hive.md
[databricks]: ./azure_databricks.md
