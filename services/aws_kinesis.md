# Amazon Kinesis

Amazon Kinesis makes it easy to collect, process, and analyze real-time, streaming data so you can get timely insights and react quickly to new information.

## Key Services

### 1. Amazon Kinesis Data Streams (KDS)
*   **Concept**: Real-time scalable data streaming service.
*   **Key Features**:
    *   **Retention**: Data stored for 24 hours by default (up to 365 days).
    *   **Shards**: Throughput is provisioned by **shards** (1MB/s IN, 2MB/s OUT). You must manually manage/scale shards (unless On-Demand mode).
    *   **Consumers**: You write custom applications (EC2, Lambda, KCL) to consume data.
    *   **Real-time**: Latency ~200ms or ~70ms (Enhanced Fan-out).

### 2. Amazon Kinesis Data Firehose
*   **Concept**: Fully managed service to deliver real-time streaming data to destinations.
*   **Destinations**: **Amazon S3**, **Amazon Redshift**, **Amazon OpenSearch**, **Splunk**, HTTP Endpoints.
*   **Key Features**:
    *   **Near Real-time**: Buffer interval (min 60s) or Buffer size (min 1MB). **Not** truly real-time.
    *   **No Code**: Fully managed, auto-scaling, serverless.
    *   **Transformation**: Can use Lambda to transform data before delivery (e.g., CSV -> JSON).

### 3. Amazon Kinesis Data Analytics
*   **Concept**: Analyze streaming data with SQL or Apache Flink.
*   **Use Case**: Real-time metrics, dashboarding, anomaly detection.

### 4. Amazon Kinesis Video Streams
*   **Concept**: Securely stream video from connected devices to AWS for analytics, ML, playback, and other processing.

## Comparison: KDS vs Firehose
| Feature | Kinesis Data Streams | Kinesis Data Firehose |
| :--- | :--- | :--- |
| **Management** | Manual (Shards) | Fully Managed (Serverless) |
| **Latency** | Real-time (~200ms) | Near Real-time (60s buffer) |
| **Storage** | 1 to 365 days retention | No retention (Delivery only) |
| **Destinations** | Custom Consumers (Lambda, EC2) | S3, Redshift, OpenSearch, Splunk |
