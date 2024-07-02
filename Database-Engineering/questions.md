# Database Engineering Questions

### Q1 : Monolith vs Microservice architecture ? 

| Monolith Architecture                                        | Microservice Architecture                                    |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| architectural style where an *application is built as a single,unified unit* | architectural style where an *application is composed of small, independent services that communicate over a network* |

###  Q2: What is an antipattern in SQL ? 

**Answer**: antipatterns are  patterns that can lead to *poor performance*, *difficult maintenance*

### Q3: List out 5 antipatterns in SQL , why is it a problem and  their respective solutions 

**Answer**: The following tables lists the 5 antipatterns,why is it a problem and their respective solution 

| Antipattern                          | Why is it a problem        | Solution                                           |
| ------------------------------------ | -------------------------- | -------------------------------------------------- |
| *Not handling transactions properly* | *Data integrity issues*    | *Use transactions correctly*                       |
| *Storing unnecessary blobs*          | *Bloats storage*           | *Store blobs in a dedicated storage*               |
| Using SELECT *                       | *Fetches unnecessary data* | specify *needed columns* in SELECT statements      |
| *Improper indexing*                  | *Slow Query performance*   | *create necessary indexes* based on query patterns |
| *Ignoring normalization*             | *data redundancy*          | *apply proper normalization techniques*            |

### Q4: What is sharding ? 

**Answer**: Partitioning a large database into *smaller, more manageable pieces called shards.* Each shard is a *separate database that holds a subset of the data*

### Q5:Horizontal vs Vertical Scaling 

**Answer**: The following table lists out the common differences between Horizontal and Vertical Scaling 

| Differentiating Factor | Horizontal Scaling                               | Vertical Scaling                             |
| ---------------------- | ------------------------------------------------ | -------------------------------------------- |
| Scaling Mechanism      | Scaling by *adding more machines to the network* | Scaling by *increasing resource per machine* |
| Implementing Approach  | Typically achieved through *load balancing*      | Involves *upgrading CPU,RAM,storage*         |

### List out 5 differences between Relational and Non-relational databases ? 

**Answer**: The following table lists out 5 differences between Relational and Non-Relational Databases

| Criteria            | Relational Database                                          | Non Relational Database                                      |
| ------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Scalability         | *vertical scaling*                                           | *horizontal scaling*                                         |
| Complex Queries     | *supports complex queries*                                   | *limited support for complex queries*                        |
| Transaction support | *ACID* Compliance (Atomicity,Consistency,Isolation,Durability) | *BASE* Compliance (Basically Available ,Soft state,Eventual Consistency) |
| Performance         | Good for *complex queries*                                   | High Performance for *large-scale distributed data*          |
| Data Integrity      | *High data integrity*                                        | *Less data Integrity*                                        |

