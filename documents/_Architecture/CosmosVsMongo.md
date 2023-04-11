---
title: Cosmos Versus Mongo DB
layout: default
---
# Cosmos Versus MongoDB

MongoDB and Cosmos DB are both **NoSQL databases**, but they have some differences.

## Similarities

Similarities:

Both databases are NoSQL, meaning they do not use the traditional table-based relational database structure.
Both support **horizontal scaling** and **distributed architectures**.
Both allow developers to store and manipulate large amounts of **unstructured or semi-structured data**.

## Differences

| Name | Description |
| --- | --- |
| Data Model | MongoDB is a document-based database, meaning it stores data in JSON-like documents that can be nested and contain arrays. Cosmos DB, on the other hand, supports multiple data models, including document, key-value, graph, and column-family. |
| Query Language | MongoDB uses its own query language called the MongoDB Query Language (MQL), which is similar to SQL but with some differences. Cosmos DB supports multiple APIs including SQL, MongoDB API, Cassandra API, Azure Tables API, and Gremlin API. |
| Consistency Models | MongoDB supports strong and eventual consistency models, with the option to choose which one to use for each query. Cosmos DB supports five consistency models: strong, bounded-staleness, session, consistent-prefix, and eventual. |
| Cost | Cosmos DB can be more expensive than MongoDB, especially for larger workloads, due to its wider range of features and better scalability. |
| Hosting | MongoDB can be self-hosted or hosted on cloud platforms such as Atlas or AWS. Cosmos DB is a cloud-native database and can only be hosted on Azure. |

