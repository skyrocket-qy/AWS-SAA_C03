# Amazon Kinesis

**Amazon Kinesis** services collect, process, and analyze real-time streaming data.

### Key Exam Points
- **Kinesis Data Streams (KDS)**: Real-time (200ms latency); data retention (24h to 365d); **manual scaling** via shards (partitions).
- **Kinesis Data Firehose**: Near real-time (**60s buffer**); **fully managed** (auto-scaling); delivers to S3, Redshift, OpenSearch, Splunk. No data retention.
- **Kinesis Data Analytics**: SQL or Flink-based analysis of streaming data in real-time.
- **Kinesis Video Streams**: Captures/processes video from devices for ML, etc.
- **Scenarios**: 
    - Need real-time/custom app? -> **Data Streams**.
    - Easiest way to S3/Redshift/OpenSearch? -> **Firehose**.
