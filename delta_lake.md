# Delta Lake
Delta Lake is an open format storage layer that delivers reliability, security and performance 
on data lake — for both streaming and batch operations. By replacing data silos with 
a single home for structured, semi-structured and unstructured data, Delta Lake is the foundation 
of a cost-effective, highly scalable lakehouse.

Delta Lake is an open source project that enables building a Lakehouse architecture on top of data lakes.
Delta Lake provides ACID transactions, scalable metadata handling, and unifies streaming and 
batch data processing on top of existing data lakes, such as S3, ADLS, GCS, and HDFS.

Specifically, Delta Lake offers:
- **ACID transactions on Spark**: Serializable isolation levels ensure that readers never see inconsistent data.
- **Scalable metadata handling**: Leverages Spark distributed processing power to handle all the metadata for petabyte-scale tables with billions of files at ease.
- **Streaming and batch unification**: A table in Delta Lake is a batch table as well as a streaming source and sink. Streaming data ingest, batch historic backfill, interactive queries all just work out of the box.
- **Schema enforcement**: Automatically handles schema variations to prevent insertion of bad records during ingestion.
- **Time travel**: Data versioning enables rollbacks, full historical audit trails, and reproducible machine learning experiments.
- **Upserts and deletes**: Supports merge, update and delete operations to enable complex use cases like change-data-capture, slowly-changing-dimension (SCD) operations, streaming upserts, and so on.


## When to use
- Delta Lake is, like Parquet, a columnar oriented format. So, it’s best fitted for analytic workloads.
- With Delta transaction log files, it provides ACID transactions and isolation level to Spark.
- To work with data lakehouse 


## Referencies
- [What is Delta Lake?](https://databricks.com/product/delta-lake-on-databricks)
- [Delta Intro](https://docs.delta.io/latest/delta-intro.html)
- [Transaction Log](https://databricks.com/blog/2019/08/21/diving-into-delta-lake-unpacking-the-transaction-log.html)
- [5 reasons to choose Delta Lake format](https://medium.com/datalex/5-reasons-to-use-delta-lake-format-on-databricks-d9e76cf3e77d)
- [Delta FAQ](https://docs.microsoft.com/en-us/azure/databricks/delta/delta-faq)
- [Delta Lake ACID](https://towardsdatascience.com/delta-lake-with-spark-what-and-why-6d08bef7b963)
