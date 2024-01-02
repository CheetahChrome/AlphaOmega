---
layout: default
title: Database Normalizing
---

# Normal Forms

| Normal Form  |Description|
|-|-|
| 1NF  | Ensures that each column contains atomic (indivisible) values and that there are no repeating groups or arrays of data. |
| 2NF  | Builds on 1NF and eliminates partial dependencies by ensuring that each non-key attribute is fully functionally dependent on the primary key. |
| 3NF   | Extends 2NF by removing transitive dependencies, ensuring that non-key attributes are not dependent on other non-key attributes. |
| BCNF (Boyce-Codd Normal Form) | Similar to 3NF but specifically addresses the issue of non-prime attributes determining prime attributes. |
| 4NF  | Addresses multi-valued dependencies by ensuring that there are no non-trivial multi-valued dependencies involving non-prime attributes. |
| 5NF  | Also known as Project-Join Normal Form (PJ/NF), it deals with cases where a table has multiple overlapping candidate keys. |

# Reason to Normalize

| Reason to Normalize       | Description                                                                                              | Pros                                               | Cons                                               |
|---------------------------|----------------------------------------------------------------------------------------------------------|---------------------------------------------------|---------------------------------------------------|
| Reducing Data Redundancy  | Normalization eliminates data redundancy by organizing data in a structured way.                      | - Saves storage space.                            | - May require more complex queries.               |
| Minimizing Data Anomalies | Normalization helps in preventing data anomalies such as update, insert, or delete anomalies.           | - Maintains data integrity.                      | - Can be complex to design and implement.         |
| Simplifying Updates       | When data is normalized, updates are more straightforward and less error-prone.                       | - Reduces the need for updating data in multiple places. | - Increased complexity of retrieving data.       |
| Enforcing Data Integrity  | Normalization enforces rules and constraints to maintain data integrity.                                | - Reduces the risk of invalid or inconsistent data. | - May require more development effort.            |
| Supporting Scalability    | A well-normalized database can be more scalable as it can handle large datasets efficiently.           | - Better performance for read-heavy workloads.   | - Increased complexity in the design phase.       |
| Facilitating Maintenance  | Normalized databases are easier to maintain and update over time.                                         | - Simplifies database maintenance.               | - May require more effort during initial design.   |

