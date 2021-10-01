# Sumário

- [Data Warehouse](data_warehouse.md)
- [Datalake](datalake.md)
- [Data Lakehouse](data_lakehouse.md)

## Data Warehouse vs Datalake
- **Different purposes**. Data Warehouses are used by managers, analysts, and other business end-users, while Data Lakes are mainly used by Data Scientists and Data engineers. Recall that Data Lake stores mostly raw unstructured and semi-structured data — telemetry, graphics, logs of user behavior, website metrics, and information systems, as well as other data with different storage formats. They are not yet suitable for daily analytics in BI systems but can be used by Data Scientists to test new business hypotheses using statistical algorithms and Machine Learning methods.
- **Different processing methods**. ETL is a popular data processing paradigm in many popular data warehousing. Essentially we extract data from a source or sources, clean it up, and convert it into the structured information we need, and upload it. With Data Lakes we use another paradigm ELT(Extract, Load, Transform) because the transformation takes place in the later stages and only if needed not upfront.
- **Different levels of understanding of the data**. In Data Lakes data is never rejected because it is stored in an unprocessed format. This is especially useful in an environment with large data if you do not know in advance what information will be obtained from the data analysis. At the same time, the central database(s) is the foundation of the data warehousing environment. Usually, such databases are implemented on RDBMS technology and therefore the necessary in-depth design of the data model is required.
- **Different approaches to design**. Data Warehouse design is based on relational data handling logic - the third normal form for normalized storage, star or snowflake schemes for storage. When designing the data lake, the Big Data Architect and Data Engineer pay more attention to ETL processes, taking into account the diversity of sources and consumers of information. And the question of storage is solved quite simply - you only need a scalable, fault-tolerant, and relatively cheap file system, such as HDFS or AWS S3.
- **Different price**. Usually, Data Lake is built on the basis of cheap servers with Apache Hadoop, without expensive licenses and powerful equipment, in contrast to a lot of maintenance costs as well as large costs of design and purchase of specialized platforms for Data Warehouse, such as SAP, Oracle, Teradata, etc.

## Referências
- [Data Lake vs Data Warehouse](https://luminousmen.com/post/data-lake-vs-data-warehouse)