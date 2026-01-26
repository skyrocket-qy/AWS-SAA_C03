# AWS Batch

**AWS Batch** runs containerized batch computing jobs across AWS Fargate, EC2, and Spot Instances.

### Key Exam Points
- **Use Case**: Long-running, compute-intensive jobs (financial analysis, genomics, rendering).
- **Core Components**: Jobs (unit of work), Job Definitions (blueprint), Job Queues (priority), Compute Environments (resources).
- **Cost Savings**: Native support for **Spot Instances**.
- **Batch vs. Lambda**: Use Batch for jobs > 15 minutes or tasks requiring specific Docker environments/heavy resources.
