---
layout: post
title: Codds 12 Rules
date: 2023-12-31
categories: [database]
---
| Rule # | Rule | Description |
| --- | --- | --- |
| 0 | Foundation rule | The system must be able to manage databases entirely through its relational capabilities, without relying on any external or procedural features. |
| 1 | Information rule | All data in the system must be represented as values in tables, with no hidden or implicit information. |
| 2 | Guaranteed access rule | Every value in the system must be uniquely identifiable by its table name, primary key, and column name. |
| 3 | Systematic treatment of null values | The system must support null values to represent missing or inapplicable information, and treat them consistently regardless of the data type. |
| 4 | Dynamic online catalog based on the relational model | The system must store the description of the database (the metadata) as data in tables, and allow users to query and manipulate it using the same relational language as the regular data. |
| 5 | Comprehensive data sublanguage rule | The system must support at least one language that can express all the operations needed to define, manipulate, and control the data, such as data definition, view definition, data manipulation, integrity constraints, authorization, and transaction boundaries. |
| 6 | View updating rule | The system must allow users to define views (subsets or combinations of data from one or more tables) and update them as if they were base tables, as long as the updates do not violate any constraints or dependencies. |
| 7 | High-level insert, update, and delete | The system must support inserting, updating, and deleting data from multiple tables at once, using a single statement that operates on sets of rows, rather than individual rows. |
| 8 | Physical data independence | The system must allow users to change the physical structure or storage of the data without affecting the logical structure or access of the data. |
| 9 | Logical data independence | The system must allow users to change the logical structure or schema of the data without affecting the existing applications or queries that use the data, as long as the changes do not alter the meaning or semantics of the data. |
| 10 | Integrity independence | The system must allow users to define and enforce the integrity rules and constraints of the data, using the same relational language as the data manipulation, and without relying on any external code or triggers. |
| 11 | Distribution independence | The system must allow users to distribute the data across multiple locations or devices, without affecting the way the data is accessed or manipulated, and without requiring any special commands or syntax. |
| 12 | Non-subversion rule | The system must not allow users to bypass or subvert the relational interface or the integrity rules of the data, by using any low-level or direct access methods. |
