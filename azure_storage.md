---
title: "Azure Storage"
tags: ["data","azure","dp203"]
---

# Azure Storage

- Azure storage accounts are the base storage type within Azure.

- Azure storage can:
    - Offer scalable object store for data objects and file system services in the cloud.
    - Provide a messaging store for reliable messaging.
    - Act as a [NoSQL store][nosql].

- There are four configuration options for Azure storage accounts:
    - [Azure Blob][blob]
    - [Azure Files][files]
    - [Azure Queue][queue]
    - [Azure Table][table]

- Azure storage can be provisioned for stand-alone use, or as the storage basis for a data platform such as:
    - [Azure Data Lake][datalake]
    - [HDInsight][hdinsight]

## Azure storage overview

|Storage Type|Key Features|Data Ingestion|Queries|Data Security|
|------------|------------|--------------|-------|-------------|
|[Azure Blob][blob]|Cheap|[Azure Data Factory][factory], [Storage Explorer][storageexplorer], [AzCopy tool][azcopy], [Powershell][powershell], [Visual Studio][visualstudio]|Not supported|[Encryption at Rest][encryption], [RBAC][rbac]|
|[Azure Data Lake][datalake]|Hierarchical namespace, Unlimited size and scalability, Geo redundant storage |[Azure Data Factory][factory], [Apache Sqoop][sqoop], [Storage Explorer][storageexplorer], [AzCopy tool][azcopy], [Powershell][powershell], [Visual Studio][visualstudio]|Azure Blob Storage API, Azure Data Lake System API|[Encryption at rest][encryption], [Active Directory][activedirectory], [RBAC][rbac], Firewall|

[nosql]: ./nonrelational_database.md
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
