### Problems with Distributed System

### Problems with Networks

- **Asynchronous Networks**
  - No guarantees on message delivery time or success.
  - Issues include lost or delayed packets and unresponsive nodes.
  - Use of timeouts helps, but exact failure causes remain uncertain.
  - Example: A request might get lost or delayed, or the node might fail.

### Problems with Clocks

- **Clock Synchronization**
  - Machines have individual clocks that can drift over time.
  - Time-of-day clocks can be synchronized with NTP, but still have inaccuracies.
  - Monotonic clocks measure durations but lack absolute time values.
  - Example: Unsynchronized clocks can lead to inconsistencies in systems using last write wins (LWW).

### Process Pauses

- **Unpredictable Delays**
  - Distributed systems may experience process pauses due to garbage collection, system overloads, or other interruptions, impacting performance and reliability.

### Coping with Challenges

- **Fault Tolerance**
  - Design strategies like replication, consistent hashing, and quorum-based approaches help manage partial failures.
  - Example: Using quorum-based approaches for ensuring data consistency.

- **Concurrency Control**
  - Mechanisms like two-phase locking (2PL) and serializable snapshot isolation help maintain transaction consistency.
  - Example: 2PL helps by allowing concurrent reads but blocking writes until safe.