---
title: "Azure Stream Analytics"
tags: ["data","azure","dp203"]
---

# Azure Stream Analytics

- Data streams are continuous event data broadcast from:
    - Applications.
    - Sensors.
    - Monitoring devices.
    - Gateways.

- Azure Stream Analtyics is used to processing data streams in real-time.

- Inputs include:
    - [IoT Hub][iot]
    - [Event Hub][event]
    - [Blob storage][blob] (batch only)

- Route job output to many storage systems:
    - [Blob storage][blob].
    - [SQL Database][sqldb].
    - [Data Lake Storage][datalake].
    - [Cosmos DB][cosmosdb].

- Run batch analytics in [HDInsight][hdinsight] or send output to [Event Hubs][event] for consumption.

- Use [PowerBI][powerbi] streaming API for real-time visualisation.

- Data is encrypted in transit, but is generally discarded after the windowing operations finish.
    - Unless transfered to a storage device, encryption is then handled by the device.

# Windowing

- Allows functions to be run on sets of streaming data

- Four kinds of windowing supported:
    - [Sliding][sliding]
    - [Tumbling][tumbling]
    - [Hopping][hopping]
    - [Session][session]

[iot]: ./azure_iot_hub.md
[event]: ./azure_event_hub.md
[blob]: ./azure_blob_storage.md
[sqldb]: ./azure_sql_database.md
[datalake]: ./azure_datalake.md
[cosmosdb]: ./azure_cosmos_db.md
[hdinsight]: ./azure_hdinsight.md
[powerbi]: ./azure_powerbi.md
[sliding]: ./sliding_window.md
[tumbling]: ./tumbling_window.md
[hopping]: ./hopping_window.md
[session]: ./session_window.md
