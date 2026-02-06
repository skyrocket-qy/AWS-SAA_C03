# Comparison: Amazon API Gateway vs. AWS AppSync

### Overview
| Feature | **Amazon API Gateway** | **AWS AppSync** |
| :--- | :--- | :--- |
| **API Type** | REST, HTTP, WebSocket | GraphQL, Pub/Sub |
| **Data Fetching** | Client makes multiple calls to different endpoints | Client makes a single call with a specific schema |
| **Real-time** | WebSocket APIs | GraphQL Subscriptions (WebSockets) |
| **Security** | IAM, Cognito, Lambda Authorizers, API Keys | IAM, Cognito, OIDC, API Keys |
| **Offline Support** | No native support | Native support via AWS Amplify |
| **Complexity** | Simple for standard REST endpoints | Advanced; requires learning GraphQL schema |

### Why use AppSync Pipeline Resolvers?
In API Gateway, complex logic often requires a Lambda function to orchestrate multiple backend calls. In **AppSync**, **Pipeline Resolvers** can handle this orchestration natively by sequencing multiple "Functions" (data source operations) without needing to write a monolithic "orchestrator" Lambda.
# Amazon AppFlow

A managed integration service for secure data transfer between SaaS (Salesforce, Zendesk, Slack) and AWS (S3, Redshift).

### Key Exam Points
- **Security**: Supports **AWS PrivateLink** (PrivateFlow) to keep traffic off the public internet.
- **No-Code**: Transform, filter, and map data without writing code.
- **Integration**: Ideal for SaaS-to-AWS or SaaS-to-SaaS data synchronization.
- **Automation**: Can be triggered on-demand, on a schedule, or by events.
# AWS Application Discovery Service

Helps plan migration by gathering inventory and behavior data from on-premises data centers.

### Key Exam Points
- **Planning Phase**: Used *before* migration to discover local infrastructure.
- **Agentless Discovery**: VM-level info (CPU/RAM/Disk) via VMware vCenter; no OS-level view.
- **Agent-based Discovery**: Detailed info (processes, network dependencies) via installed agents; required for **dependency mapping**.
- **Integration**: Syncs data with **AWS Migration Hub**.
- **Lifecycle**: Used for planning; actual migration is then performed by **[AWS Application Migration Service (MGN)](aws_mgn.md)**.

# AWS AppSync

A fully managed service that makes it easy to develop GraphQL APIs by handling the heavy lifting of securely connecting to data sources like DynamoDB, Lambda, and more.

### Key Exam Points
- **GraphQL**: Uses GraphQL to enable applications to fetch exactly the data they need.
- **Data Sources**: Supports DynamoDB, Amazon Aurora (Serverless), AWS Lambda, Amazon OpenSearch Service, and HTTP endpoints.
- **Real-time**: Provides real-time data updates using **WebSockets** (Subscriptions).
- **Offline Access**: Supports offline data synchronization with AWS Amplify.
- **Security**: Integrates with IAM, Amazon Cognito User Pools, API Keys, and OpenID Connect for authorization.

### Pipeline Resolvers
- **Definition**: Allows executing multiple operations (called **Functions**) in a sequential order for a single GraphQL field.
- **Structure**:
    - **Before mapping template**: Prepares the data before calling the first function.
    - **Functions**: One or more execution steps (e.g., check authorization in Lambda, then fetch data from DynamoDB).
    - **After mapping template**: Finalizes the response sent back to the client.
- **Use Case**: Ideal for complex business logic, such as data validation, authorization checks across multiple tables, or fetching data from multiple sources in a specific order.
- **Communication**: Functions share a `ctx.stash` object to pass data between them.
# Amazon Aurora

**Amazon Aurora** is a MySQL and PostgreSQL-compatible relational database built for the cloud with high performance and availability.

### Key Exam Points
- **Aurora Global Database**: Cross-region disaster recovery; < 1 second replication lag; < 1 minute RTO.
- **Aurora Serverless v2**: Near-instant scaling for unpredictable workloads; supports Global Database.
- **High Availability**: 6 copies of data across 3 AZs; up to 15 read replicas.
- **Features**: 
    - **Backtrack**: Quickly "rewind" to a point in time without restoring from backup.
    - **Cloning**: Fast, cost-effective data copies (copy-on-write).
- **Auto-Scaling**: Storage automatically scales up to 128 TB.
# Amazon EC2 Auto Scaling

**Amazon EC2 Auto Scaling** maintains application availability by automatically adding or removing EC2 instances based on demand.

### Key Exam Points
- **Capacity Settings**:
    - **Minimum Size**: Lower limit of instances.
    - **Maximum Size**: Upper limit of instances.
    - **Desired Capacity**: Target number of instances running now (ASG maintains this).
- **Health Checks**: Use **ELB Health Checks** (not just EC2) to replace instances if the application itself fails.
- **Launch Template**: Modern method (recommended); supports versioning and Spot offset.
- **Termination Policy**: Default strategy prioritizes balancing across AZs, then oldest launch template/configuration.
- **Scaling Policies**: (Target Tracking, Step Scaling, Simple Scaling, Predictive).
# AWS Batch

**AWS Batch** runs containerized batch computing jobs across AWS Fargate, EC2, and Spot Instances.

### Key Exam Points
- **Use Case**: Long-running, compute-intensive jobs (financial analysis, genomics, rendering).
- **Core Components**: Jobs (unit of work), Job Definitions (blueprint), Job Queues (priority), Compute Environments (resources).
- **Cost Savings**: Native support for **Spot Instances**.
- **Batch vs. Lambda**: Use Batch for jobs > 15 minutes or tasks requiring specific Docker environments/heavy resources.
# AWS Budgets

**AWS Budgets** allows you to set custom budgets to track cost and usage, providing alerts when thresholds are exceeded.

### Key Exam Points
- **Alerting**: Primary tool for set alerts on **actual** or **forecasted** costs/usage.
- **Actions**: Can trigger automated responses like stopping EC2 instances or applying IAM policies (via SNS/Systems Manager).
- **Types**: Cost, Usage, RI Utilization/Coverage, and Savings Plans Utilization/Coverage.
- **Budgets vs. Cost Explorer**: Budgets is for **planning/alerting**; Cost Explorer is for **analysis/history**.
# AWS CloudFormation

**AWS CloudFormation** is an Infrastructure as Code (IaC) service that models and provisions AWS resources using templates (JSON/YAML).

### Key Exam Points
- **Stack**: A collection of resources managed as one unit.
- **ChangeSet**: A preview of proposed changes before execution (dry run).
- **Drift Detection**: Identifies if resources have changed outside of CloudFormation.
- **StackSets**: Deploy stacks across **multiple accounts and regions** simultaneously.
- **Nested Stacks**: Reusable templates referenced within other templates for modularity.
- **Cross-Stack Reference**: Use `Export` and `ImportValue` to share outputs between stacks.
# Amazon CloudFront

**Amazon CloudFront** is a Content Delivery Network (CDN) that caches content at global **Edge Locations** to reduce latency.

### Key Exam Points
- **Origins**: S3 buckets, ALB, EC2, or custom HTTP servers.
- **S3 Security**: Use **Origin Access Control (OAC)** to restrict S3 access so users must go through CloudFront.
- **Security**: Integrates with **AWS WAF** (firewall) and **AWS Shield** (DDoS).
- **Edge Computing**:
    - **CloudFront Functions**: Lightweight JS for high-scale header/URL manipulation at Edge Locations (< 1ms).
    - **Lambda@Edge**: Full Node.js/Python functions at Regional Edge Caches for complex logic (network calls, body access).
- **Key Use Case**: Set `User-Agent` headers or perform A/B testing at the edge.
# AWS CloudHSM

**AWS CloudHSM** provides dedicated, single-tenant Hardware Security Modules for cryptographic key management.

### Key Exam Points
- **Compliance**: Meets **FIPS 140-2 Level 3** (KMS is generally Level 2).
- **Single-Tenancy**: Dedicated hardware; no sharing with other customers.
- **Control**: User has **exclusive** control of keys; AWS admins cannot access them.
- **Integration**: Runs inside your **VPC**; requires manual management of redundancy and backups.
- **When to choose**: Strict regulatory requirements (Level 3) or need for dedicated hardware.
# Amazon CloudWatch

**Amazon CloudWatch** provides monitoring and observability for AWS resources and applications.

### Key Exam Points
- **Default Metrics**: Hypervisor-level data (CPU, Network, Disk I/O).
- **CloudWatch Agent**: Required for **internal OS metrics** (Memory/RAM, Disk Space Usage, Swap) and pushing logs from EC2/on-premises.
- **Detailed Monitoring**: Increases EC2 metric frequency to **1 minute** (Standard is 5 mins). Does NOT include RAM.
- **Alarms**: Triggers actions (Auto Scaling, SNS, EC2 Reboot) when thresholds are crossed.
- **Logs**: Can be exported to **S3** (storage) or streamed to **Kinesis/OpenSearch** (analysis).
# AWS Control Tower

**AWS Control Tower** simplifies the setup and governance of a secure, multi-account AWS environment (Landing Zone).

### Key Exam Points
- **Landing Zone**: A pre-configured, multi-account environment based on best practices.
- **Guardrails**: High-level rules for governance.
    - **Preventive**: Uses **Service Control Policies (SCPs)** to prevent actions.
    - **Detective**: Uses **AWS Config** to detect non-compliance.
- **Account Factory**: Automates new account provisioning via AWS Service Catalog.
- **Dashboard**: Provides central visibility of compliance across all accounts.
- **Under the Hood**: Uses AWS Organizations, IAM Identity Center (SSO), and AWS Config.
# AWS Cost and Usage Report (CUR)

The **AWS Cost and Usage Report (CUR)** is the most detailed and granular cost/usage data available.

### Key Exam Points
- **Granularity**: Most comprehensive data (hourly/daily, resource IDs, tags).
- **Delivery**: Reports are delivered to an **Amazon S3** bucket.
- **Analysis**: Use **Amazon Athena** (SQL), **Redshift**, or **QuickSight** (visuals) to analyze the raw data in S3.
- **Use Case**: Deep-dive cost analysis or integration with external BI tools.
# AWS Cost Explorer

**AWS Cost Explorer** lets you visualize, understand, and manage your AWS costs and usage trends over time.

### Key Exam Points
- **Visualization**: View up to 12 months of history and 12 months of **forecasting**.
- **Rightsizing**: Provides recommendations to reduce costs by identifying underutilized EC2 instances.
- **RI/Savings Plans**: Track utilization and coverage; get purchase recommendations.
- **Cost Explorer vs. Budgets**: Explorer is for **analysis/forecasting**; Budgets is for **alerting** based on limits.
- **Granularity**: Available at monthly, daily, and hourly levels.
# AWS Data Exchange

**AWS Data Exchange** is a service for finding, subscribing to, and using third-party data in the cloud.

### Key Exam Points
- **Use Case**: Acquiring **external/third-party** datasets (financial, medical, etc.).
- **Delivery**: Subscribed data is delivered directly to your **Amazon S3** bucket.
- **Automation**: Automatically receives new revisions/updates from providers.
- **Marketplace**: Differentiated from general AWS Marketplace by focusing specifically on data products.
# AWS Data Exchange vs. AWS Data Pipeline

### Comparison Overview
- **Data Exchange**: Used to acquire **third-party (external)** data from providers. Data is delivered to S3.
- **Data Pipeline**: Used to orchestrate and automate the movement/transformation of **internal** data (e.g., RDS to Redshift).

### Key Exam Points
- **Source**: Exchange = External vendors; Pipeline = Your own AWS infrastructure.
- **Modern Alternatives for Pipeline**: **AWS Glue** (ETL), **Step Functions** (Orchestration), or **Amazon MWAA** (Airflow).
- **Scenario**: Choose **Data Exchange** for buying data; choose **Data Pipeline/Glue** for moving your own data.
# AWS Data Pipeline

**AWS Data Pipeline** orchestrates and automates data movement and transformation between AWS services and on-premises sources.

### Key Exam Points
- **Use Case**: Scheduled ETL jobs (e.g., RDS to Redshift, DynamoDB to S3).
- **On-Premises**: Supports on-premises sources via **Task Runner**.
- **Execution**: Uses EC2 or EMR for data processing tasks.
- **Legacy**: For new workloads, consider **AWS Glue** (serverless ETL) or **Step Functions** (general orchestration).
- **Automation**: Handles retries and sends failure notifications via SNS.
# AWS Device Farm

**AWS Device Farm** provides real mobile devices and desktop browsers for application testing.

### Key Exam Points
- **Use Case**: Testing mobile/web apps on **real physical hardware** (iOS, Android) and browsers (Chrome, Firefox).
- **Automated Testing**: Supports frameworks like Appium, Selenium, and XCTest.
- **Remote Access**: Allows manual interaction with devices via a web browser.
- **Integration**: Plugs into CI/CD pipelines (Jenkins, CodePipeline) for regression testing.
# AWS Directory Service

**AWS Directory Service** provides options for using Microsoft Active Directory (AD) or LDAP in AWS.

### Key Exam Points
- **Managed Microsoft AD**: Full AD on Windows; supports **Trust Relationships** (two-way trust with on-premises AD).
- **AD Connector**: A **proxy** to on-premises AD; no data cached in AWS; no trust relationship needed.
- **Simple AD**: Low-cost **Linux-based** AD; basic features only; no trust support.
- **Scenarios**:
    - Full AD & Trusts -> **Managed Microsoft AD**.
    - Link to on-premises AD (no sync) -> **AD Connector**.
    - Small, simple environment -> **Simple AD**.
# Amazon DynamoDB

**Amazon DynamoDB** is a fully managed, serverless, NoSQL database for fast and predictable performance.

### Key Exam Points
- **Scaling**: **Provisioned** (RCUs/WCUs) or **On-Demand** (pay-per-request).
- **Persistence/Backup**:
    - **PITR**: Continuous backups for the last **35 days** (restores to a new table).
    - **On-Demand Backup**: Manual backups for long-term archival.
- **Global Tables**: Multi-region, multi-active replication (requires DynamoDB Streams).
- **Performance**: 
    - **DAX**: In-memory cache for microsecond read latency.
    - **DynamoDB Streams**: Capture real-time changes to trigger Lambda or Kinesis.
- **Consistency**: **Eventually Consistent** (default) vs. **Strongly Consistent** (requires more RCUs).
# Amazon Elastic Block Store (EBS)

**Amazon EBS** provides block-level storage volumes for EC2 instances.

### Key Exam Points
- **Scoping**: Volumes are **locked to a specific Availability Zone (AZ)**. To move data, use Snapshots.
- **Snapshots**: Point-in-time, incremental backups stored in S3 (Regional).
- **Volume Types**:
    - **gp3**: Recommended general purpose (independent IOPS/Throughput).
    - **io2 Block Express**: Extreme performance, supports **Multi-Attach**.
    - **st1**: Throughput-optimized HDD (Big Data, Log processing).
    - **sc1**: Cold HDD (infrequently accessed, lowest cost).
- **Multi-Attach**: Allows an **io1/io2** volume to be attached to multiple Nitro-based instances in the *same* AZ.
- **Fast Snapshot Restore (FSR)**: Eliminates latency of first-time block access from snapshots.
# Amazon EC2

**Amazon EC2** provides resizable compute capacity via virtual servers (instances).

### Key Exam Points
- **Purchasing Options**:
    - **On-Demand**: Pay-as-you-go; highest cost; no commitment.
    - **Spot**: Up to 90% discount; 2-minute interruption warning; use for fault-tolerant/batch workloads.
    - **Reserved (RI)**: 1 or 3-year commitment (Standard vs. Convertible); up to 72% discount.
    - **Savings Plans**: Commitment to $/hour spend; most flexible (applies to EC2, Fargate, Lambda).
    - **Dedicated Hosts**: Physical servers for licensing (BYOL) or strict compliance.
- **Spot Fleet**: Automates launching a mix of Spot and On-Demand instances to meet target capacity.
- **Placement Groups**: (Cluster, Spread, Partition) to optimize performance or availability.
- **Instance Store**: Ephemeral (lost if stopped/failed); highest I/O performance.
# Amazon EC2 Placement Groups

**Placement Groups** influence where EC2 instances are placed on physical hardware.

### Key Exam Points
- **Cluster**: Packs instances close together in a **single AZ**. Used for high throughput/low latency (HPC, ML).
- **Spread**: Places each instance on its own distinct rack. Max **7 instances per AZ**. Used for high-availability critical nodes.
- **Partition**: Spreads instances across logical partitions (racks). Used for large distributed workloads (Hadoop, Kafka, Cassandra).
- **Scoping**: Spread and Partition can span multiple AZs; Cluster is limited to a single AZ.
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
# Elastic Load Balancing (ELB)

**ELB** automatically distributes incoming traffic across multiple targets like EC2, containers, and IP addresses.

### Key Exam Points
- **Application Load Balancer (ALB)**: Layer 7 (HTTP/HTTPS); content-based routing (path, host, header); supports WAF and Lambda.
- **Network Load Balancer (NLB)**: Layer 4 (TCP/UDP); ultra-high performance/low latency; provides **Static/Elastic IPs**.
- **Gateway Load Balancer (GWLB)**: Layer 3; used for virtual appliances (firewalls, IDS/IPS); communicates via **GENEVE** protocol.
- **Features**:
    - **Cross-Zone Load Balancing**: Even traffic distribution across AZs.
    - **Sticky Sessions**: Binds a user To a specific target (supported by ALB/CLB).
    - **Health Checks**: Periodically monitors target health.
# Elastic Network Interface (ENI)

An **ENI** is a logical networking component in a VPC representing a virtual network card.

### Key Exam Points
- **Attributes**: Includes a primary private IPv4, secondary IPs, Elastic IPs, a public IP, and security groups.
- **Primary ENI (eth0)**: Created with the instance; **cannot** be detached.
- **Secondary ENI**: Can be hot-swapped between instances for failover or management networks.
- **Security**: Security groups are attached to the ENI, not the instance.
# Amazon FSx

**Amazon FSx** provides managed third-party file systems for specific workloads.

### Key Exam Points
- **FSx for Lustre**: High-performance (HPC, ML, video processing); **Linux only**; integrates with **S3**.
    - **Scratch**: Temporary, no replication.
    - **Persistent**: Long-term, replicated.
- **FSx for Windows**: Native Windows file system (**SMB**, NTFS, Active Directory integration).
- **FSx for NetApp ONTAP**: Multi-protocol (NFS, SMB, iSCSI); best for migrating on-premises NetApp.
- **FSx for OpenZFS**: Managed ZFS (snapshots, compression).
# AWS Global Accelerator

**AWS Global Accelerator** improves application availability and performance for global users using the AWS internal network.

### Key Exam Points
- **Static IPs**: Provides **two static Anycast IP addresses** as a fixed entry point.
- **Mechanism**: Traffic enters the AWS network at the Edge Location closest to the user, bypassing the public internet to reach application endpoints (ALB, NLB, EC2).
- **Failover**: Instant failover to healthy endpoints without DNS caching issues.
- **vs. CloudFront**: 
    - **CloudFront**: Focuses on **caching** (HTTP/HTTPS) at the edge.
    - **Global Accelerator**: Focuses on **network path optimization** (TCP/UDP) over the global network. No caching.
- **Use Case**: Gaming (UDP), VoIP, or apps requiring fixed IP addresses.
# AWS Glue

**AWS Glue** is a serverless data integration service (ETL) used to discover and prepare data for analytics.

### Key Exam Points
- **Data Catalog**: Central **metadata** repository (Hive-compatible metastore) for Athena, EMR, and Redshift.
- **Crawlers**: Automatically scan data stores (S3, JDBC) to infer schema and populate the Data Catalog.
- **ETL Jobs**: Automatically generates Python/Scala code to transform data; charges only for resources used.
- **Job Bookmarks**: Tracks state to process only **new data** (incremental ETL), avoiding reprocessing.
- **Glue DataBrew**: Visual tool for cleaning/normalizing data without writing code.
# AWS IAM Identity Center (Single Sign-On)

**IAM Identity Center** is the recommended service for managing centralized SSO access to AWS accounts and SaaS apps.

### Key Exam Points
- **Multi-Account Access**: Users log into a single portal to access all authorized accounts/roles in an **AWS Organization**.
- **Permission Sets**: Templates for IAM roles that apply across managed accounts.
- **Identity Sources**: Supports internal directory, **Active Directory** (via AD Connector or Managed AD), or external SAML IdPs (Okta, Azure AD).
- **Use Case**: Centralized governance for dozens/hundreds of accounts; simpler than managing individual SAML federations.
- **ABAC**: Supports Attribute-Based Access Control using user attributes.
# Internet Gateway (IGW)

An **Internet Gateway** provides a target in your VPC route tables for internet-bound traffic and performs NAT for instances with public IPv4 addresses.

### Key Exam Points
- **Scope**: Horizontally scaled, redundant, and highly available (managed by AWS). No bandwidth constraints.
- **Constraints**: You can attach only **one** IGW to a VPC at a time.
- **Use Case**: Allows resources in **public subnets** (with public IPs) to connect to the internet and vice versa.
- **Setup**: Create, attach to VPC, and add a route (`0.0.0.0/0`) in the subnet's route table pointing to the IGW.
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
# AWS Lake Formation

**AWS Lake Formation** simplifies setting up, securing, and managing an S3-based data lake.

### Key Exam Points
- **Security**: Centralized, **fine-grained access control** (column-level, row-level, and cell-level permissions).
- **Automation**: Uses **Glue Crawlers** and **ETL** to ingest and catalog data from multiple sources.
- **Sharing**: Allows secure **cross-account** data sharing without copying data.
- **Integration**: Provides a unified permissions layer for Athena, Redshift Spectrum, and EMR.
- **Use Case**: Use when you need complex permissions (e.g., "User A can only see columns 1-3") on S3 data.
# Amazon Lex

**Amazon Lex** is a service for building conversational interfaces (chatbots) using voice and text.

### Key Exam Points
- **Technology**: Built on the same deep learning (ASR and NLU) that powers **Alexa**.
- **Fulfillment**: Commonly uses **AWS Lambda** for backend logic processing.
- **Multi-Channel**: Deploys to web, mobile, Amazon Connect (call centers), and messaging apps (Slack, Facebook).
- **vs. Others**: 
    - **Polly**: Text-to-speech.
    - **Transcribe**: Speech-to-text.
    - **Lex**: Full conversational AI (understanding intent).
# AWS Application Migration Service (AWS MGN)

The primary service for lift-and-shift migrations (rehosting) to AWS. It simplifies and automates the process of migrating applications from physical, virtual, or cloud servers to AWS.

### Key Exam Points
- **Migration Strategy**: Specifically designed for **Rehost (Lift-and-Shift)**.
- **Continuous Replication**: Performs **block-level, asynchronous replication** of the source disks into a staging area in your AWS account.
- **Minimal Downtime**: Applications remain active during replication; downtime only occurs during the final cutover.
- **Broad Support**: Works with physical servers, VMware vSphere, Microsoft Hyper-V, and other cloud providers (GCP, Azure).
- **Staging Area**: Uses low-cost EC2 instances and EBS volumes to minimize costs during the replication phase.
- **Post-Launch Actions**: Can automate optimization of migrated instances (e.g., installing AWS systems manager agent, converting licenses).
- **Replacement**: It is the successor to **CloudEndure Migration**.
# AWS Network Firewall

**AWS Network Firewall** is a managed, stateful firewall and IDS/IPS for your VPC.

### Key Exam Points
- **Inspection**: Layer 3-7 deep packet inspection; supports Suricata rules.
- **Web Filtering**: Filter outbound traffic based on **domain names** (FQDN).
- **Deployment**: Requires a dedicated **firewall subnet** in each AZ; route tables must be updated to redirect traffic to the firewall endpoint.
- **vs. others**:
    - **Security Groups**: Stateful, instance-level, IP/Port only.
    - **NACLs**: Stateless, subnet-level, IP/Port only.
    - **Network Firewall**: Stateful, VPC-level, deep inspection (Layer 7).
- **Automation**: Managed high availability and automatic scaling.
# AWS Organizations & SCPs

**AWS Organizations** provides central management and consolidated billing for multiple AWS accounts.

### Key Exam Points
- **Service Control Policies (SCPs)**: JSON policies that define **maximum permissions** for member accounts/OUs.
    - **Restriction Only**: SCPs do NOT grant permissions; they only restrict what IAM can allow.
    - **Root Account**: SCPs apply to all users/roles in an account, **including root**.
    - **Management Account**: SCPs do **NOT** apply to the management (master) account.
- **Consolidated Billing**: Aggregates usage across accounts for volume discounts (e.g., S3 storage).
- **Structure**: Uses Organizations, Organizational Units (OUs), and Accounts.
- **Governance**: Centrally manage backups (Backup Policies), tags (Tag Policies), and guardrails (SCPs).
# AWS Outposts

**AWS Outposts** extends AWS infrastructure, services, and APIs to on-premises data centers or co-location facilities.

### Key Exam Points
- **Hybrid Cloud**: Run AWS services (EC2, S3, RDS, EBS) *locally* on AWS-provided hardware.
- **Low Latency**: Ideal for apps requiring single-digit millisecond latency to on-premises systems.
- **Data Residency**: Used when data must remain in a specific geographic location for compliance.
- **Networking**: Connects to the AWS Region via Direct Connect or VPN; uses **Local Gateway (LGW)** to route traffic to your on-premises network.
- **Management**: Fully managed by AWS (monitoring, patching, and hardware replacement).
# Amazon Pinpoint

**Amazon Pinpoint** is a multi-channel marketing communication service for customer engagement.

### Key Exam Points
- **Multi-Channel**: Supports Email, SMS, Push Notifications, Voice, and In-App messages.
- **Segmentation**: Create dynamic groups of users based on attributes and behaviors for targeted campaigns.
- **Journeys**: Design multi-step customer workflows (e.g., "if user clicks, send SMS").
- **vs. SES**: SES is for high-volume email; Pinpoint is for **targeted marketing, segmentation, and campaigns** across multiple channels.
- **vs. SNS**: SNS is for service-to-service pub/sub; Pinpoint is for **end-user marketing**.
# Amazon RDS (Relational Database Service)

**Amazon RDS** is a managed relational database service supporting MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, and Aurora.

### Key Exam Points
- **High Availability (Multi-AZ)**: Synchronous replication to a standby instance in another AZ; automatic failover.
- **Read Scalability (Read Replicas)**: Asynchronous replication for scaling read traffic (can be cross-region).
- **RDS Proxy**: 
    - **Connection Pooling**: Reduces DB load by sharing connections; ideal for **Lambda**.
    - **Failover**: Reduces failover time by up to 66%.
    - **Security**: Enforces IAM auth; hides DB behind a VPC endpoint (never public).
- **Storage**: Supports **Storage Auto Scaling** and encryption at rest (KMS).
- **Backup**: Automated backups (up to 35 days) and manual snapshots.
# Amazon Redshift

**Amazon Redshift** is a petabyte-scale, columnar data warehouse optimized for OLAP (Online Analytical Processing).

### Key Exam Points
- **Performance**: Columnar storage reduces I/O for complex analytical queries; uses a cluster-based architecture (Leader + Compute nodes).
- **Redshift Spectrum**: Query data **directly from S3** (data lake) without loading it into Redshift.
- **Concurrency Scaling**: Automatically adds transient capacity to handle spikes in concurrent users/queries.
- **Materialized Views**: Pre-computed results for faster query performance on predictable workloads.
- **Redshift vs. RDS**: Redshift is for **Analytics (OLAP)**; RDS is for **Transactions (OLTP)**.
- **Backup**: Replicates data within the cluster and can back up to S3 (cross-region snapshot support).
# Amazon Redshift vs. AWS Lake Formation

### Comparison Overview
- **Redshift (Data Warehouse)**: **Schema-on-Write** (structured); high-performance SQL analytics; storage is coupled with compute (though Spectrum decouples).
- **Lake Formation (Data Lake Layer)**: **Schema-on-Read** (unstructured/semi-structured); manages permissions and blueprints on top of **Amazon S3**.

### Key Exam Points
- **Security**: Lake Formation provides centralized, **fine-grained (row/column level)** access control for S3 data.
- **Integration**: The "Lake House" architecture uses **Redshift Spectrum** to query data managed by Lake Formation in S3.
- **Use Case**: 
    - **Redshift**: High-speed BI reporting and dashboards.
    - **Lake Formation**: Managing access to raw logs and large datasets in S3 for multiple services (Athena, EMR).
# AWS Resource Groups & Tag Editor

**AWS Resource Groups** and **Tag Editor** help organize and manage AWS resources at scale.

### Key Exam Points
- **Resource Groups**: Allow you to "group" resources based on tags or CloudFormation stacks.
    - **Automation**: Perform bulk actions on group members via **Systems Manager** (e.g., patching all "Production" instances).
- **Tag Editor**: A global tool to "find" resources (especially cross-region) and "bulk tag" them.
- **Scenario**: Use Resource Groups to create application-centric views and automate management tasks across multiple regions.
# Amazon Route 53

**Amazon Route 53** is a highly available and scalable DNS, domain registration, and health checking service.

### Key Exam Points
- **Routing Policies**:
    - **Simple**: Returns one/all records; no health checks.
    - **Weighted**: Distributes traffic by % (useful for A/B testing/canary releases).
    - **Latency**: Directs users to the region with the lowest latency.
    - **Failover**: Active-Passive configuration for disaster recovery.
    - **Geolocation**: Routes based on the user's actual physical location (e.g., show European users an EU-localized site).
    - **Geoproximity**: Routes based on geography plus a "bias" to expand/shrink the reach of a specific region.
    - **Multi-value Answer**: Returns up to 8 healthy records randomly for simple load balancing.

### Hosted Zones
- **Public Hosted Zone**: Responds to queries on the public internet.
- **Private Hosted Zone**: Responds to queries within one or more VPCs (requires setting `enableDnsHostnames` and `enableDnsSupport` to true in VPC).

### Alias vs. CNAME
- **CNAME**: Maps one domain name to another; **cannot be used for the Zone Apex (Root Domain)**.
- **Alias Record**: Route 53 specific; maps the Zone Apex to an AWS resource (e.g., `example.com` -> `lb-123.aws.com`). Unlike CNAME, **Alias queries are free** for most AWS resources and always return an IP (improving performance).

### Route 53 Resolver
- **Inbound Endpoint**: Allows on-premises networks to resolve DNS names in your AWS VPC.
- **Outbound Endpoint**: Allows VPC instances to resolve DNS names in your on-premises network.
- **Hybrid DNS**: Key for SAA-C03; establishes a bridge between on-prem and cloud DNS.

### Health Checks & Traffic Flow
- **Calculated Health Checks**: Combine results from multiple health checks using OR/AND/NOT logic.
- **Traffic Flow**: Visual editor for complex routing logic (e.g., Latency + Geoproximity).

# Amazon Simple Storage Service (S3)

**Amazon S3** is an object storage service providing industry-leading scalability and availability.

### Key Exam Points
- **Consistency**: Strong read-after-write consistency for all operations.
- **Storage Classes**:
    - **Standard**: Frequently accessed (Hot).
    - **Intelligent-Tiering**: Unknown/changing patterns (auto-moves data).
    - **Standard-IA / One Zone-IA**: Infrequently accessed (Warm); lower cost but has retrieval fees.
    - **Glacier (Instant/Flexible/Deep)**: Archival (Cold); retrieval times from milliseconds to 48 hours.
- **Features**:
    - **Versioning**: Protects against accidental deletion.
    - **Lifecycle Rules**: Automates transitions/deletions.
    - **Replication**: CRR (Cross-Region) for DR; SRR (Same-Region) for logs/sync.
    - **MFA Delete**: Extra security for deletions.
- **Security**: IAM policies (Identity), Bucket policies (Resource), and encryption (SSE-S3, SSE-KMS, SSE-C).
- **Object Lock**: Write-Once-Read-Many (WORM) for compliance.
# Amazon S3 Transfer Acceleration

**S3 Transfer Acceleration** enables fast, secure file transfers over long distances using Amazon CloudFront’s edge locations.

### Key Exam Points
- **Mechanism**: Data is uploaded to a nearby Edge Location and then routed over the optimized AWS backbone network to the S3 bucket.
- **Use Case**: Global customers uploading large files to a centralized bucket across continents.
- **Setup**: Must be enabled on the bucket; use the specific endpoint: `bucketname.s3-accelerate.amazonaws.com`.
- **Differentiator**: Best for **regular** high-speed uploads from varied geographic locations.
# AWS Savings Plans

**Savings Plans** is a flexible pricing model offering significant discounts in exchange for a monetary commitment ($/hour) for 1 or 3 years.

### Key Exam Points
- **Compute Savings Plans**: **Max Flexibility**. Applies to **EC2, Fargate, and Lambda** regardless of region, family, OS, or tenancy.
- **EC2 Instance Savings Plans**: **Max Discount** (up to 72%). Specific to an instance family within a region (e.g., M5 in us-east-1).
- **SageMaker Savings Plans**: Applies specifically to SageMaker usage.
- **vs. Reserved Instances**: Savings Plans are generally easier to manage and offer more flexibility (especially Compute plans covering Fargate/Lambda).
- **Scenario**: Choose **Compute Savings Plans** for mixed workloads (EC2 + Lambda) or when instance families/regions might change.
# AWS Service Catalog

**AWS Service Catalog** allows organizations to create and manage a catalog of approved IT services for users to provision.

### Key Exam Points
- **Governance**: Ensures compliance by limiting users to **pre-approved, standardized** resources (products).
- **Structure**: Administrators organize products into **Portfolios** and share them with specific IAM users/groups.
- **Constraints**: Rules that limit how products are deployed (e.g., allowed instance types, required tags).
- **Use Case**: Self-service portal for developers to launch compliant infrastructure (via CloudFormation) without direct access to full AWS services.
- **vs. Marketplace**: Service Catalog is for internal, company-approved products; Marketplace is for 3rd-party software.
# AWS Snow Family

The **AWS Snow Family** provides physical devices for massive data migration and edge computing in disconnected environments.

### Key Exam Points
- **Snowcone**: Smallest (8-14 TB); portable/rugged; includes **DataSync** for online transfer.
- **Snowball Edge**: Briefcase-sized (80-210 TB); rugged.
    - **Storage Optimized**: For large data migrations.
    - **Compute Optimized**: High CPU/GPU for local processing (ML, Video).
- **Snowmobile**: Semi-trailer (up to 100 PB); for exabyte-scale migrations.
- **Use Case**: Data migration where internet bandwidth is the bottleneck or edge computing in remote areas (ships, mines).
- **Security**: Data is encrypted; TPM (Trusted Platform Module) ensures tamper-resistance.
# AWS Storage Gateway

**AWS Storage Gateway** is a hybrid cloud storage service providing on-premises access to cloud storage.

### Key Exam Points
- **S3 File Gateway**: NFS/SMB access to files stored as **objects in S3**; includes local caching.
- **FSx File Gateway**: SMB access to **FSx for Windows File Server** with local caching.
- **Volume Gateway**: iSCSI block storage.
    - **Cached**: Data in S3, frequent data cached locally.
    - **Stored**: Data locally, periodic EBS snapshots stored in S3.
- **Tape Gateway**: Replaces physical tapes with **virtual tapes** backed by S3/Glacier (VTL).
- **Deployment**: Virtual Appliance (VMware/Hyper-V) or hardware appliance on-premises.
- **Common Use Case**: Disaster recovery, data migration to S3, and cloud-backed local file shares.
# AWS Transit Gateway

**AWS Transit Gateway** acts as a central hub (router) to connect multiple VPCs and on-premises networks.

### Key Exam Points
- **Topology**: Hub-and-spoke model; simplifies connectivity by avoiding a full mesh of VPC peering.
- **Transitive Routing**: Allows VPC A to talk to VPC C through the hub (not possible with standard peering).
- **Attachments**: Supports VPCs, VPNs, Direct Connect Gateways, and peering with other Transit Gateways.
- **Security**: Centralized control via Transit Gateway route tables; supports **IP Multicast**.
- **Use Case**: Connecting dozens or hundreds of VPCs and site-to-site VPNs.
# Virtual Private Gateway (VGW)

A **Virtual Private Gateway** is the VPN concentrator on the AWS side of a Site-to-Site VPN or Direct Connect connection.

### Key Exam Points
- **Function**: Receives VPN/DX traffic and routes it into your VPC.
- **Constraints**: You can attach only **one** VGW to a VPC at a time.
- **Customer Gateway (CGW)**: The corresponding physical or software appliance on the on-premises side.
- **Propagation**: Enable **Route Propagation** to automatically update VPC route tables with on-premises routes.
# Amazon VPC

**Amazon VPC** lets you launch AWS resources into a defined virtual network.

### Key Exam Points
- **Subnets**:
    - **Public**: Has a route to an **Internet Gateway (IGW)**.
    - **Private**: No direct route to IGW; uses **NAT Gateway** for outbound-only access.
- **Reserved IPs**: AWS reserves **5 IP addresses** in every subnet (first 4 and last 1).
- **Routing**: Each subnet must be associated with a **Route Table**. Unassociated subnets use the **Main Route Table**.
- **Security**:
    - **Security Groups**: Stateful; instance-level; Allow-only rules.
    - **NACLs**: Stateless; subnet-level; Allow/Deny rules; processed in order.
- **Peering**: Direct connection between two VPCs; **not transitive**.
# AWS VPC Endpoints

**VPC Endpoints** enable private connections between your VPC and AWS services without using an Internet Gateway or NAT.

### Key Exam Points
- **Gateway Endpoints**:
    - **Services**: Only **S3** and **DynamoDB**.
    - **How**: Adds a target to the route table.
    - **Cost**: **Free**.
- **Interface Endpoints (PrivateLink)**:
    - **Services**: Most other services (EC2, Kinesis, SNS, sqs, etc.).
    - **How**: Uses an **ENI (Private IP)** in your subnet.
    - **Cost**: Hourly fee + data processing fee.
- **On-Prem Access**: Interface endpoints (PrivateLink) are accessible from on-premises via VPN/DX; Gateway endpoints are not.
# VPC Flow Logs

**VPC Flow Logs** capture information about IP traffic going to and from network interfaces in your VPC.

### Key Exam Points
- **Capture Levels**: VPC, Subnet, or individual Elastic Network Interface (ENI).
- **Destinations**: CloudWatch Logs, S3, or Kinesis Data Firehose.
- **Use Case**: 
    - **Troubleshooting**: Identify if Security Groups or NACLs are blocking traffic (`REJECT` vs. `ACCEPT`).
    - **Security**: Monitor for unusual traffic patterns.
- **Tip**: Flow logs do NOT capture all traffic (e.g., DNS queries to Amazon DNS, AWS service traffic, or traffic to `169.254.169.254`).
# Amazon VPC Peering

**VPC Peering** is a networking connection between two VPCs that allows traffic to flow privately using AWS's internal network.

### Key Exam Points
- **Connectivity**: Private (stays on AWS backbone); no internet involved. Works cross-account and cross-region.
- **Constraints**: **Not transitive** (A-B, B-C does NOT mean A-C). CIDR blocks must **not overlap**.
- **Management**: No gateway or VPN device; it's a logical link in the VPC routing layer.
- **Use Case**: Simple connection between a few VPCs where full bandwidth is required.
- **vs. Transit Gateway**: Use Transit Gateway for complex hub-and-spoke needs (more than a few VPCs).
# AWS VPC Sharing

**VPC Sharing** allows multiple accounts in the same AWS Organization to launch resources into a centrally managed, shared VPC.

### Key Exam Points
- **Mechanism**: Powered by **AWS Resource Access Manager (RAM)**.
- **Benefits**: Centralized network management; cost savings (fewer NAT Gateways, VPC endpoints); simplified network topology.
- **Roles**:
    - **Owner**: Manages subnets, route tables, NACLs, and gateways.
    - **Participant**: Launches resources (EC2, RDS, etc.) into shared subnets and manages their own security groups.
- **Scope**: Sharing is limited to accounts within the **same AWS Organization**.
# AWS Wavelength

**AWS Wavelength** embeds AWS compute and storage services within telecommunications providers' **5G networks**.

### Key Exam Points
- **Goal**: Ultra-low latency (single-digit milliseconds) for mobile devices and users.
- **Networking**: Traffic stays within the mobile operator's network, avoiding hops to the public internet.
- **Carrier Gateway**: Connects the Wavelength Zone to the carrier's network.
- **Use Case**: Mobile gaming, AR/VR, autonomous vehicles, and real-time ML inference for edge devices.
- **Key Word**: **5G**. If the question mentions 5G and ultra-low latency, the answer is Wavelength.
# Amazon WorkDocs

**Amazon WorkDocs** is a managed, secure enterprise storage and collaboration service (document management).

### Key Exam Points
- **Collaboration**: Supports feedback, versioning, and internal/external sharing.
- **Identity**: Integrates with Active Directory (AD Connector or Managed AD) for corporate credential usage.
- **Storage**: Highly secure; encrypted at rest (KMS) and in transit.
- **WorkDocs Drive**: Maps WorkDocs storage as a virtual drive on Windows/macOS.
- **Auditing**: Integrates with **CloudTrail** for comprehensive activity logging (who viewed/shared what).
- **vs. WorkSpaces**: WorkDocs is for **files/collaboration**; WorkSpaces is for **virtual desktops**.
# Amazon WorkSpaces

A managed, secure Desktop-as-a-Service (DaaS) solution. It helps you provision either Windows or Linux desktops in just a few minutes and quickly scale to provide thousands of desktops to workers across the globe.

### Key Exam Points
- **Desktop-as-a-Service (DaaS)**: Cloud-based virtual desktop that replaces traditional VDI (Virtual Desktop Infrastructure).
- **Persistent Storage**: Data is saved on the user's volume (D drive) and backed up to S3 automatically.
- **Security**: 
    - Data is encrypted at rest (via KMS) and in transit.
    - Integrates with **AWS Directory Service** (Managed Microsoft AD or AD Connector) for user authentication.
    - No data is stored on the local device used to access the WorkSpace.
- **Bundles**: Pre-configured hardware and software combinations (Value, Standard, Performance, Power, PowerPro, Graphics, GraphicsPro).
- **Pricing**: 
    - **Monthly**: Unlimited usage for a fixed monthly fee.
    - **Hourly**: Low monthly base fee plus a small hourly rate (best for part-time workers).
- **Network**:
    - Requires two subnets in a VPC.
    - Uses a "WorkSpaces Gateway" to stream the desktop to the client.
- **Protocol**: Supports **PCoIP** and **WSP** (Windows Streaming Protocol).

### Use Cases
- Remote work / Work from home.
- Contractors and temporary employees.
- High-security environments (data never leaves the VPC).
- Bring Your Own License (BYOL) for Windows 10/11 (requires dedicated physical hardware).
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
# Data Transfer and Migration Comparison

### Online Connectivity
- **Site-to-Site VPN**: Encrypted tunnel over **public internet**; fast setup; variable performance.
- **Direct Connect (DX)**: Dedicated **private connection**; bypasses internet; consistent performance; slow setup (weeks).

### Bulk Data Migration
- **Snow Family (Offline)**: Physical devices for **petabyte/exabyte** scale; best for limited/no internet.
- **DataSync (Online)**: Automated, accelerated transfers for **active data** (NFS, SMB, S3).
- **Transfer Family (Online)**: Managed **SFTP/FTP** entry point for S3 or EFS.
- **S3 Transfer Acceleration**: Faster **S3 uploads** over the internet via CloudFront Edge Locations.
- **Storage Gateway (Hybrid)**: On-premises caching and access to cloud storage.
- **Application Migration Service (MGN)**: [Automated server migration](aws_mgn.md) (Rehost/Lift-and-Shift).

# AWS Database Services Comparison

| Service | Type | Key Use Case | Key Performance |
| :--- | :--- | :--- | :--- |
| **RDS** | Relational | Traditional apps (ERP/CRM) | Vertical scaling; Read Replicas. |
| **Aurora** | Relational | High-perf enterprise/SaaS | 5x MySQL; Auto-scaling storage. |
| **DynamoDB** | NoSQL | Mobile, gaming, serverless | Single-digit ms; horizontal scale. |
| **ElastiCache**| In-Memory | Caching, session store | Microsecond latency; Redis/Memcached. |
| **DocumentDB** | Document | Content mgmt; MongoDB apps | Fully managed MongoDB compatibility. |
| **Neptune** | Graph | Social nets; fraud detection | High-speed relationship traversal. |
| **Timestream** | Time Series | IoT; DevOps monitoring | Scalable time-series storage. |
| **Redshift** | Warehousing | BI; Analytics (OLAP) | Petabyte-scale; Columnar storage. |
| **QLDB** | Ledger | Banking; System of record | Immutable; Cryptographically verifiable. |
# Deployment Strategies

### 1. Canary
- **Goal**: Roll out to a small % of users first.
- **Services**: API Gateway (Canary Release), Lambda (Aliases + Traffic Shifting), ALB (Weighted Target Groups).

### 2. Blue/Green
- **Goal**: Zero downtime; instant rollback by switching all traffic to a new, identical environment.
- **Services**: Route 53 (Weighted), Elastic Beanstalk (CNAME swap), CodeDeploy.

### 3. Rolling
- **Goal**: Update instances in batches (reduced capacity during deployment).
- **Services**: Auto Scaling (Instance Refresh), Elastic Beanstalk.

### 4. All-at-Once
- **Goal**: Fastest, but involves **downtime**. Best for dev/test environments.

### Exam Comparison
- **Instant Rollback?** Blue/Green.
- **Real User Testing?** Canary.
- **Minimize Cost?** All-at-Once (if downtime is okay) or Rolling.
# Comparison: Amazon EKS vs. EKS Anywhere vs. EKS Distro

| Feature | **Amazon EKS** | **EKS Anywhere** | **EKS Distro** |
| :--- | :--- | :--- | :--- |
| **Location** | AWS Cloud | On-Premises / Hybrid | Anywhere |
| **Managed By** | AWS (Control Plane) | You (with AWS tools) | You (Manual) |
| **Best For** | Managed K8s in AWS | Running EKS on-prem | Custom K8s builds |
| **Cost** | Hourly fee + resources | Open source (free) | Free |
# Federation Proxy (Identity Broker)

A **Federation Proxy** is an intermediary that authenticates users against a corporate ID store and requests temporary AWS credentials.

### Key Exam Points
- **Custom IdP**: Use when the corporate store (LDAP, DB) does **not** support SAML 2.0.
- **STS API Actions**:
    - `AssumeRole`: Basic role assumption.
    - `AssumeRoleWithSAML`: For SAML 2.0 IdPs (Okta, ADFS).
    - `AssumeRoleWithWebIdentity`: For social logins (via Cognito).
    - `GetFederationToken`: Often used by custom proxies to get scoped credentials.
- **Cognito**: Preferred for mobile/web apps with social or guest identities.
- **Temporary Credentials**: All methods return short-lived access keys and tokens.
# HLS (HTTP Live Streaming)

**HLS** is the standard protocol for adaptive bitrate video streaming over HTTP/S.

### Key Exam Points
- **Architecture**: Breaks video into small chunks (segments) referenced by a manifest file (`.m3u8`).
- **Scalability**: Designed for massive scale via **Amazon CloudFront** caching (Edge Locations).
- **AWS Workflow**: S3 (Storage) -> **MediaConvert** (Transcode to HLS) -> CloudFront (Distribution).
- **Adaptive Bitrate (ABR)**: Automatically adjusts video quality based on the user's network speed.
- **vs. RTMP**: RTMP is legacy/deprecated; HLS is the modern, scalable standard for CDNs.
# LDAP (Lightweight Directory Access Protocol)

**LDAP** is a standard protocol for accessing distributed directory services (e.g., Active Directory).

### Key Exam Points
- **Identity Store**: Typically represents an on-premises corporate directory in SAA-C03 questions.
- **Integration**:
    - **Identity Broker**: Use a custom proxy calling **STS (`GetFederationToken` or `AssumeRole`)** if the LDAP store doesn't support SAML.
    - **AD Connector**: Use if the LDAP store is part of an Active Directory environment.
- **Security**: Use **LDAPS** (LDAP over SSL) for secure communication over VPN/Direct Connect.
- **vs. SAML**: SAML is for SSO (federation); LDAP is for querying/authenticating against the directory.
# Comparison: SQS vs. Amazon MQ vs. Amazon MSK

| Feature | **Amazon SQS** | **Amazon MQ** | **Amazon MSK** |
| :--- | :--- | :--- | :--- |
| **Primary Use**| Cloud-native decoupling | Migrating legacy brokers | Real-time event streaming |
| **Protocols** | AWS HTTP API | AMQP, MQTT, STOMP | Kafka (TCP) |
| **Scaling** | **Infinite/Serverless** | Limited by instance | Cluster/Broker based |
| **Legacy App** | No | **Yes** (ActiveMQ/RabbitMQ) | No |
| **High Throughput**| Medium/High | Low/Medium | **Ultra-High** |
# Microsoft Active Directory & AD FS

**Active Directory (AD)** is a central user database, while **AD FS** provides SAML-based federation for SSO.

### Key Exam Points
- **SAML Federation**: User -> AD FS -> SAML Token -> STS (`AssumeRoleWithSAML`) -> AWS Console.
- **AWS Managed Microsoft AD**: A managed AD in the cloud; supports **Forest Trusts** (Sync/Share with on-premises).
- **AD Connector**: A **proxy** (no caching) for using on-premises AD with AWS services (WorkSpaces, QuickSight).
- **Tip**: Use **AD FS** for general AWS access; use **AD Connector** for specific AWS application integration.
- **Availability**: Always deploy in at least **two AZs**.
# SAML 2.0 (Security Assertion Markup Language)

**SAML 2.0** is the XML standard for exchanging authentication/authorization data between an Identity Provider (IdP) and a Service Provider (SP).

### Key Exam Points
- **Workflow**: Identity Provider (Okta, ADFS) -> SAML Assertion -> browser redirect -> AWS STS (`AssumeRoleWithSAML`) -> Temporary Credentials.
- **IAM Setup**: Upload the **SAML Metadata document** from the IdP to create an IAM Identity Provider.
- **Role Trust**: The IAM Role's trust policy must allow the SAML IdP as the Principal.
- **Single Sign-On (SSO)**: The primary answer for "SSO with existing corporate identities using standard protocols."
- **vs. Web Identity**: SAML is for enterprise; **Cognito** is for social/mobile web identities.
# Auto Scaling Policy Comparison

| Policy Type | Goal | Best Use Case |
| :--- | :--- | :--- |
| **Target Tracking** | Maintain a specific metric | "Keep average CPU at 50%". Default recommendation. |
| **Step Scaling** | Incremental response | Aggressive scaling (e.g., add 2 if CPU > 60%, add 4 if > 80%). |
| **Scheduled Scaling**| Predictable timing | Weekend surges or morning/evening batch jobs. |
| **Predictive Scaling**| Proactive ML-based | Regular traffic patterns (spikes predicted 48h ahead). |
| **Simple Scaling** | Single adjustment | Legacy; use Step Scaling instead. |

### Key Exam Points
- **Target Tracking**: Simplest for maintaining metrics; automatically creates CloudWatch alarms.
- **Step Scaling**: Best for handling variable traffic with specific responses.
- **Predictive**: Uses ML to provision capacity *before* it is needed.
