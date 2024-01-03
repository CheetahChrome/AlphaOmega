---
layout: default
title: Data Modeling
---

Kimball invented dimensional modeling to create an optimal user experience when using a relational database as a source for reporting and analytics.
    - optimized for large datasets

Star Schema - Intiuitive easy to use, imprese the productivyt of report degvleopers
Fact Tables
   - All measureable quantities
Dimension tables
   - Dimension attributes (columns in dimension tables) mainly contain textual descriptors that provide context and meaning to the facts stored in the fact table.



   #### Data Vault Modeling

   Data Vault modeling is a mix between normalizing data and dimensional modeling. It is designed to provide a flexible way to store detailed, historical data. By using Hubs, Links, and Satellites, you create a database in which you never need to alter an existing table. 


   #### Data Lake

   A data lake plays a central role in the modern data warehouse architecture. In this chapter, you learned what a data lake is. You learned what zones a data lake may consist of and how to set up a folder structure for those zones. You also learned about some different file formats to use.

You implemented a data lake by provisioning an Azure storage account.


#### Azure Data Factory
ETL (Extract, transform, load)
 - Activities
 - Datasets
 - Linked services
 - Pipelines