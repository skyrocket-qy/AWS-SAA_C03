# AWS Cost and Usage Report (CUR)

The **AWS Cost and Usage Report (CUR)** contains the most comprehensive set of cost and usage data available.

## Key Features
- **Granularity**: Provides data at an hourly, daily, or monthly level.
- **Detail**: Includes comprehensive details including resource IDs, tags, purchase options (e.g., Reserved Instances), and pricing categories.
- **Destination**: Delivers reports to an **Amazon S3** bucket that you define.
- **Integration**: Automatically updates the report once a day.

## Integration & Analysis
Since CUR produces raw CSV/Parquet files in S3, you typically use other services to analyze the data:
- **Amazon Athena**: To run SQL queries directly against the CUR properties in S3.
- **Amazon Redshift**: To load the data into a data warehouse for high-performance analytics.
- **Amazon QuickSight**: To visualize the data in dashboards.

## Exam Tips
- **Most Detailed**: If a question asks for the **most granular** or **most detailed** information about costs (e.g., down to the hour or specific resource ID), the answer is **Cost and Usage Report**.
- **Storage**: Always remember it is delivered to **S3**.
- **Tags**: It supports cost allocation tags, allowing you to break down costs by project, environment, or team.
- **Retention**: Offers historical data retention depending on your S3 lifecycle policies.

## Comparison
| Service | Use Case |
| :--- | :--- |
| **Cost Explorer** | Visualizing trends, graphs, and high-level cost management in the console. |
| **AWS Budgets** | Alerting when costs exceed a threshold. |
| **Cost and Usage Report** | Deep-dive analysis, raw data access, and integration with external BI tools. |
