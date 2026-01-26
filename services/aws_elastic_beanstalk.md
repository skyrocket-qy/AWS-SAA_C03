# AWS Elastic Beanstalk

**AWS Elastic Beanstalk** is a Platform-as-a-Service (PaaS) for deploying and scaling web applications.

### Key Exam Points
- **Automation**: Manages capacity, load balancing, scaling, and health monitoring.
- **Deployment Policies**:
    - **All at Once**: Fastest; involves downtime.
    - **Rolling**: Batch updates; reduced capacity during deployment.
    - **Immutable**: New ASG/Instances; Zero downtime; easy rollback; highest cost.
- **Environments**:
    - **Web Server**: Standard web apps.
    - **Worker Tier**: Background tasks via **SQS**.
- **Configuration**: Uses `.ebextensions/` files for customization.
- **Best For**: Developers who want to deploy code without managing infrastructure.
