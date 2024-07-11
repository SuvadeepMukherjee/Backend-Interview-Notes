## Questions on MongoDB 

#### Q1:What does NoSQL mean ?

**Answer**:NoSQL stands for "Not Only SQL," referring to databases that *do not use the traditional SQL-based relational model.*

#### Q2:What is the advantage of using NoSQL over SQL ?

**Answer**:The advantages of using NoSQL are listed below 

- **Scalability:** Easily scales horizontally with sharding.
- **Flexibility:** Schema-less design allows for easy handling of varying data structures.
- **Performance:** High-speed read and write operations.
- **Replication:** Built-in replication for high availability and redundancy.
- **Rich Query Language:** Powerful querying and aggregation capabilities.
- **Document-Oriented:** Stores data in JSON-like documents, making it intuitive to use.

#### Q3:What format does MongoDB store data in ?

**Answer**:data is stored in *BSON (Binary JSON) format*.

#### Q4:Can we form relations in NoSQL? 

**Answer**:Yes, relations can be formed using *embedding or referencing*.

#### Q5:What is a Document in MongoDB?

**Answer**:A document in MongoDB is a JSON-like data structure composed of field-value pairs, used to store and retrieve data within collections.

```
Database
  └── Collection
        └── Document
```



#### Q6:What are Databases in MongoDB?

**Answer**:Databases in MongoDB are containers for collections of documents. Each database has its own set of collections and is used to organize and manage data.

```
Database
  └── Collection
        └── Document
```

#### Q7:How do you Scale up MongoDB to handle millions of users?

**Answer**:To scale up MongoDB to handle millions of users:

1. **Sharding:** Distribute data across multiple servers.
2. **Replication:** Use replica sets for high availability and failover.
3. **Indexing:** Create efficient indexes to optimize query performance.
4. **Load Balancing:** Distribute load across multiple nodes.
5. **Optimize Queries:** Fine-tune queries and use aggregation pipelines effectively.
6. **Horizontal Scaling:** Add more servers to handle increased load.

#### Q8:What are the different kinds of indexing in Nosql database? Explain each one of them in your own words.

**Answer**: The following table illustrates the different kinds of indexing in NoSql databases 

| Index Type         | Defination                                |
| ------------------ | ----------------------------------------- |
| Single Field Index | Indexes a single field in a document.     |
| Compound Index     | Indexes multiple fields within a document |
| Multikey Index     | Indexes array fields within documents.    |
| Geospatial Index   | Indexes geographical data                 |
| Text Index         | Indexes textual content                   |
| Hashed Index       | Indexes data using hash values            |

####  Q9:How does sharding work in NoSql 

**Answer**:Sharding in NoSQL works by splitting large datasets across multiple servers, called shards, to improve scalability and performance. Here’s how it works:

1. **Shard Key:** A specific field or set of fields in the data is chosen as the shard key. This key determines how data is distributed across shards.
2. **Data Distribution:** The database uses the shard key to partition data. Each shard stores a subset of the data, determined by the shard key values.
3. **Query Routing:** The database automatically routes queries to the appropriate shard(s) based on the shard key, ensuring efficient data retrieval.
4. **Balancing:** As data grows, the database can automatically balance data across shards to prevent any single shard from becoming a bottleneck.
5. **Replication:** Each shard can have replicas for high availability and failover, ensuring data reliability and redundancy.

This approach enables horizontal scaling, allowing the database to handle large amounts of data and high query loads efficiently.

#### Q10:What does replica set mean in Mongodb?

**Answer**:A replica set in MongoDB is a group of MongoDB servers that maintain the same data set, providing redundancy and high availability. It includes a primary node for writes and one or more secondary nodes for read operations and failover support