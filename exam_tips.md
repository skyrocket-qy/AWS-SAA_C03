# Appflow
- Remember **PrivateFlow** for security requirements (using AWS PrivateLink to keep traffic off the public internet).
- Ideal for **SaaS-to-AWS** or **SaaS-to-SaaS** integrations without managing infrastructure.
- Differentiate from **AWS DataSync** (storage-to-storage) and **AWS Database Migration Service** (database-to-database).


---

# Application Discovery Service
- **Planning phase**: Use Application Discovery Service *before* migration to discover what you have.
- **Dependency Mapping**: If the question asks to "identify dependencies between servers" or "map network connections" for migration, choose **Agent-based** discovery.
- **VMware**: If managing VMware vCenter and want a quick/easy setup without installing software on every VM, choose **Agentless**.
- **Privacy**: Does not collect application data or content (e.g., database records).


---

# Aurora
- **Aurora Global Database** = Cross-region DR with < 1 second replication lag, < 1 minute RTO.
- **Aurora Serverless v2** = Near-instant scaling, works with Global Database.
- **Backtrack** = Quickly undo mistakes without restoring from backup (no new cluster).
- **Cloning** = Fast creation of test environment from production (copy-on-write).


---

# Autoscaling
- **Desired Capacity**: If a question asks how to ensure 3 instances are *always* running even if one fails, the answer is to set **Desired Capacity = 3** (and Minimum = 3).
- **Health Checks**: If instances are running but the application is failing, ensure the ASG is using **ELB Health Checks**, not just EC2 Health Checks.
- **Scaling Policies**: Refer to [scaling_policy_comparison.md](file:///Users/qy/skyro/aws-saa_c03/services/scaling_policy_comparison.md) for details on Target Tracking vs. Predictive scaling.
- **Availability**: ASG always tries to balance instances across the **Availability Zones** configured for the group.


---

# Batch
- **AWS Batch vs Lambda**:
    - Use **Lambda** for short-running (< 15 min), event-driven tasks.
    - Use **Batch** for long-running, complex jobs (dockerized) that need extensive compute resources.
- **Compute Environments**: "Managed" is usually the right answer unless you need specific, unsupported configurations.
- **Spot Instances**: Great for batch jobs to save costs (Batch handles interruptions and retries if configured).


---

# Budgets
- **Proactive Alerts**: AWS Budgets is the primary tool for **setting alerts** when costs exceed a defined limit.
- **Forecast vs. Actual**: Alerts can be triggered on **actual** spend or **forecasted** spend.
- **Actions**: Remember that Budgets can trigger **actions** (via Chatbot to Slack, or Systems Manager to stop instances), not just send emails.
- Difference from **Cost Explorer**: Cost Explorer is for **analyzing** historical data and trends; Budgets is for **planning** and **alerting**.


---

# Cloudfront
- Use **Lambda@Edge** to inspect/modify `User-Agent` or other headers for device-specific content.
- Use **CloudFront Functions** for simple, high-volume tasks (header manipulation, redirects).
- Lambda@Edge functions must be deployed in **us-east-1** (N. Virginia).


---

# Cloudhsm
- **FIPS 140-2 Level 3**: If a question mentions this specific compliance requirement, the answer is almost always **CloudHSM**.
- **Dedicated Hardware**: If the requirement is for keys to be stored on dedicated, single-tenant hardware, choose **CloudHSM**.
- **No AWS Access**: If the customer must have *exclusive* control over the keys such that AWS admins cannot access them, use **CloudHSM**.
- **Management Overhead**: Remember that CloudHSM comes with significantly more management overhead than KMS (backups, user management inside the HSM, scaling).


---

# Cloudwatch
- **Internal Metrics**: If the exam asks how to monitor **Memory**, **Disk Space (Internal)**, or **Logs**, the answer is almost always the **CloudWatch Agent**.
- **Detailed Monitoring**: Enabling Detailed Monitoring on EC2 changes the metric frequency from 5 minutes to **1 minute**. It does NOT provide memory metrics; you still need the agent for that.
- **Custom Metrics Resolution**: High-resolution metrics allow for 1-second resolution, useful for rapid scaling decisions.
- **Logs**: CloudWatch Logs can be exported to S3 (for long-term storage) or streamed to Kinesis Data Firehose (for real-time analysis in OpenSearch).


---

# Control Tower
- **Control Tower = Multi-account governance** (landing zone + guardrails).
- For "easiest way to set up a multi-account environment", think **Control Tower**.
- **Preventive = SCPs**, **Detective = Config Rules**.
- Control Tower uses **AWS Organizations** under the hood.
- Related services: AWS Organizations, AWS SSO (IAM Identity Center), AWS Config.


---

# Cost And Usage Report
- **Most Detailed**: If a question asks for the **most granular** or **most detailed** information about costs (e.g., down to the hour or specific resource ID), the answer is **Cost and Usage Report**.
- **Storage**: Always remember it is delivered to **S3**.
- **Tags**: It supports cost allocation tags, allowing you to break down costs by project, environment, or team.
- **Retention**: Offers historical data retention depending on your S3 lifecycle policies.


---

# Cost Explorer
- **Cost Explorer** = *Visualize* and *forecast* costs.
- **AWS Budgets** = *Alert* when exceeding a budget.
- **Cost and Usage Report** = *Raw data export* to S3 (for Athena/QuickSight analysis).
- Use Cost Explorer's **Rightsizing Recommendations** to identify underutilized EC2 instances.
- Cost Explorer data is available after ~24 hours of account activity.


---

# Data Exchange
- **Third-party data acquisition**: AWS Data Exchange is the go-to service for finding and subscribing to external datasets.
- Differentiate from **AWS Marketplace** (general software/services) — Data Exchange is specifically for data products.
- Integrates seamlessly with **Amazon S3** for data delivery and storage.
- Useful when the question mentions acquiring **external/third-party data** for analytics or ML.


---

# Data Exchange Vs Pipeline
- If the question mentions **third-party**, **external**, or **marketplace**, look for **Data Exchange**.
- If the question mentions **scheduling**, **workflow**, or **orchestrating ETL**, look for **Data Pipeline** (though modern questions may favor Glue or Step Functions).


---

# Data Pipeline
- **Legacy service**: AWS Data Pipeline is considered a legacy orchestration service; for new workloads, AWS recommends **AWS Step Functions** or **Amazon MWAA (Managed Workflows for Apache Airflow)**.
- Ideal for **scheduled, data-centric ETL jobs** across AWS services.
- Supports **on-premises data sources** via Task Runner installed on your servers.
- Differentiate from **AWS Glue** (serverless ETL with schema discovery) and **Step Functions** (general-purpose workflow orchestration).


---

# Device Farm
- **Real Devices**: If a question asks about testing on **real mobile devices** or browsers, the answer is Device Farm.
- Differentiate from **AWS Amplify** (building/hosting apps) — Device Farm is specifically for **testing**.


---

# Directory Service
- **Managed Microsoft AD** = Full AD with trusts (two-way trust with on-premises).
- **AD Connector** = Proxy to on-premises AD (no data in AWS, no caching).
- **Simple AD** = Basic, low-cost, Linux-based (no trusts, no advanced features).
- If the question mentions "trust relationship" or "replicate users", choose **Managed Microsoft AD**.
- If the question says "use existing on-premises AD without storing data in AWS", choose **AD Connector**.


---

# Dynamodb
- **PITR** is for the last 35 days.
- **Global Tables** require DynamoDB Streams to be enabled.
- **DAX** is for read-intensive workloads where microsecond latency is needed.
- **Partition Key** vs. **Sort Key**: Understand how they affect data distribution and query flexibility.


---

# Ec2
- Use **Spot Instances** for any workload that can handle interruptions (max cost savings).
- Use **Reserved Instances (Standard)** for steady-state usage where requirements won't change.
- Use **Convertible RIs** if you need flexibility to change instance families later.
- Use **Compute Savings Plans** for maximum flexibility across Fargate and Lambda usage as well.


---

# Elastic Beanstalk
- **PaaS**: Elastic Beanstalk is a **Platform as a Service (PaaS)**. It is the best choice for developers who want to deploy code without worrying about infrastructure management.
- **Deployment Strategies**: Know the difference between **All at Once** (downtime), **Rolling** (reduced capacity), and **Immutable** (full capacity, zero downtime, most expensive/slowest).
- **Worker Tier**: If a question mentions a background task processing an **SQS queue**, the answer is the Elastic Beanstalk **Worker Tier**.
- **Configuration**: Extensions to Beanstalk are handled via `.ebextensions/` folder containing YAML or JSON files.
- **Customization**: Use **Docker** if your environment is not supported by standard Beanstalk platforms.


---

# Fsx
- **FSx for Lustre** = **HPC, ML, high-throughput** workloads + **S3 integration**.
- **FSx for Windows** = **SMB**, Active Directory, Windows apps.
- **FSx for NetApp ONTAP** = Multi-protocol (NFS + SMB + iSCSI), hybrid cloud.
- **Scratch vs Persistent**: Scratch = no replication (temporary), Persistent = replication (durable).
- Lustre is **Linux only**; Windows File Server is for **Windows**.


---

# Glue
- **Job Bookmarks** = Process only **new data** (incremental ETL), avoid reprocessing.
- **Data Catalog** = Central **metadata** repository (Hive-compatible metastore).
- **Crawlers** = Automatically infer **schema** and populate Data Catalog.
- Glue is **serverless** (no infrastructure to manage).


---

# Iam Identity Center
- **AWS Organizations**: IAM Identity Center works at the **Organization** level. It is the best choice for managing access to dozens or hundreds of accounts.
- **Centralized Login**: Whenever a scenario asks for a "single portal" or "centralized login" for an entire organization, think **IAM Identity Center**.
- **External AD**: You can connect your on-premises Active Directory to IAM Identity Center using **AD Connector** or **AWS Managed Microsoft AD**.
- **ABAC**: IAM Identity Center supports **Attribute-Based Access Control (ABAC)**, allowing you to use user attributes (like `CostCenter`) in your permission sets.


---

# Lake Formation
- **Lake Formation = Simplified data lake setup + Fine-grained access control**.
- Works on top of **S3** (storage) and **Glue** (catalog + ETL).
- Key differentiator is **centralized, fine-grained permissions** (row/column level).
- Use when you need to grant specific users access to specific columns or rows.
- consolidate data from multiple accounts into a single account.


---

# Lex
- **Conversational AI**: If a question asks about building **chatbots** or **voice assistants**, the answer is **Amazon Lex**.
- **Lambda Integration**: Lex commonly uses Lambda for backend fulfillment.
- Differentiate from **Amazon Polly** (text-to-speech) and **Amazon Transcribe** (speech-to-text) — Lex is the full conversational AI service.


---

# Organizations
- **SCPs do NOT apply to the Management Account**.
- SCPs affect **all users and roles**, including **root**.
- SCPs are about **restricting permissions**, not granting them.
- For "restrict actions across all accounts in an OU", think **SCP**.
- For "easiest way to set up multi-account governance", think **Control Tower** (uses Organizations + SCPs).


---

# Outposts
- Think **"AWS on-premises"**. If a question asks about running AWS infrastructure in your own data center, the answer is likely Outposts.
- **Latency & Residency**: Key drivers for adoption.
- **Managed Service**: Even though it's on-prem, AWS manages, monitors, and patches the infrastructure.


---

# Pinpoint
- **Customer Engagement**: If a question asks about sending **targeted marketing messages** across multiple channels (email, SMS, push), the answer is **Pinpoint**.
- Differentiate from **Amazon SES** (Simple Email Service) which is for high-volume email sending only; Pinpoint adds segmentation, campaigns, and multi-channel support.
- Differentiate from **Amazon SNS** which is for pub/sub messaging between services; Pinpoint is for end-user marketing communications.


---

# Rds
- **RDS Proxy** = **Lambda + RDS** (connection pooling for serverless).
- RDS Proxy is **VPC only** (not publicly accessible).
- **Multi-AZ** = High Availability (HA), **Read Replicas** = Read Scaling.
- RDS Proxy reduces failover time and enforces IAM authentication via Secrets Manager.


---

# Redshift Vs Lake Formation
- **Structured, high-performance SQL** = **Redshift**.
- **Centralized security/permissions for S3 data** = **Lake Formation**.
- **Schema-on-Write** = **Redshift**.
- **Schema-on-Read** = **Lake Formation** (S3 + Glue + Athena).


---

# Resource Groups Tag Editor
- Use **Resource Groups** to "group" resources for application-centric management or automation (Systems Manager).
- Use **Tag Editor** to "find" resources (especially cross-region) or to "bulk tag" resources.
- If the question asks how to apply updates to all EC2 instances in a specific environment, think **Resource Groups** + **Systems Manager**.


---

# Route53
- **Latency** ≠ **Geoproximity**: Latency is based on actual network latency; Geoproximity is based on physical distance with bias.
- **Geolocation** = "Where is the user?" (legal/compliance); **Latency** = "Fastest route?"
- **Failover** requires health checks on the primary.
- **Alias** records are free for AWS resources (unlike CNAME).


---

# Savings Plans
- **Compute Savings Plans** = **Max Flexibility** (Regions, Families, Services: EC2 + Fargate + Lambda).
- **EC2 Instance Savings Plans** = **Max Discount** (Ec2 only, specific Region + Family).
- If the question asks for the "most cost-effective and flexible option for a mix of Fargate and EC2", choose **Compute Savings Plans**.


---

# Service Catalog
- **Approved/Standardized Deployments**: If a question asks about allowing users to deploy **only pre-approved, compliant resources**, the answer is **Service Catalog**.
- **CloudFormation Based**: Products are essentially CloudFormation templates wrapped with governance.
- Differentiate from **AWS Marketplace** (third-party software) — Service Catalog is for internal, organization-defined products.


---

# Storage Gateway
- **S3 File Gateway** = NFS/SMB → S3 (files as objects).
- **FSx File Gateway** = SMB → FSx for Windows (Windows file shares).
- **Volume Gateway (Cached)** = iSCSI, data in S3, cache locally.
- **Volume Gateway (Stored)** = iSCSI, data locally, backup to S3.
- **Tape Gateway** = Virtual tapes → S3 → Glacier (for backup software).
- For "hybrid cloud storage" or "on-premises access to cloud", think **Storage Gateway**.


---

# Wavelength
- **5G Network**: The keyword is **5G**. If a question mentions low latency for mobile devices using 5G, the answer is AWS Wavelength.
- Differentiate from **Outposts** (On-premises) and **Local Zones** (Extension of Region near large population centers, but not specifically inside a telecom 5G network).


---

# Workdocs
- **AD Integration**: If an exam question asks for a secure document storage solution where employees use their **existing corporate AD credentials**, think **WorkDocs + AD Connector**.
- **Sharing**: WorkDocs supports sharing with external users via email-based invites.
- **Audit Trails**: Remember that **CloudTrail** integration is key for tracking "who accessed what" in a regulated environment.


---

# Xray
- **Performance Bottlenecks**: If a question asks how to find **latency issues** or visualize where a specific request is failing in a complex microservices architecture, the answer is **X-Ray**.
- **Service Graph/Map**: Look for keywords like "visualize service dependencies" or "trace requests across multiple components".
- **Cross-Account Tracing**: X-Ray supports tracing requests across multiple AWS accounts.


---

# Deployment Strategies
- **API Gateway**: If the question mentions "Canary," "Stage Variables," or "Traffic %," think **API Gateway**.
- **Lambda**: If the question asks to shift traffic gradually over time (e.g., 10% every 10 minutes) for a serverless function, use **CodeDeploy with Lambda Aliases**.
- **Instant Rollback**: If the requirement is "immediate rollback" in case of failure, **Blue/Green** is the best answer.
- **Minimize Cost**: If cost is the primary factor and some downtime is acceptable, **All-at-Once** is the answer. If no downtime is allowed but cost is still a concern, **Rolling**.


---

# Federation Proxy
- **Custom Identity Store**: If the scenario describes a **custom identity store** (non-SAML, non-OIDC), the answer likely involves a **Federation Proxy** calling `GetFederationToken` or `AssumeRole`.
- **SAML 2.0**: If the IdP supports SAML (like ADFS or Okta), prefer direct SAML federation (`AssumeRoleWithSAML`) over a custom broker.
- **Web Identity**: For mobile/web apps authenticating via social logins (Google, Facebook), use **Amazon Cognito** with `AssumeRoleWithWebIdentity`.
- **Temporary Credentials**: All federation methods return **temporary security credentials** (Access Key, Secret Key, Session Token) with a defined expiration.


---

# Hls
- **Scalability**: If you need to stream video to thousands or millions of users globally, the answer is **S3 + MediaConvert + CloudFront (HLS)**.
- **Performance**: High-resolution video streaming requires CloudFront for caching to reduce latency and origin (S3) load.
- **Protocols**: Remember that **RTMP is deprecated** in CloudFront. Use HLS or DASH for modern streaming requirements.


---

# Ldap
- **"Custom Identity Store"**: If a question mentions a "custom identity store" or an "LDAP server without SAML support," look for the **Identity Broker** or **Federation Proxy** solution.
- **`GetFederationToken`**: This STS API call is often associated with custom identity brokers authenticating against LDAP or other custom databases.
- **LDAPS**: Always use **LDAPS (LDAP over SSL)** when discussing secure communication between your cloud VPC and an on-premises LDAP server.
- **Direct Connect / VPN**: Integrating with an on-premises LDAP requires a secure, private connection (Site-to-Site VPN or Direct Connect).


---

# Microsoft Active Directory
- **AD FS = SAML**: If a question mentions AD FS, the federation protocol is always **SAML 2.0**.
- **Managed AD Trusts**: If you need to log into AWS using your on-premises AD credentials and want to manage resources natively in an AD environment in the cloud, use **AWS Managed Microsoft AD with a Trust Relationship**.
- **AD Connector vs. Federation**: Use **AD Connector** for AWS service integration (WorkSpaces, etc.). Use **Federation (SAML)** for AWS Console/CLI access for thousands of users.
- **High Availability**: Always deploy AD Connectors or Managed AD in at least **two Availability Zones**.


---

# Saml
- **SSO**: If the question asks for "Single Sign-On" for "Existing Corporate Identities" using a "Standard Protocol," the answer is **SAML 2.0**.
- **AssumeRoleWithSAML**: This is the specific STS API call used in SAML federation.
- **Trust Relationship**: The Role used for SAML federation must trust the SAML IdP created in IAM.
- **Automation**: Use SAML to avoid the overhead of managing individual IAM users for every employee.


---

# Scaling Policy Comparison
- **Target Tracking** is usually the right answer for "maintain specific metric" (e.g., maintain average CPU at 40%).
- **Step Scaling** is preferred over Simple Scaling because it handles "flapping" better and doesn't wait for cooldowns (uses instance warm-up).
- **Scheduled Scaling** is for "known time" events (e.g., weekly batch job).
- **Predictive Scaling** is for "proactive" scaling based on historical data.


---


# Services without explicit 'Exam Tips' section (Check manually if needed):

- architecture_three_tier.md
- aws_cloudformation.md
- aws_ebs.md
- aws_ec2_placement_groups.md
- aws_egress_only_internet_gateway.md
- aws_elb.md
- aws_eni.md
- aws_global_accelerator.md
- aws_internet_gateway.md
- aws_kinesis.md
- aws_nat_instance.md
- aws_network_firewall.md
- aws_redshift.md
- aws_s3.md
- aws_s3_transfer_acceleration.md
- aws_snow_family.md
- aws_transit_gateway.md
- aws_virtual_private_gateway.md
- aws_vpc.md
- aws_vpc_endpoints.md
- aws_vpc_flow_logs.md
- aws_vpc_peering.md
- aws_vpc_sharing.md
- data_transfer_comparison.md
- database_comparison.md
- eks_comparison.md
- messaging_comparison.md
