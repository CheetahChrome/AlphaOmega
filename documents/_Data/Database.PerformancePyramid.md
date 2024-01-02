---
layout: default
title: Database Performance Pyramid
---

The database Performance pyramid is a framework for measuring and improving the performance of database systems. It consists of five factors: workload, throughput, resources, optimization, and contention

| Factor | Description |
| --- | --- |
| Workload | The demand placed on the database by the users and applications. |
| Throughput | The ability of the database to process data efficiently. |
| Resources | The hardware and software tools available to the database. |
| Optimization | The process of tuning the database to achieve the best performance. |
| Contention | The conflict that arises when multiple components of the workload compete for the same resource. |

The database Performance pyramid helps to identify the root causes of performance problems and to prioritize the actions for performance improvement. By aligning the vision, resources, and support system of the database, the Performance pyramid can help to achieve the desired results.


Pyramid (Top to bottom)
- Server Tuning
- Locking
- Indexing
- Query Optmization
- Schema design

#### NOTE

The expected/intended workload of a database is key when designing a database schema and choosing the proper modeling technique.

Databases are created for different types of use case. This means that different databases are used in different ways. Data Vault is a modeling technique that optimizes the database for flexible, long-term storage of historical data.