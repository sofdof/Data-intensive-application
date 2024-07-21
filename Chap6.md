### Reasons for Partitioning

- **Scalability**
  - Distributes data and query load evenly across multiple machines
  - Allows for handling large datasets and high query throughput
  - HBase regions or MongoDB shards

### Methods of Partitioning

- **Key-Range Partitioning**
  - Assigns continuous ranges of keys to each partition
  - Facilitates efficient range queries by keeping keys in sorted order
  - Using date-based keys can lead to hot spots
  - Partitions are typically rebalanced dynamically by splitting ranges when they become too large

- **Hash Partitioning**
  - Uses a hash function to determine the partition for a given key
  - Distributes keys uniformly to prevent skew and hot spots
  - Cassandra uses consistent hashing to distribute keys
  - Common to create a fixed number of partitions in advance, assigning several to each node and moving partitions when nodes are added or removed
  - Dynamic partitioning can also be used

### Challenges of Partitioning

- **Skewed Partitions and Hot Spots**
  - Uneven distribution of data or query load
  - Results in some partitions being overburdened while others remain idle
  - High load on a single partition leads to performance bottlenecks

### Secondary Index Partitioning

- **Partition by Document (Local Index)**
  - Each partition maintains its own secondary index
  - Requires scatter/gather queries across all partitions
  - MongoDB and Elasticsearch

- **Partition by Term (Global Index)**
  - Secondary index is partitioned separately
  - Writes may need to update multiple partitions
  - Indexing by terms in a search engine like Solr

### Rebalancing Partitions

- **Fixed Number of Partitions**
  - Large number of partitions created initially
  - Evenly distributes load but can complicate scaling
  - Riak and Couchbase

- **Dynamic Partitioning**
  - Partitions split or merge based on load
  - Adapts to changing data sizes and access patterns
  - HBase and RethinkDB dynamically adjust partition sizes

### Query Routing Techniques

- **Partition-Aware Load Balancing**
  - Directs queries to the appropriate partition
  - Ensures efficient query handling and load distribution

- **Sophisticated Parallel Query Execution Engines**
  - Optimize query execution across multiple partitions
  - Enhance performance for complex queries involving multiple partitions
