# AWS Elastic Beanstalk

**AWS Elastic Beanstalk** is an easy-to-use service for deploying and scaling web applications and services developed with Java, .NET, PHP, Node.js, Python, Ruby, Go, and Docker on familiar servers such as Apache, Nginx, Passenger, and IIS.

## Key Features

- **Fast Deployment**: You can simply upload your code, and Elastic Beanstalk automatically handles the deployment—from capacity provisioning, load balancing, and auto-scaling to application health monitoring.
- **Full Control**: You retain full control over the AWS resources powering your application and can access the underlying resources at any time.
- **Cost**: There is no additional charge for Elastic Beanstalk. You pay only for the AWS resources (e.g., EC2 instances or S3 buckets) that you use to store and run your application.
- **Health Monitoring**: Collects 40+ key metrics and attributes to determine the health of your application.

## Components

- **Application**: A logical collection of Elastic Beanstalk components, including environments, versions, and environment configurations.
- **Application Version**: A specific, labeled iteration of deployable code (e.g., a JAVA WAR file).
- **Environment**: A version that is deployed onto AWS resources. There are two types:
    - **Web Server Environment**: Generally runs a standard web application.
    - **Worker Environment**: Generally runs background tasks that process messages from an SQS queue.

## Deployment Policies

Elastic Beanstalk supports several deployment strategies:
1.  **All at Once**: Deploys the new version to all instances simultaneously. Fastest, but results in downtime.
2.  **Rolling**: Deploys the new version in batches. One batch at a time is taken out of service, causing reduced capacity during the process.
3.  **Rolling with Additional Batch**: Deploys in batches but initiates a new batch of instances first to maintain full capacity.
4.  **Immutable**: Deploys the new version to a fresh group of instances in a separate Auto Scaling group. Once verified, the old instances are terminated. Zero downtime and safe fallback.
5.  **Blue/Green**: Not a direct feature of the console but achieved by swapping CNAMEs between two separate environments. Best for massive changes or database schema updates.

---

## Exam Tips

- **PaaS**: Elastic Beanstalk is a **Platform as a Service (PaaS)**. It is the best choice for developers who want to deploy code without worrying about infrastructure management.
- **Deployment Strategies**: Know the difference between **All at Once** (downtime), **Rolling** (reduced capacity), and **Immutable** (full capacity, zero downtime, most expensive/slowest).
- **Worker Tier**: If a question mentions a background task processing an **SQS queue**, the answer is the Elastic Beanstalk **Worker Tier**.
- **Configuration**: Extensions to Beanstalk are handled via `.ebextensions/` folder containing YAML or JSON files.
- **Customization**: Use **Docker** if your environment is not supported by standard Beanstalk platforms.
