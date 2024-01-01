---
layout: default
title: Data Modeling 
---

Data modeling is the process of deciding which data structures to use for storing data. With regard to relational databases, this translates into deciding on the table structure (schema) to use.

### Third Norma Form
 - 3NF
    - database design principle that aims to reduce data duplication 
     - and avoid data anomalies by ensuring that every non-key attribute of a table is directly and only dependent on the primary key. 
     - A table is in 3NF if it is in second normal form (2NF) and has no transitive dependencies, which means that 
        - no non-key attribute depends on another non-key attribute through the primary key. 
        
For example, if a table has the attributes `student_id`, `course_id`, `instructor_id`, and `instructor_email`, and the primary key is (`student_id`, `course_id`), then the table is not in 3NF because `instructor_email` depends on `instructor_id`, which is not part of the primary key. To achieve 3NF, the table should be split into two tables: A student based table with the attributes `student_id`, `course_id`, and `instructor_id`, and an instructor based table with the attributes `instructor_id` and `instructor_email`. 

### Different categories of sql

Sql consists of

| Category | Summary | Description |
|----------|----------|-|
| DCL  | Data Control Language  | Securing data<br/> - Grant<br/> - Deny<br/>- Revoke  |
| DDL  | Data Definition Language  | Database manipulation<br/> - Create<br/> - Alter</br> - Drop |
| DQL  | Data Query Language | Some believe `Select` should be its category on its own. |
| DML  | Data Manipulation Language  | Working with Data<br/>- SELECT<br/>- INSERT<br/>- UPDATE<br/>- DELETE<br/>  |

### Relational Theory
A relational database stores data in tables according to Codd's rules of the relational model.

- Elements of a set are **not ordered.**
   - Set based theory
   - Setup up indexes speed up data retrieval
      - One can override an index and sort w/in the query.
- All elements in a set are unique.
    - Axium of unicity
       - Unicity demands that each element of a set is unique.
    - To enforce the uniqueness of rows, we use keys. 
        - A key is a column, or a couple of columns together, in which we store unique values.

#### Types of Keys
- `Canditate Keys`
    - Columns that logically store unique values
    - Types
        - Logical/Business keys
           - Key that has a real meaning in the context of the data, such as a Social Security Number or a license plate. 
           - Data Vault Modelingg is where buisness keys play a central role
           - Can be unique in origin...but sometimes not.
        - Technical/Surrogate keys 
           - Key that is artificially created by the system
               - such as a sequence number or a GUID, and has no *business* meaning in the data. 
           - Key value has no relation to data so technically design breaks 3NF
           - Types of Constraints
                - Primary Key
                   - Used by database to check uniqness
                   - One column ensures quicker run times
                - Foreign Key
    - Referential Integrety
       - Referential integrity is the guarantee that references to other tables using foreign keys always reference existing rows.

