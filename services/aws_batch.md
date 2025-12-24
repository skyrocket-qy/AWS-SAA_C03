# AWS Batch

**AWS Batch** enables developers, scientists, and engineers to easily and efficiently run hundreds of thousands of batch computing jobs on AWS. It dynamically provisions the optimal quantity and type of compute resources (e.g., CPU or memory optimized instances) based on the volume and specific resource requirements of the batch jobs submitted.

## Key Components

### 1. Jobs
- The unit of work (e.g., a shell script, a Linux executable, or a container image).
- Runs as a containerized application on AWS Fargate or Amazon EC2.

### 2. Job Definitions
- A template for jobs. Specifies:
    - Docker image
    - vCPU and Memory requirements
    - IAM Role
    - Environment variables
    - Mount points

### 3. Job Queues
- Where jobs reside until they are scheduled onto a compute environment.
- Can have priority (high priority queues get scheduled first).

### 4. Compute Environments
- The compute resources that run the jobs.
- **Managed Compute Environments**: AWS Batch manages the capacity (EC2 or Fargate). You specify instance types (or "optimal") and scaling limits (min/max vCPUs).
- **Unmanaged Compute Environments**: You manage your own EC2 instances.

## Key Features
- **Multi-node Parallel Jobs**: For tightly coupled workloads (e.g., MPI) that span multiple instances.
- **Dependencies**: Jobs can depend on other jobs (e.g., Job B starts only after Job A succeeds).
- **Scheduling**: Priority-based scheduling.
- **Cost Optimization**: Supports **Spot Instances** to reduce costs by up to 90%.

## Pricing
- No additional charge for AWS Batch itself.
- You pay for the underlying resources created (e.g., EC2 instances, Fargate tasks, Lambda functions).

## Use Cases
- **Financial Services**: High-performance computing for risk analysis, post-trade analytics.
- **Life Sciences**: DNA sequencing, drug screening.
- **Media & Entertainment**: Visual effects rendering, media transcoding.

## Exam Tips
- **AWS Batch vs Lambda**:
    - Use **Lambda** for short-running (< 15 min), event-driven tasks.
    - Use **Batch** for long-running, complex jobs (dockerized) that need extensive compute resources.
- **Compute Environments**: "Managed" is usually the right answer unless you need specific, unsupported configurations.
- **Spot Instances**: Great for batch jobs to save costs (Batch handles interruptions and retries if configured).
