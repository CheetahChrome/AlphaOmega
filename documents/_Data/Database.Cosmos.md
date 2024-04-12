---
layout: default
title: Database Cosmos
---

| Interview Question | Answer |
|--------------------|--------|
| What is Azure Cosmos DB and what are its key features? | Azure Cosmos DB is a globally distributed, multi-model database service that offers `multi-master replication`, `horizontal scaling`, and `multiple consistency models`. |
| What are the advantages of using Azure Cosmos DB over traditional relational databases? | Azure Cosmos DB offers global distribution, elastic scalability, low latency, and support for multiple data models, which are not typical features of traditional relational databases. |
| Can you explain the different `consistency levels` available in Azure Cosmos DB? | Azure Cosmos DB offers five consistency levels: `Strong`, `Bounded Staleness`, `Session`, `Consistent Prefix`, and `Eventual`. Each provides a trade-off between consistency and performance. |
| What are the different APIs supported by Azure Cosmos DB? | Azure Cosmos DB supports `SQL API`, `MongoDB API`, `Cassandra API`, `Gremlin API`, and `Table API`, allowing developers to use familiar languages and patterns. |
consumption. |
| How does Azure Cosmos DB handle concurrency? | Azure Cosmos DB handles concurrency using either `optimistic concurrency` control with `ETags` or by leveraging the `session consistency` model. |
| How does Azure Cosmos DB ensure data distribution and global scalability? | It uses global distribution and partitioning to distribute data across multiple regions and scales horizontally by adding or removing resources as needed. |
| How does partitioning work in Azure Cosmos DB and why is it important? | Partitioning in Azure Cosmos DB involves distributing data across multiple partitions based on a partition key. It's important for load balancing and maximizing throughput. |
| What is the role of Request Units (`RUs`) in Azure Cosmos DB? | `RUs` are a measure of throughput in Azure Cosmos DB. They represent the cost of database operations and are used to manage and scale resources. |
| Can you describe the indexing strategy used by Azure Cosmos DB? | Azure Cosmos DB automatically indexes all data by default, but it allows for customization of the indexing policy to optimize performance and RU 
| How do you secure data in Azure Cosmos DB? | Data in Azure Cosmos DB can be secured using Azure Active Directory, role-based access control, network security with VNETs, and encryption at rest and in transit. |
