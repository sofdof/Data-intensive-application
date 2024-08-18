- **Data Integration**
  - Problem: Merging data across different tools.
  - Use OLTP + Elasticsearch for diverse queries.

- **Derived Data vs. Transactions**
  - Derived data updates async. transactions focus on strong consistency.
  - Log-based data sync avoids heavy transaction costs.

- **Lambda Architecture**
  - Mix batch + stream for real-time + historical data.
  - Stream for instant updates, batch for accuracy.

- **Unbundling Databases**
  - Split database roles into specialized tools.
  - Separate indexing and search from core database.

- **Federated Databases**: Unified reads across systems.
- **Unbundled Databases**: Specialized tools for different tasks.