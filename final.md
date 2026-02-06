# AWS Solutions Architect Associate (SAA-C03) - Complete Service Reference

## About This Document

This comprehensive reference guide covers all AWS services relevant to the AWS Certified Solutions Architect - Associate (SAA-C03) certification exam. Each service entry includes:

- **Function**: What the service does
- **Use Case**: Common scenarios where the service is used
- **Tips**: Key exam tips and important details to remember

---

## Table of Contents

- [Amazon API Gateway](#amazon-api-gateway)
- [Amazon AppFlow](#amazon-appflow)
- [Amazon Athena](#amazon-athena)
- [Amazon Aurora Serverless](#amazon-aurora-serverless)
- [Amazon Aurora](#amazon-aurora)
- [Amazon CloudFront](#amazon-cloudfront)
- [Amazon CloudWatch](#amazon-cloudwatch)
- [Amazon Cognito](#amazon-cognito)
- [Amazon Comprehend](#amazon-comprehend)
- [Amazon Detective](#amazon-detective)
- [Amazon DocumentDB (with MongoDB compatibility)](#amazon-documentdb-with-mongodb-compatibility)
- [Amazon DynamoDB](#amazon-dynamodb)
- [Amazon EC2 Auto Scaling](#amazon-ec2-auto-scaling)
- [Amazon EC2](#amazon-ec2)
- [Amazon ECS Anywhere](#amazon-ecs-anywhere)
- [Amazon EKS Anywhere](#amazon-eks-anywhere)
- [Amazon EKS Distro](#amazon-eks-distro)
- [Amazon Elastic Block Store (Amazon EBS)](#amazon-elastic-block-store-amazon-ebs)
- [Amazon Elastic Container Registry (Amazon ECR)](#amazon-elastic-container-registry-amazon-ecr)
- [Amazon Elastic Container Service (Amazon ECS)](#amazon-elastic-container-service-amazon-ecs)
- [Amazon Elastic File System (Amazon EFS)](#amazon-elastic-file-system-amazon-efs)
- [Amazon Elastic Kubernetes Service (Amazon EKS)](#amazon-elastic-kubernetes-service-amazon-eks)
- [Amazon Elastic Transcoder](#amazon-elastic-transcoder)
- [Amazon ElastiCache](#amazon-elasticache)
- [Amazon EMR](#amazon-emr)
- [Amazon EventBridge](#amazon-eventbridge)
- [Amazon Forecast](#amazon-forecast)
- [Amazon Fraud Detector](#amazon-fraud-detector)
- [Amazon FSx (for all types)](#amazon-fsx-for-all-types)
- [Amazon GuardDuty](#amazon-guardduty)
- [Amazon Inspector](#amazon-inspector)
- [Amazon Kendra](#amazon-kendra)
- [Amazon Keyspaces (for Apache Cassandra)](#amazon-keyspaces-for-apache-cassandra)
- [Amazon Kinesis Video Streams](#amazon-kinesis-video-streams)
- [Amazon Kinesis](#amazon-kinesis)
- [Amazon Lex](#amazon-lex)
- [Amazon Macie](#amazon-macie)
- [Amazon Managed Grafana](#amazon-managed-grafana)
- [Amazon Managed Service for Prometheus](#amazon-managed-service-for-prometheus)
- [Amazon Managed Streaming for Apache Kafka (Amazon MSK)](#amazon-managed-streaming-for-apache-kafka-amazon-msk)
- [Amazon MQ](#amazon-mq)
- [Amazon Neptune](#amazon-neptune)
- [Amazon OpenSearch Service](#amazon-opensearch-service)
- [Amazon Pinpoint](#amazon-pinpoint)
- [Amazon Polly](#amazon-polly)
- [Amazon Quantum Ledger Database (Amazon QLDB)](#amazon-quantum-ledger-database-amazon-qldb)
- [Amazon QuickSight](#amazon-quicksight)
- [Amazon RDS](#amazon-rds)
- [Amazon Redshift](#amazon-redshift)
- [Amazon Rekognition](#amazon-rekognition)
- [Amazon Route 53](#amazon-route-53)
- [Amazon S3 Glacier](#amazon-s3-glacier)
- [Amazon S3](#amazon-s3)
- [Amazon SageMaker](#amazon-sagemaker)
- [Amazon Simple Notification Service (Amazon SNS)](#amazon-simple-notification-service-amazon-sns)
- [Amazon Simple Queue Service (Amazon SQS)](#amazon-simple-queue-service-amazon-sqs)
- [Amazon Textract](#amazon-textract)
- [Amazon Transcribe](#amazon-transcribe)
- [Amazon Translate](#amazon-translate)
- [Amazon VPC](#amazon-vpc)
- [AWS Amplify](#aws-amplify)
- [AWS Application Discovery Service](#aws-application-discovery-service)
- [AWS Application Migration Service](#aws-application-migration-service)
- [AWS AppSync](#aws-appsync)
- [AWS Artifact](#aws-artifact)
- [AWS Audit Manager](#aws-audit-manager)
- [AWS Auto Scaling](#aws-auto-scaling)
- [AWS Backup](#aws-backup)
- [AWS Batch](#aws-batch)
- [AWS Budgets](#aws-budgets)
- [AWS Certificate Manager (ACM)](#aws-certificate-manager-acm)
- [AWS Client VPN](#aws-client-vpn)
- [AWS CloudFormation](#aws-cloudformation)
- [AWS CloudHSM](#aws-cloudhsm)
- [AWS CloudTrail](#aws-cloudtrail)
- [AWS Command Line Interface (AWS CLI)](#aws-command-line-interface-aws-cli)
- [AWS Compute Optimizer](#aws-compute-optimizer)
- [AWS Config](#aws-config)
- [AWS Control Tower](#aws-control-tower)
- [AWS Cost and Usage Report](#aws-cost-and-usage-report)
- [AWS Cost Explorer](#aws-cost-explorer)
- [AWS Data Exchange](#aws-data-exchange)
- [AWS Data Pipeline](#aws-data-pipeline)
- [AWS Database Migration Service (AWS DMS)](#aws-database-migration-service-aws-dms)
- [AWS DataSync](#aws-datasync)
- [AWS Device Farm](#aws-device-farm)
- [AWS Direct Connect](#aws-direct-connect)
- [AWS Directory Service](#aws-directory-service)
- [AWS Elastic Beanstalk](#aws-elastic-beanstalk)
- [AWS Fargate](#aws-fargate)
- [AWS Firewall Manager](#aws-firewall-manager)
- [AWS Global Accelerator](#aws-global-accelerator)
- [AWS Glue](#aws-glue)
- [AWS Health Dashboard](#aws-health-dashboard)
- [AWS IAM Identity Center (AWS Single Sign-On)](#aws-iam-identity-center-aws-single-sign-on)
- [AWS Identity and Access Management (IAM)](#aws-identity-and-access-management-iam)
- [AWS Key Management Service (AWS KMS)](#aws-key-management-service-aws-kms)
- [AWS Lake Formation](#aws-lake-formation)
- [AWS Lambda](#aws-lambda)
- [AWS License Manager](#aws-license-manager)
- [AWS Management Console](#aws-management-console)
- [AWS Migration Hub](#aws-migration-hub)
- [AWS Network Firewall](#aws-network-firewall)
- [AWS Organizations](#aws-organizations)
- [AWS Outposts](#aws-outposts)
- [AWS PrivateLink](#aws-privatelink)
- [AWS Proton](#aws-proton)
- [AWS Resource Access Manager (AWS RAM)](#aws-resource-access-manager-aws-ram)
- [AWS Secrets Manager](#aws-secrets-manager)
- [AWS Security Hub](#aws-security-hub)
- [AWS Serverless Application Repository](#aws-serverless-application-repository)
- [AWS Service Catalog](#aws-service-catalog)
- [AWS Shield](#aws-shield)
- [AWS Site-to-Site VPN](#aws-site-to-site-vpn)
- [AWS Snow Family](#aws-snow-family)
- [AWS Step Functions](#aws-step-functions)
- [AWS Storage Gateway](#aws-storage-gateway)
- [AWS Systems Manager](#aws-systems-manager)
- [AWS Transfer Family](#aws-transfer-family)
- [AWS Transit Gateway](#aws-transit-gateway)
- [AWS Trusted Advisor](#aws-trusted-advisor)
- [AWS WAF](#aws-waf)
- [AWS Wavelength](#aws-wavelength)
- [AWS Well-Architected Tool](#aws-well-architected-tool)
- [AWS X-Ray](#aws-x-ray)
- [Elastic Load Balancing (ELB)](#elastic-load-balancing-elb)
- [Savings Plans](#savings-plans)
- [VMware Cloud on AWS](#vmware-cloud-on-aws)

---

# Amazon API Gateway

### Function
Fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale.

### Use Case
- Exposing Lambda functions as REST or HTTP APIs.
- API proxy for external or internal services.
- Throttling and securing access to backend services.

### Tips
- Supports RESTful APIs and WebSocket APIs.
- Throttling, caching, and authentication (Cognito/IAM).
- Direct integration with many AWS services.


---

# Amazon AppFlow

### Function
Fully managed integration service that enables you to securely transfer data between Software as a Service (SaaS) applications like Salesforce, SAP, Zendesk, Slack, and ServiceNow, and AWS services like Amazon S3 and Amazon Redshift.

### Use Case
- Importing Salesforce records into S3 weekly.
- Sending AWS data to Slack.
- Backing up SaaS data to S3.

### Tips
- SaaS-to-AWS integration without code.
- Supports AWS PrivateLink for security.
- Trigger flows on schedule, on event, or on demand.


---

# Amazon Athena

### Function
Serverless interactive query service that makes it easy to analyze data in Amazon S3 using standard SQL.

### Use Case
- Querying logs stored in S3 (e.g., VPC Flow Logs, CloudTrail logs).
- Ad-hoc analysis of data lakes stored in S3 without managing servers.

### Tips
- Pay-per-query (data scanned).
- Use columnar formats like Parquet/ORC and partition data to save costs.
- Serverless, no infrastructure to manage.


---

# Amazon Aurora Serverless

### Function
On-demand, auto-scaling configuration for Amazon Aurora where the database will automatically start up, shut down, and scale capacity up or down based on your application's needs.

### Use Case
- Applications with unpredictable or infrequent traffic.
- Non-production environments (Dev/Test).
- Scaling capacity instantly for traffic spikes.

### Tips
- Scale by ACUs (Aurora Capacity Units).
- Aurora Serverless v2 scales in fractions of a second.
- Cost-effective for variable workloads.


---

# Amazon Aurora

### Function
MySQL and PostgreSQL-compatible relational database built for the cloud, that combines the performance and availability of traditional enterprise databases with the simplicity and cost-effectiveness of open source databases.

### Use Case
- High-performance relational workloads.
- Applications requiring high availability and durability (6-way replication).
- Global scale applications.

### Tips
- Auto-scaling storage.
- Aurora Global Database for cross-region disaster recovery.
- Up to 15 read replicas.
- Aurora Serverless for unpredictable workloads.


---

# Amazon CloudFront

### Function
Fast content delivery network (CDN) service that securely delivers data, videos, applications, and APIs to customers globally with low latency, high transfer speeds, all within a developer-friendly environment.

### Use Case
- Caching static website assets at edge locations.
- Low-latency video streaming.
- DDOS protection (integrated with Shield/WAF).

### Tips
- Edge Locations vs. Regional Edge Caches.
- TTL (Time to Live) and Invalidation.
- Lambda@Edge / CloudFront Functions for logic at the edge.
- Origins: S3, ELB, EC2, custom origins.


---

# Amazon CloudWatch

### Function
Monitoring and observability service built for DevOps engineers, developers, site reliability engineers (SREs), and IT managers.

### Use Case
- Monitoring resource utilization (CPU, memory via Agent).
- Centralized logging (CloudWatch Logs).
- Alerting via CloudWatch Alarms.

### Tips
- Metrics (Standard/Custom).
- Logs (Log Groups, Log Streams).
- Alarms (Static, Anomaly Detection).
- Events (replaced by EventBridge).
- Agent required for memory/disk metrics.


---

# Amazon Cognito

### Function
Service that lets you add user sign-up, sign-in, and access control to your web and mobile apps quickly and easily.

### Use Case
- Managing a user directory for a mobile application (User Pools).
- Granting temporary AWS credentials to external users (Identity Pools).

### Tips
- User Pools (Authentication/Profile).
- Identity Pools (Authorization for AWS resources).
- Supports social logins and SAML/OIDC.


---

# Amazon Comprehend

### Function
Natural language processing (NLP) service that uses machine learning to find insights and relationships in text.

### Use Case
- Sentiment analysis of customer reviews.
- Topic modeling of support tickets.
- Extracting entities (people, places, brands) from documents.

### Tips
- Serverless NLP.
- Supports personally identifiable information (PII) identification.


---

# Amazon Detective

### Function
Service that makes it easy to analyze, investigate, and quickly identify the root cause of potential security issues or suspicious activities.

### Use Case
- Investigating security findings from GuardDuty or Security Hub.

### Tips
- Uses graph graphs and ML to visualize connections between security events.


---

# Amazon DocumentDB (with MongoDB compatibility)

### Function
Fast, scalable, highly available, and fully managed enterprise document database service that supports MongoDB workloads.

### Use Case
- Content management systems.
- Personalization and recommendations.
- Storing JSON-like document data at scale.

### Tips
- Fully managed, MongoDB compatible.
- Decoupled storage and compute.
- Supports MongoDB 3.6, 4.0, and 5.0 APIs.


---

# Amazon DynamoDB

### Function
Key-value and document database that delivers single-digit millisecond performance at any scale.

### Use Case
- High-traffic web applications (sessions, shopping carts).
- Mobile backends.
- IoT metadata storage.

### Tips
- NoSQL, serverless.
- Global Tables for multi-region active-active replication.
- DAX (DynamoDB Accelerator) for microsecond latency.
- On-demand or Provisioned capacity modes.


---

# Amazon EC2 Auto Scaling

### Function
Service that helps you maintain application availability and allows you to automatically add or remove EC2 instances according to conditions you define.

### Use Case
- Automatically scaling a web server fleet based on CPU usage.
- Ensuring a minimum number of instances are always running.
- Predicting and handling traffic spikes.

### Tips
- Target Tracking, Step Scaling, Scheduled Scaling, Predictive Scaling.
- Balance instances across AZs.
- Uses Launch Templates (preferred) or Launch Configurations.


---

# Amazon EC2

### Function
Web service that provides secure, resizable compute capacity in the cloud.

### Use Case
- Hosting web applications or databases.
- Custom software server instances.
- Any workload requiring OS-level control.

### Tips
- Instance Families (General Purpose, Compute Optimized, Memory Optimized, etc.).
- Pricing: On-Demand, Spot, Reserved, Dedicated Hosts/Instances.
- EBS-backed for persistence.


---

# Amazon ECS Anywhere

### Function
Feature of Amazon Elastic Container Service (Amazon ECS) that enables you to run and manage containerized applications on-premises using the same APIs, cluster management, workload scheduling, and monitoring that you use in AWS today.

### Use Case
- Managing containers on-premises and in AWS with a single control plane.
- Hybrid container management.

### Tips
- Requires ECS Agent on-premises.
- Consistent management interface for all containers.


---

# Amazon EKS Anywhere

### Function
Deployment option for Amazon EKS that enables you to easily create and operate Kubernetes clusters on-premises, including on your own virtual machines (VMs) and bare metal servers.

### Use Case
- Consistent Kubernetes experience across on-premises and AWS.

### Tips
- Open-source Kubernetes distribution.
- Supports VMware vSphere and bare metal.


---

# Amazon EKS Distro

### Function
Distribution of the same open source Kubernetes and dependencies used by Amazon EKS.

### Use Case
- Running the exact same Kubernetes version as EKS in your own self-managed environments.

### Tips
- Open source project from AWS.
- Includes patches and updates from EKS.


---

# Amazon Elastic Block Store (Amazon EBS)

### Function
High-performance block storage service designed for use with Amazon Elastic Compute Cloud (EC2) for both throughput and transaction-intensive workloads.

### Use Case
- Root volume for an EC2 instance.
- Highly available and reliable storage for databases.

### Tips
- Types: gp2/gp3 (general), io1/io2 (high performance), st1 (throughput), sc1 (cold storage).
- Snapshots are incremental and stored in S3.


---

# Amazon Elastic Container Registry (Amazon ECR)

### Function
Fully managed Docker container registry that makes it easy for developers to store, manage, and deploy Docker container images.

### Use Case
- Storing Docker images for use in ECS, EKS, or Lambda.
- Scanning container images for vulnerabilities.

### Tips
- Private/Public repositories.
- Integrated with IAM for access control.
- Image tag mutability controls.


---

# Amazon Elastic Container Service (Amazon ECS)

### Function
Highly scalable, high-performance container orchestration service that supports Docker containers and allows you to easily run and scale containerized applications on AWS.

### Use Case
- Running microservices in containers.
- Batch processing using Docker.
- Scalable web applications.

### Tips
- Launch types: Fargate (serverless) or EC2.
- Capacity Providers for scaling.
- Deeply integrated with AWS (IAM, VPC, CloudWatch).


---

# Amazon Elastic File System (Amazon EFS)

### Function
Simple, serverless, set-and-forget, elastic file system that lets you share file data without provisioning or managing storage.

### Use Case
- Shared storage for multiple EC2 instances (Content Management Systems, home directories).
- Container storage (ECS/EKS/Lambda).

### Tips
- NFSv4 protocol.
- Regional availability (3+ AZs) or One Zone.
- Serverless, grows and shrinks automatically.


---

# Amazon Elastic Kubernetes Service (Amazon EKS)

### Function
Managed service that makes it easy for you to run Kubernetes on AWS without needing to stand up or maintain your own Kubernetes control plane or nodes.

### Use Case
- Running cloud-native applications with Kubernetes.
- Migrating existing Kubernetes workloads to AWS.
- Standardizing container orchestration with open source.

### Tips
- Managed Control Plane.
- Fargate or EC2 worker nodes.
- Supports standard kubectl tools.


---

# Amazon Elastic Transcoder

### Function
Media transcoding in the cloud. It is designed to be a highly scalable, easy to use and a cost effective way for developers and businesses to convert (or transcode) media files from their source format into versions that will playback on devices like smartphones, tablets and PCs.

### Use Case
- Converting video files into different formats for mobile/web playback.

### Tips
- Managed transcoding.
- Legacy service (prefer AWS Elemental MediaConvert for newer workloads).


---

# Amazon ElastiCache

### Function
Fully managed, Redis- and Memcached-compatible service that provides seamless, high-performance, in-memory caching in the AWS Cloud.

### Use Case
- Database caching (reducing load on RDS).
- Session storage for web apps.
- Real-time leaderboards (Redis).

### Tips
- Redis (advanced data structures, HA) vs Memcached (simple, multithreaded).
- Improves read latency significantly.


---

# Amazon EMR

### Function
Industry-leading cloud big data platform for processing vast amounts of data using open source tools such as Apache Spark, Apache Hive, Apache HBase, Apache Flink, Apache Hudi, and Presto.

### Use Case
- Big data processing and analysis.
- Machine learning workflows on large datasets.
- Financial modeling and genomic research.

### Tips
- EMR uses EC2 instances (usually M or C families).
- Use Spot Instances for workers to save costs.
- Decouple storage (S3) from compute (EMR) using EMRFS.


---

# Amazon EventBridge

### Function
Serverless event bus that makes it easier to build event-driven applications at scale using events generated from your applications, integrated SaaS applications, and AWS services.

### Use Case
- Triggering a Lambda function when an EC2 instance changes state.
- Automating workflows based on SaaS events (e.g., Zendesk ticket update).
- Building a decoupled, event-driven architecture.

### Tips
- Successor to CloudWatch Events.
- Supports third-party SaaS event integration.
- Schema Registry for easier application development.


---

# Amazon Forecast

### Function
Fully managed service that uses machine learning to deliver highly accurate forecasts.

### Use Case
- Forecasting inventory demand.
- Predicting financial metrics.
- Planning resource requirements.

### Tips
- Uses time-series data.
- Automatically selects the best ML algorithm for the data.


---

# Amazon Fraud Detector

### Function
Fully managed service that makes it easy to identify potentially fraudulent online activities, such as online payment fraud and the creation of fake accounts.

### Use Case
- Detecting fake account signups.
- Identifying suspicious credit card transactions.

### Tips
- Uses historical data to train fraud models.
- Integrated with AWS CloudTrail and other services.


---

# Amazon FSx (for all types)

### Function
Fully managed third-party file systems for a wide range of workloads.

### Use Case
- Windows file shares (FSx for Windows).
- High Performance Computing (FSx for Lustre).
- Migration of NetApp or OpenZFS storage.

### Tips
- FSx for Windows (SMB), Lustre (HPC), NetApp ONTAP, OpenZFS.


---

# Amazon GuardDuty

### Function
Threat detection service that continuously monitors for malicious activity and unauthorized behavior to protect your AWS accounts, workloads, and data stored in Amazon S3.

### Use Case
- Detecting compromised EC2 instances or mining activity.
- Monitoring for unauthorized IAM access patterns.

### Tips
- Uses VPC Flow Logs, CloudTrail Logs, and DNS Logs.
- Intelligent threat detection using ML.


---

# Amazon Inspector

### Function
Automated security assessment service that helps improve the security and compliance of applications deployed on AWS.

### Use Case
- Scanning EC2 instances and ECR container images for software vulnerabilities.

### Tips
- Automated vulnerability management.
- Different from GuardDuty (threat detection) vs. Inspector (vulnerability scanning).


---

# Amazon Kendra

### Function
Intelligent search service powered by machine learning.

### Use Case
- Searching internal corporate documentation and knowledge bases.
- Improving search results for customer support pages.

### Tips
- NLP-powered enterprise search.
- Natural language query support (e.g., 'What is the holiday policy?').


---

# Amazon Keyspaces (for Apache Cassandra)

### Function
Scalable, highly available, and managed Apache Cassandra–compatible database service.

### Use Case
- Migrating Cassandra workloads to a managed serverless service.

### Tips
- Compatible with Cassandra Query Language (CQL).
- Serverless capacity mode available.


---

# Amazon Kinesis Video Streams

### Function
Service that makes it easy to securely stream video from connected devices to AWS for analytics, machine learning (ML), playback, and other processing.

### Use Case
- Ingesting video from IoT cameras for real-time analysis.
- Storing video for playback in surveillance applications.

### Tips
- Supports WebRTC for two-way media streaming.
- Highly scalable ingestion for millions of devices.


---

# Amazon Kinesis

### Function
Platform for streaming data on AWS, offering powerful services to make it easy to load and analyze streaming data, and also providing the ability for you to build custom streaming data applications for specialized needs.

### Use Case
- Real-time log collection from thousands of instances.
- Real-time analytics on social media feeds.
- IoT data ingestion and processing.

### Tips
- Data Streams: Real-time, sharded, data retained 24h-365d.
- Data Firehose: Near real-time, loads data into S3/Redshift/OpenSearch/Splunk.
- Data Analytics: SQL/Flink on streaming data.
- Video Streams: For video recording/processing.


---

# Amazon Lex

### Function
Fully managed service for building conversational interfaces for any application using voice and text.

### Use Case
- Building chatbots for customer service.
- Voice-controlled applications (Alexa-like tech).

### Tips
- The technology behind Alexa.
- Integrated with Lambda for backend logic.
- Commonly paired with Polly and Transcribe.


---

# Amazon Macie

### Function
Fully managed data security and data privacy service that uses machine learning and pattern matching to discover and protect your sensitive data in AWS.

### Use Case
- Finding PII (Personally Identifiable Information) in S3 buckets.
- Auditing S3 bucket security settings.

### Tips
- Focuses specifically on data in S3.
- Alerts on exposed or unencrypted sensitive data.


---

# Amazon Managed Grafana

### Function
Fully managed service for open source Grafana, a popular open source analytics platform that enables you to query, visualize, and alert on your metrics, logs, and traces.

### Use Case
- Visualizing metrics from CloudWatch, Prometheus, and external sources.
- Creating advanced operational dashboards.

### Tips
- Managed Grafana infrastructure.
- Deeply integrated with AWS IAM Identity Center.


---

# Amazon Managed Service for Prometheus

### Function
Prometheus-compatible monitoring service that makes it easy to monitor containerized applications at scale.

### Use Case
- Monitoring EKS or ECS clusters using Prometheus metrics.
- Scaling Prometheus monitoring automatically.

### Tips
- Fully managed, scalable Prometheus.
- Uses same query language (PromQL).


---

# Amazon Managed Streaming for Apache Kafka (Amazon MSK)

### Function
Fully managed service that makes it easy for you to build and run applications that use Apache Kafka to process streaming data.

### Use Case
- Migrating existing Kafka workloads to AWS.
- Building real-time stream processing applications using Kafka APIs.
- Decoupling microservices.

### Tips
- Managed Kafka infrastructure.
- Easier to manage than self-hosted Kafka on EC2.
- High availability across multiple AZs.


---

# Amazon MQ

### Function
Managed message broker service for Apache ActiveMQ and RabbitMQ that makes it easy to set up and operate message brokers in the cloud.

### Use Case
- Migrating existing applications using industry-standard messaging protocols (JMS, NMS, AMQP, STOMP, MQTT, WebSocket).
- Hybrid cloud messaging between on-premises and AWS.

### Tips
- Supports industry standards (ActiveMQ/RabbitMQ).
- Use for legacy migrations; for new cloud-native apps, prefer SQS/SNS.


---

# Amazon Neptune

### Function
Fast, reliable, fully managed graph database service that makes it easy to build and run applications that work with highly connected datasets.

### Use Case
- Fraud detection.
- Social networking features.
- Knowledge graphs.

### Tips
- Supports property graphs (TinkerPop) and W3C RDF metadata.
- Highly available with up to 15 replicas.


---

# Amazon OpenSearch Service

### Function
Successor to Amazon Elasticsearch Service; a managed service that makes it easy to deploy, operate, and scale OpenSearch for log analytics, full-text search, and more.

### Use Case
- Application monitoring and log analytics (ELK stack).
- Real-time search and filtering for websites.
- Security information and event management (SIEM).

### Tips
- Includes OpenSearch Dashboards (formerly Kibana).
- Good for full-text search and complex aggregations.
- Managed service for high volume search.


---

# Amazon Pinpoint

### Function
AWS’s flexible and scalable outbound and inbound marketing communication service.

### Use Case
- Sending personalized push notifications, SMS, or emails for marketing campaigns.
- Customer segmentation and engagement tracking.
- A/B testing marketing messages.

### Tips
- Multi-channel communication (Email, SMS, Push, Voice).
- Differentiate from SNS (simple pub/sub) and SES (bulk email).


---

# Amazon Polly

### Function
Service that turns text into lifelike speech, allowing you to create applications that talk, and build entirely new categories of speech-enabled products.

### Use Case
- Converting blog posts to audio podcasts.
- Voice output for automated phone systems.

### Tips
- Text-to-Speech (TTS).
- Supports SSML for fine-grained control of speech (pitch, rate, etc.).


---

# Amazon Quantum Ledger Database (Amazon QLDB)

### Function
Fully managed ledger database that provides a transparent, immutable, and cryptographically verifiable transaction log owned by a central trusted authority.

### Use Case
- Supply chain tracking.
- Financial transaction history.
- HR records and asset ownership.

### Tips
- Immutable and verifiable.
- Centralized (not decentralized like blockchain).
- SQL-like interface (PartiQL).


---

# Amazon QuickSight

### Function
Scalable, serverless, embeddable, machine learning-powered business intelligence (BI) service built for the cloud.

### Use Case
- Creating interactive dashboards to visualize business data.
- Performing ad-hoc analysis of data from RDS, Redshift, S3, or Athena.
- Embedding analytics into applications.

### Tips
- SPICE engine (Super-fast, Parallel, In-memory Calculation Engine) for performance.
- Per-user pricing.
- Serverless BI.


---

# Amazon RDS

### Function
Service that makes it easy to set up, operate, and scale a relational database in the cloud.

### Use Case
- Standard relational database needs (MySQL, PostgreSQL, Oracle, SQL Server, MariaDB).
- Apps where you need managed backups, patching, and scaling.

### Tips
- Multi-AZ for high availability (failover).
- Read Replicas for read scaling (not HA).
- RDS Proxy for Lambda connection pooling.


---

# Amazon Redshift

### Function
Fast, fully managed, petabyte-scale data warehouse that makes it simple and cost-effective to analyze all your data using standard SQL and your existing Business Intelligence (BI) tools.

### Use Case
- Enterprise data warehousing and reporting.
- Analyzing structured data from different sources with high performance.
- Complex SQL queries on large datasets.

### Tips
- Columnar storage for fast OLAP.
- Redshift Spectrum queries data directly in S3.
- Dense Compute (SSD) for performance, Dense Storage (HDD) for volume.
- Concurrently scale with Redshift Serverless.


---

# Amazon Rekognition

### Function
Service that makes it easy to add image and video analysis to your applications.

### Use Case
- Face detection and matching for security.
- Object and scene detection in images.
- Identifying inappropriate content (content moderation).

### Tips
- Image and video ML analysis.
- Includes Celebrity Recognition and Text-in-image detection.


---

# Amazon Route 53

### Function
Highly available and scalable cloud Domain Name System (DNS) web service.

### Use Case
- Domain registration.
- Routing users to different endpoints based on routing policies.
- DNS Health Checks and failover.

### Tips
- Routing Policies: Simple, Weighted, Latency-based, Failover, Geolocation, Geoproximity, Multi-value Answer.
- Alias records (pointing to AWS resources).


---

# Amazon S3 Glacier

### Function
Extremely low-cost Amazon S3 storage classes for data archiving and long-term backup.

### Use Case
- Long-term archival for regulatory data.
- Backup data that is rarely accessed.

### Tips
- Glacier Instant Retrieval (milliseconds), Glacier Flexible Retrieval (minutes to hours), Glacier Deep Archive (12+ hours).


---

# Amazon S3

### Function
Object storage service that offers industry-leading scalability, data availability, security, and performance.

### Use Case
- Static website hosting.
- Data lake storage.
- Backups and archiving.

### Tips
- Classes: Standard, Intelligent-Tiering, Standard-IA, One Zone-IA, Glacier (Instant/Flexible/Deep).
- Versions, Replication, Lifecycle policies.
- Strong Read-after-Write consistency.


---

# Amazon SageMaker

### Function
Fully managed service that provides every developer and data scientist with the ability to build, train, and deploy machine learning (ML) models quickly.

### Use Case
- End-to-end ML model development.
- Deploying high-performance ML inference endpoints.
- Data labeling and preparation (Ground Truth).

### Tips
- Broad set of ML tools (Studio, Notebooks, Processing, Training, Hosting).
- Supports open source frameworks (TensorFlow, PyTorch, etc.).


---

# Amazon Simple Notification Service (Amazon SNS)

### Function
Highly available, durable, secure, fully managed pub/sub messaging service that enables you to decouple microservices, distributed systems, and serverless applications.

### Use Case
- Fan-out messaging to multiple SQS queues.
- Sending SMS, push notifications, or emails to end-users.
- Decoupling microservices where one event needs multiple reactions.

### Tips
- Pub/Sub model.
- SMS, Email, Mobile Push, HTTP/S, Lambda, SQS endpoints.
- Topic-based filtering.


---

# Amazon Simple Queue Service (Amazon SQS)

### Function
Fully managed message queuing service that enables you to decouple and scale microservices, distributed systems, and serverless applications.

### Use Case
- Decoupling producers and consumers in a web application.
- Handling spike loads by buffering requests.
- Asynchronous task processing.

### Tips
- Standard Queues (at-least-once delivery, best-effort ordering).
- FIFO Queues (exact once, first-in-first-out).
- Visibility Timeout (item hidden while being processed).
- Dead Letter Queues (DLQ) for failed messages.


---

# Amazon Textract

### Function
Machine learning service that automatically extracts text, handwriting, and data from scanned documents.

### Use Case
- Digitizing scanned forms and invoices.
- Extracting data from tables and forms automatically.

### Tips
- Goes beyond simple OCR (understands document structure/tables).
- Highly accurate text extraction.


---

# Amazon Transcribe

### Function
Automatic speech recognition (ASR) service that makes it easy for developers to add speech-to-text capability to their applications.

### Use Case
- Transcribing recorded customer calls.
- Generating subtitles for video content.
- Creating searchable transcripts of meetings.

### Tips
- Speech-to-Text.
- Supports multi-channel audio and speaker identification.


---

# Amazon Translate

### Function
Neural machine translation service for fast, high-quality, and affordable language translation.

### Use Case
- Translating website content for global audiences.
- Real-time chat translation in multilingual applications.

### Tips
- Neural Machine Translation (NMT).
- Supports many languages and automatic language detection.


---

# Amazon VPC

### Function
Service that lets you provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define.

### Use Case
- Isolating application tiers for security.
- Defining custom IP address ranges and subnets.

### Tips
- Subnets (Public/Private).
- Route Tables, Internet Gateway (IGW), NAT Gateway (Public to Private traffic).
- Security Groups (Stateful) vs. NACLs (Stateless).
- VPC Flow Logs.


---

# AWS Amplify

### Function
Set of tools and services that can be used together or on their own, to help front-end web and mobile developers build scalable full stack applications, powered by AWS.

### Use Case
- Fast setup of web/mobile backends and hosting.
- Frontend-driven development for full stack apps.
- Continuous deployment for static websites.

### Tips
- Includes libraries, CLI, and hosting UI components.
- Ideal for rapid prototyping and front-end developers.


---

# AWS Application Discovery Service

### Function
Service that helps enterprise customers plan modernization and migration projects by gathering information about their on-premises data centers.

### Use Case
- Inventorying on-premises servers and their dependencies for migration planning.

### Tips
- Agentless (vCenter) or Agent-based (OS-level).
- Mapping server dependencies.


---

# AWS Application Migration Service

### Function
Primary migration service Recommended for lift-and-shift migrations to AWS.

### Use Case
- Migrating on-premises servers to EC2 with minimal downtime (Rehost).

### Tips
- Formerly MGN (CloudEndure technology).
- Continuous block-level replication.


---

# AWS AppSync

### Function
Managed service that uses GraphQL to make it easy for applications to get exactly the data they need.

### Use Case
- Building real-time mobile and web apps with offline capabilities.
- Aggregating data from multiple local and remote data sources into a single API.
- Collaborative applications with real-time updates.

### Tips
- GraphQL based.
- Real-time subscriptions (WebSocket).
- Works well with DynamoDB, Lambda, and OpenSearch.


---

# AWS Artifact

### Function
Self-service portal for on-demand access to AWS’s compliance reports and select online agreements.

### Use Case
- Downloading SOC, ISO, or PCI reports for auditing purposes.
- Accepting Business Associate Addendum (BAA) for HIPAA compliance.

### Tips
- The 'go-to' for compliance documentation.


---

# AWS Audit Manager

### Function
Service that helps you continuously audit your AWS usage to simplify how you assess risk and compliance with regulations and industry standards.

### Use Case
- Automating evidence collection for audits.

### Tips
- Managed service for continuous compliance monitoring.


---

# AWS Auto Scaling

### Function
Service that monitors your applications and automatically adjusts capacity to maintain steady, predictable performance at the lowest possible cost.

### Use Case
- Managing groups of resources (ASG, ECS, DynamoDB, Spot Fleets) collectively.
- Using a single scaling plan for a multi-resource application suite.

### Tips
- Different from EC2 Auto Scaling (which is specific to instances).
- Provides a unified interface for scaling multiple resources.


---

# AWS Backup

### Function
Fully managed backup service that makes it easy to centralize and automate the back up of data across AWS services.

### Use Case
- Centralizing backup policies for EBS volumes, RDS databases, DynamoDB tables, EFS file systems, and Storage Gateway volumes.

### Tips
- Supports cross-region and cross-account backup.
- Policy-based management.


---

# AWS Batch

### Function
Fully managed batch processing service that enables developers, scientists, and engineers to easily and efficiently run hundreds of thousands of batch computing jobs on AWS.

### Use Case
- Running large-scale simulations or image processing tasks.
- High-performance computing (HPC) jobs.
- Long-running Docker container jobs.

### Tips
- Serverless (using Fargate) or EC2-based.
- Handles job dependencies and sequencing.
- Integrated with Spot Instances for cost savings.


---

# AWS Budgets

### Function
Service to set custom budgets to track cost and usage, providing alerts when thresholds are exceeded.

### Use Case
- Alerting when monthly spending exceeds a specific dollar amount.
- Monitoring RI/Savings Plans utilization and coverage.
- Triggering actions (e.g., stopping instances) when a budget is exceeded.

### Tips
- Proactive alerting based on actual OR forecasted costs.
- Actions via SNS or Systems Manager.
- Budgets is for planning; Cost Explorer is for historical analysis.


---

# AWS Certificate Manager (ACM)

### Function
Service that makes it easy to provision, manage, and deploy public and private Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificates for use with AWS services.

### Use Case
- Automating SSL certificate renewal for an ALB or CloudFront.

### Tips
- Free for public certificates used on AWS resources.
- Automates renewal process.


---

# AWS Client VPN

### Function
Managed client-based VPN service that enables you to securely access your AWS resources and resources in your on-premises network.

### Use Case
- Allowing remote employees to access application servers in a private VPC.

### Tips
- OpenVPN-based client.
- Scalable and fully managed.


---

# AWS CloudFormation

### Function
Service that gives developers and businesses an easy way to create a collection of related AWS and third-party resources, and provision and manage them in an orderly and predictable fashion.

### Use Case
- Infrastructure as Code (IaC).
- Standardizing deployments across accounts and regions.
- Automating the rollout of complex multi-tier applications.

### Tips
- Templates (YAML/JSON).
- StackSets (for cross-account/region deployment).
- Drift Detection (identify manual changes).
- Rollback on failure.


---

# AWS CloudHSM

### Function
Cloud-based hardware security module (HSM) that enables you to easily generate and use your own encryption keys on the AWS Cloud.

### Use Case
- Workloads requiring FIPS 140-2 Level 3 compliance.
- Scenarios where the customer must have exclusive control of HSM instances.

### Tips
- Single-tenant hardware.
- User-managed; high operational overhead compared to KMS.


---

# AWS CloudTrail

### Function
Service that enables governance, compliance, operational auditing, and risk auditing of your AWS account.

### Use Case
- Auditing 'who did what' via AWS API calls.
- Compliance logging and reporting.
- Troubleshooting operational issues by tracking resource changes.

### Tips
- Enabled by default (90 days history).
- Management Events vs. Data Events (S3/Lambda).
- Store logs in S3 or CloudWatch Logs for analysis.


---

# AWS Command Line Interface (AWS CLI)

### Function
Unified tool to manage your AWS services from the terminal.

### Use Case
- Automating AWS administrative tasks.
- Scripting resource management.

### Tips
- Uses Access Key and Secret Key for authentication.
- Standard way to interact with AWS from scripts.


---

# AWS Compute Optimizer

### Function
Service that recommends optimal AWS resources for your workloads to reduce costs and improve performance by using machine learning to analyze historical utilization metrics.

### Use Case
- Identifying over-provisioned EC2 instances to save costs.
- Finding memory-constrained Lambda functions.

### Tips
- Analyzes CloudWatch metrics.
- Free to use (with some advanced options).
- Available for EC2, EBS, Lambda, Fargate.


---

# AWS Config

### Function
Service that enables you to assess, audit, and evaluate the configurations of your AWS resources.

### Use Case
- Tracking resource configuration history over time.
- Ensuring compliance via Config Rules (e.g., 'all S3 buckets must be encrypted').
- Continuous auditing and automated remediation.

### Tips
- Compliance-oriented service.
- Used for 'Detective' guardrails.
- Integrates with AWS Systems Manager for remediation.


---

# AWS Control Tower

### Function
Service that provides the easiest way to set up and govern a secure, multi-account AWS environment, based on best practices.

### Use Case
- Setting up a Landing Zone for a large organization.
- Applying guardrails (preventive and detective) across multiple accounts.
- Centralizing multi-account governance.

### Tips
- Orchestrates other services (Organizations, CloudFormation, SSO).
- Standardizes account setup.


---

# AWS Cost and Usage Report

### Function
The most comprehensive set of AWS cost and usage data available, including additional metadata about AWS services, pricing, and reservations.

### Use Case
- Detailed cost analysis using Athena or QuickSight.
- Internal cost allocation and chargeback to departments.
- Granular auditing of AWS spend at the resource level.

### Tips
- Most granular data available (hourly/resource ID).
- Delivered to S3.
- Integrates with QuickSight for visualization.


---

# AWS Cost Explorer

### Function
Interface that lets you visualize, understand, and manage your AWS costs and usage over time.

### Use Case
- Identifying cost trends and spikes over the last 12 months.
- Forecasting future spend.
- Getting rightsizing recommendations for EC2 instances.

### Tips
- Free to use (API calls cost $).
- Visual reports and filtering.
- Provides Savings Plans recommendations.


---

# AWS Data Exchange

### Function
Service that makes it easy to find, subscribe to, and use third-party data in the AWS Cloud.

### Use Case
- Financial market data subscriptions.
- Acquiring weather data for demand forecasting.
- Health research data acquisition.

### Tips
- Specifically for third-party data.
- Integrates with S3 for data delivery.
- Different from AWS Marketplace (general software).


---

# AWS Data Pipeline

### Function
Web service that helps you reliably process and move data between different AWS compute and storage services, as well as on-premises data sources.

### Use Case
- Moving data from S3 to DynamoDB at regular intervals.
- Orchestrating ETL workflows across different instances.

### Tips
- Managed workflow service.
- Use for scheduling data moves.
- Modern alternatives include AWS Step Functions or AWS Glue.


---

# AWS Database Migration Service (AWS DMS)

### Function
Service that helps you migrate databases to AWS quickly and securely.

### Use Case
- Migrating on-premises databases to RDS/Aurora.
- Replicating data between different database engines (with SCT).

### Tips
- Supports homogeneous and heterogeneous migrations.
- Schema Conversion Tool (SCT) used for engine changes.
- Can perform continuous data replication.


---

# AWS DataSync

### Function
Online data transfer service that simplifies, automates, and accelerates moving data between on-premises storage systems and AWS storage services, as well as between AWS storage services.

### Use Case
- Moving large amounts of file data from on-prem NAS to S3/EFS/FSx.
- Periodic sync of datasets to the cloud.

### Tips
- Accelerated transfer via custom protocol.
- Can copy between AWS services (S3-to-S3, etc.).


---

# AWS Device Farm

### Function
App testing service that lets you test and interact with your Android, iOS, and web apps on real, physical phones and tablets that are hosted by AWS.

### Use Case
- Testing mobile apps on specific hardware generations/OS versions.
- Automated testing of web apps on real browsers.

### Tips
- Uses REAL devices, not simulators.
- Test report includes screenshots and logs.


---

# AWS Direct Connect

### Function
Cloud service solution that makes it easy to establish a dedicated network connection from your premises to AWS.

### Use Case
- Workloads requiring consistent network performance (bypassing the public internet).
- High-bandwidth data transfer to/from on-premises.

### Tips
- Physical cross-connect.
- Dedicated (1/10/100 Gbps) or Hosted (up to 10 Gbps) connections.
- Public/Private/Transit Virtual Interfaces (VIFs).


---

# AWS Directory Service

### Function
Managed service that provides several ways to use Microsoft Active Directory (AD) with other AWS services.

### Use Case
- Using existing corporate AD credentials for AWS services.
- Creating a standalone managed AD in the cloud.

### Tips
- Managed Microsoft AD, AD Connector (Proxy), Simple AD.


---

# AWS Elastic Beanstalk

### Function
Easy-to-use service for deploying and scaling web applications and services developed with Java, .NET, PHP, Node.js, Python, Ruby, Go, and Docker on familiar servers such as Apache, Nginx, Passenger, and IIS.

### Use Case
- Rapidly deploying a web app without managing individual resources like ELB, ASG, or EC2.
- Handling infrastructure management while maintaining control.

### Tips
- PaaS (Platform as a Service).
- Managed deployment strategies (All-at-once, Rolling, Immutable).
- Worker tier for SQS-based background processing.


---

# AWS Fargate

### Function
Serverless compute engine for containers that works with both Amazon Elastic Container Service (ECS) and Amazon Elastic Kubernetes Service (EKS).

### Use Case
- Running containers without managing the underlying EC2 instances.

### Tips
- Eliminates the need to manage scaling and patching of nodes.
- Pay only for resources used by the container.


---

# AWS Firewall Manager

### Function
Security management service which allows you to centrally configure and manage firewall rules across your accounts and applications in AWS Organizations.

### Use Case
- Centrally managing WAF rules across an whole organization.

### Tips
- Automates application of security policies across accounts.


---

# AWS Global Accelerator

### Function
Service that improves the availability and performance of your applications with local or global users.

### Use Case
- Routing traffic to the nearest regional endpoint using the AWS global network.
- Fast failover between AWS regions.

### Tips
- Provides Static Anycast IP addresses.
- Uses the AWS Global Private Network.
- Improves performance by up to 60% by avoiding internet jitters.


---

# AWS Glue

### Function
Serverless data integration service that makes it easy to discover, prepare, and combine data for analytics, machine learning, and application development.

### Use Case
- ETL (Extract, Transform, Load) for data lakes.
- Cataloging data in S3 for querying by Athena or Redshift.
- Preparing data for Machine Learning.

### Tips
- Glue Crawlers automatically infer schema.
- Glue Data Catalog is central metadata repository.
- Glue Job Bookmarks handle incremental data processing.


---

# AWS Health Dashboard

### Function
Single place to learn about the availability and operations of AWS services and your AWS resources specifically.

### Use Case
- Checking if a regional AWS outage is affecting your services.

### Tips
- Service Health (general) and Resource Health (personal).
- Provides notifications for scheduled maintenance.


---

# AWS IAM Identity Center (AWS Single Sign-On)

### Function
Service that helps you centrally manage SSO access to all your AWS accounts and cloud applications.

### Use Case
- Centralized portal for logging into multiple AWS accounts.

### Tips
- Preferred over standard IAM users for multi-account environments.
- Integrates with external identity providers (Okta, Azure AD).


---

# AWS Identity and Access Management (IAM)

### Function
Service that helps you securely control access to AWS resources.

### Use Case
- Managing users, groups, and roles for AWS service access.
- Defining granular permissions using JSON policies.

### Tips
- Users, Groups, Roles (Temporary credentials).
- Policies (Inline vs Managed).
- Principle of Least Privilege.


---

# AWS Key Management Service (AWS KMS)

### Function
Managed service that makes it easy for you to create and control the cryptographic keys used to encrypt your data.

### Use Case
- Managing encryption keys for S3, EBS, RDS, etc.
- Defining key usage policies.

### Tips
- Multi-tenant but extremely secure (FIPS 140-2 Level 2).
- Integrates with almost all AWS services.
- Customer Managed Keys (CMK) vs. AWS Managed Keys.


---

# AWS Lake Formation

### Function
Service that makes it easy to set up a secure data lake in days.

### Use Case
- Setting up a centralized data lake on S3.
- Implementing fine-grained (row/column level) access control for data in S3.
- Simplifying data ingestion and cataloging from multiple sources.

### Tips
- Built on top of Glue and S3.
- Provides a centralized dashboard for permissions.
- Use when you need complex security on data lakes.


---

# AWS Lambda

### Function
Serverless compute service that lets you run code without provisioning or managing servers. You pay only for the compute time you consume.

### Use Case
- Reacting to S3 file uploads for image processing.
- Backend API logic triggered by API Gateway.
- Automating maintenance tasks.

### Tips
- Event-driven.
- Max runtime 15 mins.
- Stateless by nature.
- Concurrency limits and cold starts.


---

# AWS License Manager

### Function
Service that makes it easier to manage licenses from software vendors such as Microsoft, SAP, Oracle, and IBM across AWS and on-premises environments.

### Use Case
- Enforcing software license limits to stay compliant.
- Tracking license usage (e.g., number of vCPUs).

### Tips
- Centralized license management.
- Integrates with EC2 (Dedicated Hosts and standard instances).


---

# AWS Management Console

### Function
Web-based user interface for managing AWS resources.

### Use Case
- Manual configuration of AWS resources.
- Visualizing resource status and settings.

### Tips
- Easier for beginners; use CLI/Terraform for automation.


---

# AWS Migration Hub

### Function
Single location to track the progress of application migrations across multiple AWS and partner solutions.

### Use Case
- Centralized tracking of all migration activities.

### Tips
- Dashboard for migration status.
- Integration with Discovery Service and MGN.


---

# AWS Network Firewall

### Function
Managed service that makes it easy to deploy essential network protections for all of your Virtual Private Clouds (VPCs).

### Use Case
- Granular traffic filtering (L3-L7) for VPC egress/ingress.

### Tips
- Network-level protection (as opposed to WAF which is application-level).


---

# AWS Organizations

### Function
Account management service that enables you to consolidate multiple AWS accounts into an organization that you create and centrally manage.

### Use Case
- Centralized billing (Consolidated Billing).
- Applying Service Control Policies (SCPs) to restrict actions at account/OU level.
- Automated account creation.

### Tips
- SCPs do not grant permissions; they filter them.
- SCPs do not apply to the Management account.
- Used for multi-account strategy.


---

# AWS Outposts

### Function
Fully managed service that extends AWS infrastructure, AWS services, APIs, and tools to virtually any data center, co-location space, or on-premises facility for a truly consistent hybrid experience.

### Use Case
- Workloads requiring low latency to on-premises systems.
- Local data processing for regulatory compliance.
- Running AWS services in a private data center.

### Tips
- AWS on-premises.
- AWS managed and supported.
- Consistent with AWS Region APIs.


---

# AWS PrivateLink

### Function
Technology that provides high-availability connectivity between VPCs, AWS services, and on-premises networks, without exposing your traffic to the public internet.

### Use Case
- Securely consuming services from service providers while keeping traffic inside the AWS network.
- Creating interface VPC endpoints.

### Tips
- Uses Interface Endpoints.
- Keeps traffic off the public internet.
- Commonly used for security-sensitive SaaS integrations.


---

# AWS Proton

### Function
Fully managed delivery service for container and serverless applications. Platform engineering teams can use AWS Proton to connect and coordinate all the different tools needed for infrastructure provisioning, code deployments, monitoring, and updates.

### Use Case
- Standardizing infrastructure and CI/CD pipelines for microservices developers.

### Tips
- Platform engineering tool.
- Managed infrastructure templates.


---

# AWS Resource Access Manager (AWS RAM)

### Function
Service that helps you securely share your AWS resources across AWS accounts, within your organization or organizational units (OUs), and with IAM roles and IAM users for supported resource types.

### Use Case
- Sharing a Transit Gateway or Subnet across multiple accounts in an organization.

### Tips
- Optimizes resource usage in multi-account strategies.


---

# AWS Secrets Manager

### Function
Service that helps you protect secrets needed to access your applications, services, and IT resources.

### Use Case
- Storing database credentials and rotating them automatically.
- Retrieving secrets programmatically in application code.

### Tips
- Supports automatic rotation (especially for RDS).
- Pay-per-secret pricing.


---

# AWS Security Hub

### Function
AWS service that provides a comprehensive view of your security state in AWS and helps you check your environment against security industry standards and best practices.

### Use Case
- Centralized dashboard for security findings from GuardDuty, Inspector, Macie, IAM Access Analyzer, and AWS Systems Manager Patch Manager.

### Tips
- Security 'single pane of glass'.


---

# AWS Serverless Application Repository

### Function
Managed repository for serverless applications. It enables teams, organizations, and individual developers to store and share reusable applications, and easily assemble and deploy serverless architectures in powerful new ways.

### Use Case
- Quickly deploying pre-built serverless applications (e.g., log processors).
- Sharing serverless components within a large organization.

### Tips
- Search and deploy common serverless patterns.
- Supports nested applications.


---

# AWS Service Catalog

### Function
Service that allows organizations to create and manage catalogs of IT services that are approved for use on AWS.

### Use Case
- Enabling self-service for users to deploy approved, compliant infrastructure.
- Standardizing CloudFormation templates for general organization use.

### Tips
- Governance-focused.
- Users only see and deploy what is in the catalog.


---

# AWS Shield

### Function
Managed Distributed Denial of Service (DDoS) protection service that safeguards applications running on AWS.

### Use Case
- Protecting ELB, CloudFront, and Route 53 from DDoS attacks.

### Tips
- Shield Standard (free, basic proteção).
- Shield Advanced (paid, specialized protection, cost protection against spikes).


---

# AWS Site-to-Site VPN

### Function
Service that creates a secure connection between your data center or branch office and your AWS resources.

### Use Case
- Connecting an on-premises data center to a VPC over the public internet with IPsec encryption.

### Tips
- Uses Virtual Private Gateway (VGW) or Transit Gateway (TGW).
- Uses Customer Gateway (CGW) on-premises.
- Fast setup compared to Direct Connect.


---

# AWS Snow Family

### Function
Collection of physical devices and capacity-points that help move petabytes of data into and out of AWS and provide edge computing capabilities.

### Use Case
- Offline transfer of petabytes of data to AWS (Snowball/Snowmobile).
- Edge computing in disconnected environments (Snowcone/Snowball Edge).

### Tips
- Snowcone (8TB), Snowball Edge (80TB), Snowmobile (100PB).
- Physical shipping required.


---

# AWS Step Functions

### Function
Serverless function orchestrator that makes it easy to sequence AWS Lambda functions and multiple AWS services into business-critical applications.

### Use Case
- Orchestrating a multi-step ETL process involving Lambda, Glue, and Redshift.
- Implementing long-running workflows with manual approval steps.
- Managing retry logic and error handling in microservices.

### Tips
- Visual workflows (state machines).
- Handles retries, timeouts, and error catching automatically.
- Standard workflows (long-running) and Express workflows (high-volume, short-running).


---

# AWS Storage Gateway

### Function
Hybrid cloud storage service that gives you on-premises access to virtually unlimited cloud storage.

### Use Case
- NFS/SMB access to S3 (S3 File Gateway).
- Replacing physical tape libraries with cloud storage (Tape Gateway).
- Cached access to cloud-stored volumes (Volume Gateway).

### Tips
- Connects on-premises to AWS storage.
- Cached vs Stored modes for Volume Gateway.


---

# AWS Systems Manager

### Function
AWS service that you can use to view and control your infrastructure on AWS and on-premises.

### Use Case
- Patch management for EC2 fleets (Patch Manager).
- Storing configuration parameters and secrets (Parameter Store).
- Remote shell access without SSH (Session Manager).

### Tips
- Formerly called SSM.
- Requires SSM Agent on managed instances.
- Huge toolset: Run Command, State Manager, Automation, AppConfig, etc.


---

# AWS Transfer Family

### Function
Fully managed support for file transfers directly into and out of Amazon S3 or Amazon EFS over the SFTP, AS2, FTPS, and FTP protocols.

### Use Case
- Allowing partners to upload files to S3 via SFTP.
- Migrating FTP/SFTP workloads into AWS.

### Tips
- Fully managed SFTP/FTP/FTPS/AS2.
- Directly uses S3 or EFS as the backend.


---

# AWS Transit Gateway

### Function
Service that connects VPCs and on-premises networks through a central hub.

### Use Case
- Cleaning up complex VPC peering meshes (Hub-and-Spoke).
- Centralizing connectivity for thousands of VPCs and on-premises networks.

### Tips
- Simplifies network management.
- Supports Inter-Region Peering.
- Central gateway for VPN and DX.


---

# AWS Trusted Advisor

### Function
Online tool that provides you real-time guidance to help you provision your resources following AWS best practices.

### Use Case
- Identifying S3 buckets with public access.
- Finding underutilized resources to save money.
- Checking for service limit increases.

### Tips
- Categories: Cost Optimization, Performance, Security, Fault Tolerance, Service Limits.
- Core checks free; full checks with Business/Enterprise support.


---

# AWS WAF

### Function
Web application firewall that helps protect your web applications or APIs against common web exploits and bots that may affect availability, compromise security, or consume excessive resources.

### Use Case
- Blocking SQL injection and Cross-Site Scripting (XSS).
- Throttling requests from specific IP ranges (IP Reputation).

### Tips
- L7 firewall.
- Deployed on ALB, API Gateway, CloudFront, AppSync.


---

# AWS Wavelength

### Function
AWS infrastructure offering optimized for mobile edge computing applications. Wavelength Zones are AWS infrastructure deployments that embed AWS compute and storage services within 5G networks, providing seamless access to AWS services from 5G devices worldwide.

### Use Case
- Ultra-low latency mobile applications (5G).
- Real-time gaming, augmented reality (AR), and smart factories.
- Connected vehicles.

### Tips
- Keywords: 5G, mobile edge, ultra-low latency.
- Part of Wavelength Zones.


---

# AWS Well-Architected Tool

### Function
Service that helps you review the state of your workloads and compares them to the latest AWS architectural best practices.

### Use Case
- Performing self-service architectural reviews.
- Measuring and improving the health of your workloads.

### Tips
- 6 Pillars: Operational Excellence, Security, Reliability, Performance Efficiency, Cost Optimization, Sustainability.


---

# AWS X-Ray

### Function
Service that helps developers analyze and debug distributed applications, such as those built using a microservices architecture.

### Use Case
- Tracing requests through multiple AWS services (API Gateway -> Lambda -> DynamoDB).
- Identifying performance bottlenecks and latency issues.
- Visualizing service dependencies via Service Maps.

### Tips
- Integrated with Lambda, API Gateway, ECS, ELB.
- Provides end-to-end tracing.
- Essential for microservices debugging.


---

# Elastic Load Balancing (ELB)

### Function
Service that automatically distributes incoming application traffic across multiple targets, such as Amazon EC2 instances, containers, IP addresses, Lambda functions, and virtual appliances.

### Use Case
- Distributing HTTP/HTTPS traffic (ALB).
- Decoupling clients from servers for high availability.

### Tips
- ALB (Layer 7 - URL/Path/Host based).
- NLB (Layer 4 - TCP/UDP, ultra-high performance, static IP).
- GWLB (Layer 3 - Third-party appliances).
- CLB (Legacy).
- Health Checks.


---

# Savings Plans

### Function
Flexible pricing model that offers low prices on AWS usage, in exchange for a commitment to a consistent amount of usage (measured in $/hour) for a 1 or 3 year term.

### Use Case
- Reducing costs for a mix of EC2, Fargate, and Lambda usage.
- Committing to steady-state usage to save up to 72%.

### Tips
- Compute Savings Plans provide max flexibility (across Regions, families, and services).
- EC2 Instance Savings Plans provide max savings for specific family/Region.
- Commitment-based savings.


---

# VMware Cloud on AWS

### Function
Integrated cloud service that delivers a highly scalable, secure and innovative service that allows organizations to seamlessly migrate and extend their on-premises VMware vSphere-based environments to the AWS Cloud running on next-generation Amazon Elastic Compute Cloud (Amazon EC2) bare metal infrastructure.

### Use Case
- Migrating VMware workloads to AWS without refactoring.
- Hybrid cloud extension of on-premises VMware vSphere environments.

### Tips
- Native VMware stack on AWS infrastructure.
- Uses Bare Metal EC2 instances.


---

