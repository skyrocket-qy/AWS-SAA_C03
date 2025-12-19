# Amazon EC2 (Elastic Compute Cloud)

**Amazon EC2** provides resizable compute capacity in the cloud. It allows you to launch virtual servers (instances) with a variety of operating systems and configurations.

## Purchasing Options

### 1. On-Demand Instances
- **Description**: Pay for compute capacity by the second (minimum 60 seconds) with no long-term commitment.
- **Use Case**: Short-term, irregular, or spiky workloads that cannot be interrupted. App development and testing.
- **Cost**: Highest per-hour cost.

### 2. Spot Instances
- **Description**: Request spare computing capacity for up to **90% off** the On-Demand price.
- **Interruption**: AWS can terminate these instances with a **2-minute warning** if capacity is needed back.
- **Use Case**: Fault-tolerant, flexible, stateless applications.
    - Batch processing.
    - Big Data (Hadoop/Spark).
    - CI/CD pipelines.
    - High Performance Computing (HPC).
    - **NOT** for critical jobs or databases.
- **Strategies**:
    - **Spot Fleet**: A set of Spot Instances (and optionally On-Demand) that meets your target capacity. Helps diversify across instance types and AZs to reduce interruption risk.
        - **Allocation Strategies**:
            - `lowestPrice`: Launches instances from the pools with the lowest price (higher interruption risk).
            - `diversified`: Distributes instances across all Spot pools (balanced interruption risk).
            - `capacityOptimized`: Launches from pools with optimal capacity (lowest interruption risk).
            - `priceCapacityOptimized`: (Default for most use cases) Balances price and capacity availability.
        - **Request Types**: `request` (one-time) vs. `maintain` (keeps target capacity over time).
    - **Spot Block**: (Deprecated in some regions) Reserve for a specific duration (1-6 hours).

### 3. Reserved Instances (RI)
- **Description**: Significant discount (up to 72%) compared to On-Demand in exchange for a **1-year or 3-year term commitment**.
- **Payment Options**: No Upfront, Partial Upfront, All Upfront (higher upfront = deeper discount).
- **Types**:
    - **Standard RI**: Up to 72% off. Can change Availability Zone, instance size (for same OS family), networking type. **Cannot** change instance family.
    - **Convertible RI**: Up to 54% off. Can change instance family, OS, tenancy, and payment option. Gives flexibility to change to newer instance families.
    - **Scheduled RI**: Launch within time window (e.g., every Thursday).

### 4. Savings Plans
- **Description**: Commitment to a specific usage (measured in $/hour) for a 1 or 3-year term.
- **Types**:
    - **Compute Savings Plans**: Most flexible (up to 66% off). Applies regardless of family, Region, OS, or tenancy. Also applies to Fargate and Lambda.
    - **EC2 Instance Savings Plans**: Up to 72% off. Specific to instance family in a Region (e.g., M5 in us-east-1).

### 5. Dedicated Hosts / Instances
- **Dedicated Hosts**: Physical server dedicated to your use. Helps with compliance and server-bound software licenses.
- **Dedicated Instances**: Instances run on hardware dedicated to a single customer (isolated at hardware level).

## Exam Tips
- Use **Spot Instances** for any workload that can handle interruptions (max cost savings).
- Use **Reserved Instances (Standard)** for steady-state usage where requirements won't change.
- Use **Convertible RIs** if you need flexibility to change instance families later.
- Use **Compute Savings Plans** for maximum flexibility across Fargate and Lambda usage as well.
