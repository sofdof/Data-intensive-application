### Chapter 11: Stream Processing

- **Unbounded Data Streams**
  - Unlike batch processing, stream processing handles data that continuously arrives over time, without a defined end.
  - Example: Processing user activity logs in real-time as they are generated.

- **Event Time vs. Processing Time**
  - Stream processing differentiates between when an event occurred (event time) and when it is processed (processing time). This distinction is crucial for accurate data handling.
  - Example: Windowing functions in Apache Flink, which group events by event time rather than when they are processed.

- **Windowing**
  - To manage unbounded data, stream processing uses windows to group data over specific time frames.
  - Example: Calculating a rolling average over the last 10 minutes of data, using sliding windows.

- **Stateful Stream Processing**
  - Maintains state across events, enabling complex operations like joins and aggregations.
  - Example: Apache Kafka Streams, which can join a live data stream with a reference table stored in a database.

### Fault Tolerance

- **Exactly-Once Semantics**
  - Stream processing systems strive for exactly-once processing guarantees, ensuring that each piece of data is processed exactly once, even in the face of failures.
  - Example: Apache Kafka's support for exactly-once semantics through transactionally consistent processing.