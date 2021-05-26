---
title: "Azure Cosmos DB"
tags: ["data","azure","dp203"]
---

# Azure Cosmos DB

- [NoSQL database][nosql]

- Multimodal; Can be deployed using several API models:
    - [SQL API][sql] (Core)
    - [MongoDB API][mongo]
    - [Cassandra API][cassandra]
    - [Gremlin API][gremlin]
    - [Table API][table]

- Globally distributed

- Use when you require a [NoSQL database][nosql]:
    - of the supported API model
    - is highly scalable
    - has low-latency
    - has quick response times (less than 10ms)
    - has high availability (99.999% uptime)

- Commonly used for:
    - IOT
    - Marketing
    - Web
    - Mobile

## Consistency

- Cosmos DB offers five consistency (the ability for the data to be read once it's written) levels:
    - Strong
        - High consistency
        - High latency __is this right?__
        - High cost
        - Suited for transactional databases
    - Bounded staleness
        - Eventual consistency with set performance (specified lag)
            - Seconds (ie, 10 seconds behind)
            - Operations (ie, 10 operations behind)
    - Session
        - Default
        - Moderate consistency/latency
        - Half the cost of Strong
    - Consistent prefix
    - Eventual
        - Low consistency
        - Low latency __is this right?__
        - Low cost
        - Suited for analytics databases

[nosql]: ./nonrelational_database.md
[sql]: ./azure_core_api.md
[mongo]: ./azure_mongo_api.md
[cassandra]: ./azure_cassandra_api.md
[gremlin]: ./azure_gremlin_api.md
[table]: ./azure_table_api.md
