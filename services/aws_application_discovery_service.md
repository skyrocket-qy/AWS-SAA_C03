# AWS Application Discovery Service

**AWS Application Discovery Service** helps enterprise customers plan migration projects by gathering information about their on-premises data centers. It collects and presents configuration, usage, and behavior data from your servers to help you better understand your workloads.

## Key Features

### 1. Data Collection
- **Server Specification**: Collects CPU, RAM, and disk IOPS/throughput.
- **Performance**: Measures resource utilization over time.
- **Dependencies**: Identifies network connections between servers (useful for grouping applications).

### 2. Integration
- **AWS Migration Hub**: Automatically sends collected data to Migration Hub for a unified view of your migration status.
- **Athena**: Data can be exported to S3 and queried with Athena for custom analysis.

### 3. Collection Methods

#### Agentless Collector
- **Deployment**: Deployed as an OVA file (virtual appliance) in **VMware vCenter**.
- **Use Case**: When you cannot install agents on servers or for a high-level view.
- **Data**: VM inventory, configurations, and performance profile (CPU/RAM/Disk).
- **Limitation**: Cannot see inside the OS (processes, network dependencies).

#### Agent-based Discovery
- **Deployment**: Install a lightweight agent on each host (Windows/Linux) - physical or virtual.
- **Use Case**: When you need detailed information or **network dependency mapping**.
- **Data**: Detailed system configuration, time-series system performance, inbound/outbound network connections, running processes.

## Exam Tips
- **Planning phase**: Use Application Discovery Service *before* migration to discover what you have.
- **Dependency Mapping**: If the question asks to "identify dependencies between servers" or "map network connections" for migration, choose **Agent-based** discovery.
- **VMware**: If managing VMware vCenter and want a quick/easy setup without installing software on every VM, choose **Agentless**.
- **Privacy**: Does not collect application data or content (e.g., database records).
