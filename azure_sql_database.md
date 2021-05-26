---
title: "Azure SQL Database"
tags: ["data","azure","dp203"]
---

# Azure SQL Database

- Managed [relational Database][relationaldb] service based on [SQL Server][sqlserver].

- Dynamic scaling on demand
    - [Scale Up (Vertical)][scaling]
        - Two modes of scaling:
            - DTUs
                - Database Transaction Units.
                - Platform takes care of fine-tuning.
            - vCore
                - Virtual Cores.
                - More complex than DTUs.
                - Choose from 2 to 80 vCores.
     - [Scale Out (Horizontal)][scaling]
         - Load balance with read-only workloads.
         - Default for premium and business critical service tiers.
         - Availalbve in Hyperscale with secondary replica creation.
     - Elastic Pools
         - Designed for unpredictable demands
         - Shared pool resources to mange and scales multiple databases
         - Two pricing options:
             - DTUs
             - vCores
     - __Note:__ <u>Not</u> autoscaling.

- More flexible than it's [on-prem counterpart][sqlserver]:
    - Provision and configure it very quickly.
    - Avoid the capital expenditure and increasing operational spend of an on-prem solution.

[relationaldb]: ./relational_database.md
[sqlserver]: ./sql_server.md
[relationaldata]: ./structured_data.md
[nonrelationaldata]: ./nonstructured_data.md
[scaling]: ./scaling.md
