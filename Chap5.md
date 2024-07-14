### Reasons for Replication

- **Availability**
  - Ensures data remains accessible even if some system parts fail
  - Fault tolerance in distributed systems like Cassandra

- **Latency**
  - Reduces access time by placing data geographically closer to users
  - CDNs delivering content from the nearest server

- **Scalability**
  - Distributes read queries across multiple machines, increasing read throughput
  - MySQL read replicas

### Replication Methods

- **Single-Leader Replication**
  - One node (leader) handles all writes and propagates changes to followers
  - PostgreSQL primary and standby servers

- **Multi-Leader Replication**
  - Multiple nodes accept writes and replicate changes to others
  - CouchDB for distributed editing

- **Leaderless Replication**
  - Nodes coordinate writes without a central leader using quorum-based techniques
  - Amazon DynamoDB's quorum-based replication

### Replication Lag and Its Issues

- **Read-After-Write Consistency**
  - Ensures users read their own recent writes by directing reads to the leader or synchronizing replicas
  - MongoDB primary reads

- **Monotonic Reads**
  - Guarantees users do not read older data after having read newer data, typically by reading from the same replica
  - Cassandra consistent read replicas

- **Consistent Prefix Reads**
  - Ensures reads reflect a consistent sequence of events, crucial for partitioned databases
  - Google Spanner's synchronized clocks and global transaction manager

### Handling Conflicts

- **Avoidance**
  - Minimize write conflicts by assigning writes to a single leader
  - MySQL master node for serialized writes

- **Resolution**
  - Use strategies like last write wins, custom conflict resolution logic, or CRDTs to merge conflicting changes
  - Cassandra's last write wins with timestamps

### Replication Techniques

- **Statement-Based Replication**
  - Replicates SQL statements, which can be problematic with non-deterministic functions like random numbers
  - MySQL's statement-based replication issues with `NOW()`

- **Write-Ahead Log (WAL) Shipping**
  - Replicates changes at the storage engine level, but can be tightly coupled to the storage format
  - PostgreSQL WAL shipping

- **Row-Based Replication**
  - Logs individual row changes, offering better compatibility and flexibility for various versions and external systems
  - MySQL row-based replication

- **Trigger-Based Replication**
  - Uses application-level triggers to manage replication, providing flexibility but adding overhead
  - Oracle database triggers for custom replication logic