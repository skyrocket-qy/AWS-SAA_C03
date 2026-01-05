# AWS X-Ray

**AWS X-Ray** helps developers debug and analyze strictly distributed applications, such as those built using a microservices architecture. It allows you to understand how your application and its underlying services are performing to identify and troubleshoot the root cause of performance issues and errors.

## Key Concepts
- **End-to-End Tracing**: Follows a request as it travels through your entire application specifically to spot bottlenecks.
- **Service Map**: Visualizes the relationships between services and resources in your application, displaying latency and failure rates for each connection.
- **Segments and Subsegments**:
    - **Segment**: Records information about the original request (time, source, etc.).
    - **Subsegment**: Breaks down the segment deeper, showing details about calls to downstream AWS services or external APIs.
- **Annotations and Metadata**:
    - **Annotations**: Key-value pairs indexed for search (e.g., `user_type: premium`).
    - **Metadata**: Key-value pairs NOT indexed (e.g., giant JSON debug payload).

## Architecture
- **X-Ray Daemon**: A software application that listens for traffic on UDP port 2000, buffers segment documents, and relays them to the AWS X-Ray API.
- **Integration**: Works seamlessly with EC2, ECS, Lambda, API Gateway, SNS, SQS, and Elastic Beanstalk.

## Exam Tips
- **Performance Bottlenecks**: If a question asks how to find **latency issues** or visualize where a specific request is failing in a complex microservices architecture, the answer is **X-Ray**.
- **Service Graph/Map**: Look for keywords like "visualize service dependencies" or "trace requests across multiple components".
- **Cross-Account Tracing**: X-Ray supports tracing requests across multiple AWS accounts.
