---
title: "Azure Synapse Analytics"
tags ["data","azure","dp203"]
---

# Azure Synapse Analytics

- Cloud based platform that brings together:
    - Enterprise data warehousing, now known as SQL Pools
    - Big Data analytics.

- Process massive amounts of data and answer business questions with limitless scale.

- SQL Pools is Massively Parallel Processing (MPP).
    - Queries can be quickly run across petabytes of data.
    - Compute nodes can be scaled independently of storage.

- Data Movement Service (DMS) coordinates and transports data between compute nodes.

- Use replicated tabes to reduce data movement and improve performance.

- Supports three types of distributed tables:
    - Hash
        - Each row assigned to a specific compute node by a deterministic hash function.
	- Minimises data movement during quries and improves performance.
	- Best for large tables (>2GB) with frequent INSERT, UPDATE and DELETE.
    - Round-robin
        - Rows distributed evenly across all distributions (at random).
	    - More expensive due to more data movement.
	- Best for running fast queries.
    - Replicated
        - Full copy of the table is replicated.
	    - This uses a lot of space.
	- Joins on replicated tables don't require data movement so quries are fast.
	- Best for small table.

- Uses ELT for bulk data

- Able to pause and resume the compute layer, this means you pay only for the computation you use (useful for Data Warehousing).
