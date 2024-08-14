# Concepts

## Index

Index is a special data structure that facilitates data search across the table. Indexing is the way to get an unordered table into an order that will maximize the query’s efficiency while searching.

When a table is unindexed, the order of the rows will likely not be discernible by the query as optimized in any way, and your query will therefore have to search through the rows linearly. In other words, the queries will have to search through every row to find the rows matching the conditions. As you can imagine, this can take a long time. Looking through every single row is not very efficient.

In reality the database table does not reorder itself every time the query conditions change in order to optimize the query performance: that would be unrealistic. In actuality, what happens is the index causes the database to create a data structure. The data structure type is very likely a B-Tree. While the advantages of the B-Tree are numerous, the main advantage for our purposes is that it is sortable. When the index creates a data structure on a specific column it is important to note that no other column is stored in the data structure. Database indexes will also store pointers which are simply reference information for the location of the additional information in memory. 

### Summing up

- Indexing adds a data structure with columns for the search conditions and a pointer
- The pointer is the address on the memory disk of the row with the rest of the information
- The index data structure is sorted to optimize query efficiency
- The query looks for the specific row in the index; the index refers to the pointer which will find the rest of the information.
- The index reduces the number of rows the query has to search through from 17 to 4.

## Table Partitioning
Table partitioning is a database design technique used to divide a large table into smaller, more manageable chunks called partitions. Each partition is essentially a separate table that stores a subset of the original data. This technique can significantly improve query performance and data management for large datasets.

Partitioning can be done based on one or more columns, such as a date column or a range of values. For example, you can partition a table based on the date of the records, where each partition represents data for a specific date range. When querying the data, PostgreSQL can quickly eliminate partitions that are not relevant to the query, resulting in faster query execution.


### Benefits

- **Improved Query Performance**: Partitioning allows the database to quickly narrow down the data to a specific partition, reducing the amount of data that needs to be scanned during queries. This results in faster query execution times, especially for large datasets.
- **Easier Data Management**: With table partitioning, you can easily manage large datasets by splitting them into smaller, more manageable partitions. This can simplify tasks such as data archiving, data purging, and backup and restore operations.
- **Enhanced Data Loading and Indexing**: When loading data into a partitioned table, the process can be parallelized, leading to faster data ingestion. Additionally, indexes on partitioned tables can be more efficient, as they only need to cover a smaller subset of data.
- **Cost-Effective Storage**: Partitioning allows you to store older or less frequently accessed data on cheaper storage media, while keeping frequently accessed data on faster storage devices.


## Sharding
Sharding, also known as horizontal partitioning, is a database partition approach that divides the database schema and distributes them across multiple instances or servers into smaller parts that are faster and easier to manage. When a database is sharded, a replica of the schema is created. This is then used to divide data to be stored in a shard based on a shard key. To make this possible, a special logic or identifier called a "shard key" is used to determine which specific instance or server holds the data to query.

To gain a deeper understanding of how sharding operates, and how you can use it, let's consider a scenario to illustrate its effectiveness. Imagine a social media platform with millions of users worldwide. In this case, you can implement sharding based on geographical regions. For example, users from North America would have their data stored in instance 1, while users from Europe would be allocated to instance 2, and so forth.

### Some benefits of sharding include:

- Improved response time
- Maintenance tasks, like backups, take less time to complete
- Schema migrations complete faster
- Increased read/write throughput
- Increased storage capacity
- Improved availability
- Outages are more isolated and less impactful


## partitioning vs sharding

While sharding and partitioning share the common goal of dividing a large database into smaller ones, they have different approaches to achieve this. When sharding a database, the data is distributed across multiple servers, resulting in new tables spread across these servers. On the other hand, partitioning involves splitting tables within the same database instance. Sharding is referred to as horizontal scaling, and it makes it easier to scale as you can increase the number of machines to handle user traffic as it increases. Partitioning splits based on the column value(s). All columns should be retained when partitioned – just different rows will be in different tables. It is also easier to manage data with partitioning, as all partitions are in one database instance.

Sharding disperses data across various databases or servers, while partitioning segregates data within a single database instance into subsets. As such, sharding is typically implemented for distributing load across a cluster to enhance scalability, and partitioning is used to improve data management and performance optimization within a database.

# References

- [How does indexing work](https://www.atlassian.com/data/databases/how-does-indexing-work)
- [Guite to Postgresql table partitioning](https://rasiksuhail.medium.com/guide-to-postgresql-table-partitioning-c0814b0fbd9b)
- [Sharding vs Partitioning](https://planetscale.com/learn/articles/sharding-vs-partitioning-whats-the-difference)
- [Sharding vs Partitioning Detailed Comparison](https://www.pingcap.com/article/sharding-vs-partitioning-a-detailed-comparison/)
