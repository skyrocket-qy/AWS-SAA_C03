# Amazon EC2 Placement Groups

Placement groups determine how instances are placed on underlying hardware. When you launch instances, you can specify a placement group to influence their placement to meet the needs of your workload.

## Placement Strategies

### 1. Cluster
*   **Concept**: Packs instances close together inside a single Availability Zone.
*   **Goal**: Low network latency, high network throughput.
*   **Mechanism**: All instances are on the same high-bandwidth rack or adjacent racks.
*   **Use Case**: High Performance Computing (HPC), Big Data (Spark, Hadoop), Machine Learning training, tightly coupled applications.
*   **Restriction**: **Single AZ** only.

### 2. Spread
*   **Concept**: Strictly places a small group of instances across distinct underlying hardware to reduce correlated failures.
*   **Goal**: Maximize availability and reduce risk of simultaneous failure.
*   **Mechanism**: Each instance is placed on a distinct rack with its own network and power source.
*   **Use Case**: Critical applications where each instance must be isolated from failure of another (e.g., individual database nodes).
*   **Restriction**: Max **7 instances per AZ** per placement group. Can span multiple AZs.

### 3. Partition
*   **Concept**: Spreads instances across logical partitions such that instances in one partition do not share hardware with instances in other partitions.
*   **Goal**: Distribute large distributed workloads with replication needs (Hadoop HDFS, Cassandra, Kafka).
*   **Mechanism**: Divides the group into logical segments called partitions. AWS ensures partitions are on separate racks.
*   **Use Case**: Large distributed and replicated workloads (Big Data).
*   **Restriction**: Can span multiple AZs. Max 7 partitions per AZ.

## Comparison Table

| Strategy | Goal | Availability Zone Scope | Max Instances | Use Case |
| :--- | :--- | :--- | :--- | :--- |
| **Cluster** | Performance (Low Latency) | **Single AZ** | Limited by Instance Type capacity | HPC, ML, Tightly coupled apps |
| **Spread** | Availability (Hardware Isolation) | **Multi-AZ** | **7 per AZ** | Critical reliability, Database nodes |
| **Partition** | Distributed/Replicated Workloads | **Multi-AZ** | Unlimited (7 partitions per AZ) | Hadoop, Cassandra, Kafka |
