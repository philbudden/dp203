---
title: "Azure Blob Storage"
tags: ["data","azure","dp203"]
---

# Azure Blob Storage

- Azure Blob storage is a configuration option for [Azure storage accounts][storage].

- Use Blob storage to provision a data store that will store, but not query your data.

- Blob storage works well with unstructured data, especially images.

- Blob storage is the cheapest way to store data in Azure.

- There are three access tiers which manage the data lifecycle in Azure Blob Storage:
    - Hot
        - Best for frequently used-data
        - Low read and write cost
        - High storage cost
    - Cool
        - Best for data accessed in increments of >30 days
        - Often used for short-term backup adn disaster recovery
        - Double the read and write cost of the Hot tier
        - Half the storage cost of the Hot tier
    - Archive
        - Best for data not accessed for >180 days
        - Often used for compliance and regulatory purposes
        - Extremly affordable as long as the data isn't being moved

[storage]: ./azure_storage.md
