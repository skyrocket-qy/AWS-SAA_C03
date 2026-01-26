# Amazon EC2 Placement Groups

**Placement Groups** influence where EC2 instances are placed on physical hardware.

### Key Exam Points
- **Cluster**: Packs instances close together in a **single AZ**. Used for high throughput/low latency (HPC, ML).
- **Spread**: Places each instance on its own distinct rack. Max **7 instances per AZ**. Used for high-availability critical nodes.
- **Partition**: Spreads instances across logical partitions (racks). Used for large distributed workloads (Hadoop, Kafka, Cassandra).
- **Scoping**: Spread and Partition can span multiple AZs; Cluster is limited to a single AZ.
