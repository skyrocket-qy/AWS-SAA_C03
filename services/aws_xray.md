# AWS X-Ray

**AWS X-Ray** is a distributed tracing service that helps developers analyze and debug performance issues in microservices.

### Key Exam Points
- **Tracing**: Follows requests across multiple services and resources (EC2, ECS, Lambda, SNS, SQS).
- **Service Map**: Provides a visual graph of application components, showing latency and error rates.
- **Key Terms**:
    - **Segments**: Data about the original request.
    - **Subsegments**: Breakdown of internal calls (e.g., to DynamoDB or external APIs).
    - **Annotations**: Indexed key-value pairs used for **searching/filtering**.
    - **Metadata**: Non-indexed additional data.
- **Use Case**: Finding **bottlenecks**, high latency, or request failure points in complex architectures.
