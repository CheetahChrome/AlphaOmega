---
layout: default
title: Oracle Basics
---

| **Oracle Terms** | **Summary** |
|--------------|-------------|
| Difference VARCHAR & VARCHAR2? | VARCHAR can store characters up to 2000 bytes and holds space for characters defined during declaration even if not used. VARCHAR2 can store characters up to 4000 bytes and releases unused space. |
| Oracle Components of the logical database structure | The components include Tablespaces (logical storage units) and Database Schema Objects (tables, indexes, views, stored procedures, etc.). |
| Relationship among database, tablespace, and data file | A database contains tablespaces, which are logical storage units. Tablespaces consist of data files that store the actual data. |
| Database objects | Oracle database objects include tables, views, indexes, sequences, synonyms, and stored procedures. |
| ANALYZE command | The ANALYZE command is used to collect statistics about the schema objects to help the Oracle optimizer make decisions about the execution plan. |
| Joins in writing subqueries | Types of joins include INNER JOIN, LEFT JOIN, RIGHT JOIN, and FULL OUTER JOIN. |
| RAW datatype in Oracle | The RAW datatype is used to store binary data or byte strings. |
| Aggregate functions | Aggregate functions perform calculations on multiple rows of a single column of a table and return a single value. Examples include SUM, AVG, COUNT, MAX, and MIN. |
| Temporal data types | Temporal data types are used to store date and time information. Examples include DATE, TIMESTAMP, TIMESTAMP WITH TIME ZONE, and TIMESTAMP WITH LOCAL TIME ZONE. |
