# AWS Database Services Comparison

| Service | Type | Use Case | Performance/Scaling | Protocol/Compatibility |
| :--- | :--- | :--- | :--- | :--- |
| **Amazon RDS** | Relational (OLTP) | Traditional applications, ERP, CRM, commerce | Vertical scaling (instance size), Read Replicas | MySQL, Postgres, MariaDB, Oracle, SQL Server |
| **Amazon Aurora** | Relational (OLTP) | High throughput, enterprise apps, SaaS | Auto-scaling storage, Serverless option, high availability | MySQL, PostgreSQL compatible |
| **Amazon DynamoDB** | Key-Value (NoSQL) | Serverless apps, microservices, mobile, gaming | Horizontal scaling, single-digit millisecond latency | proprietary API |
| **Amazon DocumentDB** | Document (NoSQL) | Content management, catalogs, user profiles | Scalable compute/storage independent | MongoDB compatible |
| **Amazon ElastiCache** | In-Memory | Caching, session store, real-time analytics | Microsecond latency, horizontal scaling | Redis, Memcached |
| **Amazon Neptune** | Graph | Social networks, recommendation engines, fraud detection | Relationships navigation, Billions of relationships | Gremlin, SPARQL |
| **Amazon Timestream** | Time Series | IoT applications, DevOps monitoring, telemetry | Trillions of events per day, 1000x faster than relational | SQL |
| **Amazon QLDB** | Ledger | Supply chain, banking, system of record | Immutable, cryptographically verifiable | PartiQL |
| **Amazon Keyspaces** | Wide Column (NoSQL) | High-speed, high-volume data, industrial apps | Serverless, scaling on demand | Apache Cassandra |
| **Amazon Redshift** | Warehousing (OLAP) | Data warehousing, complex analytics | Petabyte-scale, columnar storage | PostgreSQL compatible (SQL) |
