# Data Lakehouse
Now new systems are beginning to emerge that address the limitations of both Data Lake and Data Warehouse - Lakehouse(new marketing term from Databricks). The main solutions are **Delta Lake** from Databricks, **Apache Hudi** from Uber, **Apache Iceberg** from Netflix.

A data lakehouse is a new, open **data management architecture** that combines the flexibility, cost-efficiency, and scale of data lakes with the data management and ACID transactions of data warehouses, enabling business intelligence (BI) and machine learning (ML) on all data.

<p align="center">
    <img src="images/data_lakehouse.png" alt="Data Lakehouse" />
</p>

There are a few key technology advancements that have enabled the data lakehouse:

- metadata layers for data lakes.
- new query engine designs providing high-performance SQL execution on data lakes.
- optimized access for data science and machine learning tools.

Data warehouses have a long history in decision support and business intelligence applications, **though were not suited or were expensive for handling unstructured data, semi-structured data, and data with high variety, velocity, and volume.** 

Data lakes emerged to handle raw data in a variety of formats on cheap storage for data science and machine learning, though lacked critical features from the world of data warehouses: **they do not support transactions, they do not enforce data quality, and their lack of consistency/isolation makes it almost impossible to mix appends and reads, and batch and streaming jobs.**

Data teams consequently stitch these systems together to enable BI and ML across the data in both these systems, resulting in duplicate data, extra infrastructure cost, security challenges, and significant operational costs. In a two-tier data architecture, data is ETLd from the operational databases into a data lake. This lake stores the data from the entire enterprise in low-cost object storage and is stored in a format compatible with common machine learning tools but is often not organized and maintained well. Next, a small segment of the critical business data is ETLd once again to be loaded into the data warehouse for business intelligence and data analytics.

Most of the recent advances in AI have been in better models to process unstructured data (text, images, video, audio), but these are precisely the types of data that a data warehouse is not optimized for. A common approach is to use multiple systems – a data lake, several data warehouses, and other specialized systems such as streaming, time-series, graph, and image databases. Having a multitude of systems introduces complexity and more importantly, introduces delay as data professionals invariably need to move or copy data between different systems.

Why use a lakehouse instead of a data lake for AI? A lakehouse gives you data versioning, governance, security and ACID properties that are needed even for unstructured data.

## Key Features
A lakehouse has the following key features:

- **Transaction support**: In an enterprise lakehouse many data pipelines will often be reading and writing data concurrently. Support for ACID transactions ensures consistency as multiple parties concurrently read or write data, typically using SQL.
- **Schema enforcement and governance**: The Lakehouse should have a way to support schema enforcement and evolution, supporting DW schema architectures such as star/snowflake-schemas. The system should be able to reason about data integrity, and it should have robust governance and auditing mechanisms.
- **BI support**: Lakehouses enable using BI tools directly on the source data. This reduces staleness and improves recency, reduces latency, and lowers the cost of having to operationalize two copies of the data in both a data lake and a warehouse.
- **Storage is decoupled from compute**: In practice this means storage and compute use separate clusters, thus these systems are able to scale to many more concurrent users and larger data sizes. Some modern data warehouses also have this property.
- **Openness**: The storage formats they use are open and standardized, such as Parquet, and they provide an API so a variety of tools and engines, including machine learning and Python/R libraries, can efficiently access the data directly.
- **Support for diverse data types ranging from unstructured to structured data**: The lakehouse can be used to store, refine, analyze, and access data types needed for many new data applications, including images, video, audio, semi-structured data, and text.
- **Support for diverse workloads**: including data science, machine learning, and SQL and analytics. Multiple tools might be needed to support all these workloads but they all rely on the same data repository.
- **End-to-end streaming**: Real-time reports are the norm in many enterprises. Support for streaming eliminates the need for separate systems dedicated to serving real-time data applications.


## Referencies
- [Data Lake vs Data Warehouse](https://luminousmen.com/post/data-lake-vs-data-warehouse)
- [Data Lakehouse](https://databricks.com/glossary/data-lakehouse)
- [What Is a Lakehouse?](https://databricks.com/blog/2020/01/30/what-is-a-data-lakehouse.html)
