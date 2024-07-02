# Database Engineering Questions

### Q1 : Monolith vs Microservice architecture ? 

| Monolith Architecture                                        | Microservice Architecture                                    |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| architectural style where an *application is built as a single,unified unit* | architectural style where an application is composed of small, independent services that communicate over a network |

###  Q2: What is an antipattern in SQL ? 

**Answer**: antipatterns are  patterns that can lead to *poor performance*, *difficult maintenance*

### Q3: List out 5 antipatterns in SQL , why is it a problem and  their respective solutions 

**Answer**: The following tables lists the 5 antipatterns,why is it a problem and their respective solution 

| Antipattern                        | Why is it a problem        | Solution                                           |
| ---------------------------------- | -------------------------- | -------------------------------------------------- |
| Not handling Transactions Properly | *Data integrity issues*    | *Use transactions correctly*                       |
| Storing Unnecessary Blobs          | *Bloats storage*           | *Store blobs in a dedicated storage*               |
| Using SELECT *                     | *Fetches unnecessary data* | specify *needed columns* in SELECT statements      |
| Improper Indexing                  | *Slow Query performance*   | *create necessary indexes* based on query patterns |
| Ignoring Normalization             | *data redundancy*          | *apply proper normalization techniques*            |

### Q4: What is sharding ? 

**Answer**: Partitioning a large database into *smaller, more manageable pieces called shards.* Each shard is a *separate database that holds a subset of the data*

### Q5:Horizontal vs Vertical Scaling 

**Answer**: The following table lists out the common differences between Horizontal and Vertical Scaling 

| Differentiating Factor | Horizontal Scaling                               | Vertical Scaling                             |
| ---------------------- | ------------------------------------------------ | -------------------------------------------- |
| Scaling Mechanism      | Scaling by *adding more machines to the network* | Scaling by *increasing resource per machine* |
| Implementing Approach  | Typically achieved through *load balancing*      | Involves *upgrading CPU,RAM,storage*         |

