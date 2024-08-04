### Chapter 9: Consistency and Consensus

- **Eventual Consistency**
  - Nodes may temporarily hold different data but will converge over time.
  - Example: DNS updates propagate gradually across servers.

- **Linearizability**
  - Ensures immediate consistency by making writes instantly visible.
  - Example: Google Spanner provides linearizable reads.

### CAP Theorem

- **Trade-offs**
  - Systems must balance Consistency, Availability, and Partition Tolerance, often choosing two.
  - Example: Amazon Dynamo prioritizes availability during network partitions.

### Consensus Algorithms

- **Importance**
  - Crucial for tasks like leader election and maintaining consistent state.
  - Example: Raft used in etcd for log replication.

- **Common Algorithms**
  - **Paxos**: Robust but complex.
  - **Raft**: Simpler alternative to Paxos.

### Chapter 10: Batch Processing

### Key Concepts

- **Batch vs. Stream Processing**
  - Batch processes data in chunks at intervals; stream handles continuous data.
  - Example: Hadoop for batch, Kafka for streams.

### MapReduce

- **Framework**
  - Distributes large dataset processing via `Map` (filter/sort) and `Reduce` (aggregate).
  - Example: Google’s MapReduce for web indexing.

- **Components**
  - **Hadoop**: Open-source implementation of MapReduce.
  - Example: Hadoop processes large log files efficiently.

### Data Pipelines

- **Workflow Orchestration**
  - Tools like Airflow manage complex workflows and dependencies.
  - Example: Automating ETL processes.

### Fault Tolerance

- **Techniques**
  - Checkpointing and retries ensure job recovery.
  - Example: Spark’s checkpointing for fault tolerance.