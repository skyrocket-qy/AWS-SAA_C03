# AWS Data Exchange vs. AWS Data Pipeline

While both services involve "data" and its movement, they serve fundamentally different purposes in the AWS ecosystem.

## Comparison Overview

| Feature | AWS Data Exchange | AWS Data Pipeline |
| :--- | :--- | :--- |
| **Primary Purpose** | Finding, subscribing to, and using **third-party data** from providers. | **Orchestrating** and automating data movement and transformation (ETL). |
| **Data Source** | Third-party providers (Financial, Healthcare, etc.). | Your own AWS services (S3, RDS, DynamoDB) or on-premises. |
| **Focus** | **Marketplace** & Data Acquisition. | **Workflow Scheduling** & Data Movement. |
| **Integration** | Directly to your S3 bucket. | Connects multiple AWS services in a dependency-based workflow. |
| **Managed Type** | Fully managed data delivery. | Managed orchestration (you define the pipeline logic). |
| **Modern Alternative**| N/A (Standard for 3rd party data). | **AWS Glue** or **Step Functions** or **Amazon MWAA**. |

---

## Key Differences

### 1. The "Whose Data" Question
- **AWS Data Exchange**: Used when you need data from **someone else** (external vendors). You are looking for a dataset you don't own.
- **AWS Data Pipeline**: Used when you want to move/transform data that **you already have** (internal data).

### 2. Market vs. Engineering
- **AWS Data Exchange** is like a "Data App Store." It handles billing, licensing, and delivery of revisions.
- **AWS Data Pipeline** is like a "Task Scheduler" for data. It handles retries, dependencies, and complex movement logic across compute resources (EC2/EMR).

### 3. Workflow Complexity
- **AWS Data Exchange** is simple: You subscribe, and data appears in S3.
- **AWS Data Pipeline** is complex: You define "Data Nodes" (where data is) and "Activities" (what to do with it) and "Schedules" (when to do it).

---

## When to Choose What?

| Scenario | Recommended Service |
| :--- | :--- |
| Need historical stock market data from a vendor. | **AWS Data Exchange** |
| Move data from RDS to Redshift every night at 2:00 AM. | **AWS Data Pipeline** (or AWS Glue) |
| Subscribe to a clinical trial dataset for research. | **AWS Data Exchange** |
| Run an EMR job as soon as a file arrives in S3. | **AWS Data Pipeline** (or Step Functions) |

## Exam Tips
- If the question mentions **third-party**, **external**, or **marketplace**, look for **Data Exchange**.
- If the question mentions **scheduling**, **workflow**, or **orchestrating ETL**, look for **Data Pipeline** (though modern questions may favor Glue or Step Functions).
