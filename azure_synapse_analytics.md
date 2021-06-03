---
title: "Azure Synapse Analytics"
tags ["data","azure","dp203"]
---

# Azure Synapse Analytics

- Cloud based integrated platform that brings together:
    - Enterprise data warehousing, now known as SQL Pools
    - Big Data analytics
    - Data integration
    - Visualization

- Supports a range of analytical types:
    - [Descriptive Analytics][descriptive]
        - Leverages the dedicated SQL Pool capability that enables you to create persisted data warehouse
        - Make use of the serverless SQL pool to prepeare data from files sotred in a [datalake][datalake] to create a data warehouse interactivly
    - [Diagnostic Analytics][diagnostic]
        - Use the same serverless SQL pool capability
        - Serverless SQL pools can quickly enable a user to search for additional data that may help them to understand "Why is this happening?" 
    - [Predictive Analytics][predictive]
        - Use Synapse analytics integraged [Apache Spark][spark] engine
        - Synapse spark pools can be used with other services such as Azure Machine Learning services or [Azure Databricks][databricks]
    - [Prescriptive Analytics][prescriptive] 
        - Synapse analytics provides capability through both [Apache Spark][spark] and Azure Synapse Link
        - Integrate streaming technologies such as [Azure Stream Analytics][stream]
        - Use either serverless or dedicated resources at scale
        - Ingest, prepare, manage and serve data using Azure Synapse Pipelines
        - Visualise data in the form o dashboards and reports for immediate analysis using the integrated Power BI

- Process massive amounts of data and answer business questions with limitless scale.

- Uses ELT for bulk data

- Able to pause and resume the compute layer, this means you pay only for the computation you use (useful for Data Warehousing).

- Data Movement Service (DMS) coordinates and transports data between compute nodes.

- Integrate with a wide-variety of technologies, such as:
    - Use data integration pipelines built in [Azure Data Factory][factory] to load data into Synapse Analytics
    - Integrate existing data preparation or Data Science projects held in [Azure Databricks][databricks] 
    - Integrate with many Azure security components to ensure that security and compliance requirements are met
    - Deploy Synapse Workspace and [Azure Data Lake Storage (Gen2)][datalake] accounts during setup
        - [Azure Data Lake Storage][datalake] acts as the primary storage for the workspace

### Azure Synapse SQL

- Distributed query system

- Enables you to implement:
    - Data warehousing
    - Data virtualisation

- Utilises standard T-SQL

- Massively Parallel Processing (MPP).
    - Queries can be quickly run across petabytes of data.
    - Compute nodes can be scaled independently of storage.

- Work with [descriptive][descriptive] and [diagnostic][diagnostic] analytical scenarios 

- Offers both serverless and dedicated resource models

- Dedicated SQL Pools:
    - Offer predictable performance and cost
    - Reserve processing power for data stored in SQL tables

- Serverless SQL Pools:
    - Offer always-available serverless SQL endpoint
    - User for unplanned or ad-hoc workloads

### Apache Spark for Big Data Engineering

- Develop Big Data engineering and machine learning solutions using [Apache Spark][spark] for Azure Synapse

- Take advantage of Big Data computation engine to deal with complex compute transformations that would take too long in a data warehouse

- For machine learning workloads, use SparkML algorithms and AzureML integration for [Apache Spark][spark] 2.4

- Built-in support for Linux Foundation Delta Lake

- Simple model for provisioning and scaling [Spark][spark] clusters to meet compute needs

### Azure Synapse Link

- Enables you to reach out to operational data

- Achieved without impacting the performance of the transactional data store

- Feature needs to be enabled within both Synapse Analytics and the target data store
    - For [Cosmos DB][cosmos], this will create an analytical data store
        - As data changes in the transactional system, the changed data is fed to the analytical store in a [Column][column] store format
        - Azure Synapse Link can query this format with no disruption to the source system

### Distributed tables 

- Hash tables
    - Each row assigned to a specific compute node by a deterministic hash function.
    - Minimises data movement during queries and improves performance.
    - Best for large tables (>2GB) with frequent INSERT, UPDATE and DELETE.

- Round-robin tables
    - Rows distributed evenly across all distributions (at random).
	- More expensive due to more data movement.
    - Best for running fast queries.

- Replicated tables
    - Full copy of the table is replicated.
	- This uses a lot of space.
    - Joins on replicated tables don't require data movement so queries are fast.
    - Best for small table.
    - Use to reduce data movement and improve performance

### Azure Synapse Studio

- Single web UI

- Explore your data estate

- Develop T-SQL scripts and notebooks to interact with analytical engines

- Build data integration pipelines for managing data movement

- Monitor the workloads within the service

- Manage the components of the service

### Creating an Azure Synapse Analytics Workspace

- First you need to deploy an Azure Synapse Analytics workspace

- An Azure Data Lake Storage container is created to act as the primary storage and to store workspace data
    - Workspace data is stored in [Apache Spark][spark] tables
    - [Spark][spark] application logs are stored in the directory: `/synapse/<workspacename>`

- Endpoints are created that can be used to connect to the SQL on-demand services or the Azure Synapse Analytics workspace itself

- Synapse Analytics allows you to create pools, either SQL pools or Spark pools
    - These can be seamlessly mixed and matched to best suit your requirements
        - This is achieved by sharing metadata, enabling the different engines to share databases and tables 

- Resources can be connected to directly from the Synapse Analytics workspace

- Some aspects of the service can be managed in the Azure portal, but best practices is to connect to the Synapse Studio

### Azure Synapse Analytics SQL

- Enables you to implement data warehouse solutions or perform data virtualisation

- A data warehouse is a core component of Business Intelligence (BI) solutions
    - Provides a central repository of data stored in relational tables
    - Facilitates solutions around descriptive analytics
    - Data is retrieved, cleansed and transformed from a range of source data systems
    - Data is served in a structured format commonly referred to as a star schema

- Data in a data warehouse is stored in permanent tables
    - Tables are populated using an extract, transform and load (ETL) process
        - ETL services include Azure Synapse pipelines and [Azure Data Factory][factory]
    - You need to understand the data that is stored in the source systems
        - How it should arrive in the data warehouse
        - How you should cleanse or transform the data

- Data virtualisation allows you to interact with data without understanding how:
    - Data format
    - Data structure
    - Data type

- Virtualisation enables you to explore the data without understanding the technical specifications of the source
    - This allows you to access data in a timely manner, useful for [diagnostic analytics][diagnostic]

- Virtualisation also enables ad-hoc data preparation scenarios
    - Organisation are wanting to unlock insights from their own data stores without setting up a data warehouse
    - You can extract data from a source system and load it into a [Data Lake][datalake] in raw format
    - Transformations may be applied to present the data as required
    - The most complex part of the ETL process is at the end, it means that the access to the data is much quicker 

- Synapse SQL offers both a dedicated and serverless model of the service to meet the demands of both solutions
    - The dedicated model is referred to as dedicated SQL Pools
        - It refers to the data warehousing features that are generally available in Synapse Analytics
        - Dedicated SQL pools represent a collection of analytical resources that are being provisioned when using Synapse SQL
        - Creating dedicated SQL pools
            - Reserves processing power for data permanently stored in SQL tables in a data warehouse
            - Provides predictable performance and cost
    - The serverless models is ideal for unplanned or ad-hoc workloads that the [diagnostic analytics][diagnostic] approach generates
        - Useful for performing data exploration when preparing data for data virtualisation 

### Apache Spark in Azure Synapse Analytics

- Spark pools use the [Apache Spark][spark] system to process large amounts of data in memory

- This capability is achieved via Spark pool clusters
    - Groups of computers treated a single computer which handle the execution of commands

- Clusters allow processing of data to be parallelised across many computers
    - Improves scale and performance

- Clusters consist of a Spark Driver and Worker nodes
    - The Driver node sends work to the Worker nodes
    - The Worker nodes pull data from a specified data source
    - You can configure the number of nodes that are required to perform a task

- Spark pools in Synapse Analytics offer a fully managed service, benefits include
    - Speed and efficiency
        - Spark instances start in approx. 2mins for fewer than 60 nodes or approx. 5mins for more than 60 nodes
        - The instance shuts down by default 5mins after the last job executed unless it is kept alive by an active connection
    - Ease of creation
        - You can create a new Spark pool in Synapse Analytics using:
            - Azure portal
            - Azure Powershell
            - Synapse Analytics .NET API
    - Ease of use
    - Scalability
        - Can have auto-scale enabled so that pools scale by adding or removing nodes as needed
        - Spark pools can be shut down with no data loss as data is stored in [Azure Storage][storage] or [Data Lake Storage][datalake]
    - Support for [Azure Data Lake Storage (Gen2)][datalake]
        - Spark pools can use [Azure Data Lake Storage (Gen2)][datalake] as well as [Blob Storage][blob]

- Use Spark pools to process data too big to be handled by SQL pools

- If you already have a Spark implementation, such as [Azure Databricks][databricks], Synapse Analytics can be integrated

- Spark pools comes with Anaconda libraries pre-installed
    - Anaconda provides close to 200 libraries that enable you to use the spark pool for:
        - Machine learning
        - Data analysis
        - Data visualisation

### Orchestrate data integration with Azure Synapse Pipelines

- Azure Synapse Pipelines is the cloud-based ETL and data integration service
    - Allows you to create data-driven workflows for:
        - Orchestrating data movement
        - Transforming data at scale
    - Create and schedule pipelines that can ingest data from disparate data stores
    - Build complex ETL or ELT processes that transform data visually using:
        - Data flows
        - Compute services such as:
            - HDInsight
            - Azure Databricks
            - Azure Synapse Analytics

- Synapse Pipelines allow you to integrated data pipelines between:
    - SQL Pools
    - Spark pools
    - SQL Serverless


- Much of the functionality of Synapse Pipelines comes from the Azure Data Factory feature
    - Like Data Factory, Synapse pipelines consist of four core components
        - Linked Service
            - An object that enables connection to a wide variety of data sources
            - Data can be ingested from the data source in readiness to prepare the data fro transformation or analysis
            - Additionally, can fire up compute services on-demand
                - For example, a HDInsight cluster for the purpose of processing data through a Hive query
        - Data Set
            - Objects which represent the data structures within the data store that is referenced by the Linked Service object
            - Can also be used by an object known as an Activity
        - Activity
            - Object which typically contains transformation logic or the analysis commands
            - Includes the Copy Activity
                - Used to ingest data from a variety of data sources
            - Includes the Mapping Data Flow
                - Perform code-free data transformations
            - For transforming data, Also includes
                - Execution of a stored procedure
                - Hive Query
                - Pig script
            - You can push data into a machine learning model to perform analysis
            - Not uncommon for multiple activities, for example:
                - Transform data using SQL pool stored procedure
                - Perform analytics in Databricks
        - Pipeline
            - Object which logically groups together multiple activities
            - Activities can be scheduled or triggered
            - There are different triggers for different types of event:
                - Control flow
                    - Orchestration of pipeline activities that include:
                    - Chaining activities in a sequence 
                    - Branching
                    - Defining parameters at the pipeline level
                    - Passing arguments while invoking the pipeline on-demand from a trigger
                    - Custom-state passing and looping containers
                    - For-each iterators
                - Parameters
                    - Key-value pairs of read-only configuration
                    - Defined in the pipeline
                    - Arguments for the defined parameter are passed during execution from:
                        - The run context that was created by a trigger
                        - A pipeline that was executed manually
                    - Activities within the pipeline consume parameter values

- Synapse Pipelines have an integration-runtime
    - Enables pipeline to bridge between the activity and linked services objects
    - Referenced by linked service
    - Provides the compute environment where the activity either runs on or gets despatched from
        - Allows the activity can be performed in the region closes possible
    - There are three types of integration-runtime:
        - Azure
        - Self-hosted
        - Azure Data Factory

### Hybrid Transactional/Analytical Processing

- HTAP

- Enables businesses to perform analytics over a transactional database system without impacting performance
    - Enables organisations to use a database to:
        - Fulfill both transactional and analytical needs
        - Support near real-time analysis of operational data

- Azure Synapse Link connects [Azure Cosmos DB][cosmos] with Synapse Analytics for HTAP architecture
    - This integration:
        - Eliminates ETL
        - Provides self-service capabilities to users of the data

[descriptive]: ./descriptive_analytics.md
[diagnostic]: ./diagnostic_analytics.md
[predictive]: ./predictive_analytics.md
[prescriptive]: ./prescriptive_analytics
[datalake]: ./azure_datalake.md
[spark]: ./apache_spark.md
[databricks]: ./azure_databricks.md
[stream]: ./azure_stream_analytics.md
[cosmos]: ./azure_cosmos_db.md
[column]: ./columnar_data_model.md
[factory]: ./azure_data_factory.md
[storage]: ./azure_storage.md
[blob]: ./azure_blob_storage.md
