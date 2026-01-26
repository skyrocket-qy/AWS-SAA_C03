# AWS Savings Plans

**Savings Plans** is a flexible pricing model offering significant discounts in exchange for a monetary commitment ($/hour) for 1 or 3 years.

### Key Exam Points
- **Compute Savings Plans**: **Max Flexibility**. Applies to **EC2, Fargate, and Lambda** regardless of region, family, OS, or tenancy.
- **EC2 Instance Savings Plans**: **Max Discount** (up to 72%). Specific to an instance family within a region (e.g., M5 in us-east-1).
- **SageMaker Savings Plans**: Applies specifically to SageMaker usage.
- **vs. Reserved Instances**: Savings Plans are generally easier to manage and offer more flexibility (especially Compute plans covering Fargate/Lambda).
- **Scenario**: Choose **Compute Savings Plans** for mixed workloads (EC2 + Lambda) or when instance families/regions might change.
