# AWS Cost Explorer

**AWS Cost Explorer** is a tool that enables you to visualize, understand, and manage your AWS costs and usage over time.

## Key Features

### Cost Visualization
- **Historical Data**: View up to 12 months of historical cost data.
- **Forecast**: Predict costs for the next 12 months based on historical usage.
- **Granularity**: View data at monthly, daily, or hourly level.
- **Group By**: Slice costs by service, linked account, tag, region, and more.

### Cost and Usage Reports
- **Filters**: Filter by service, region, availability zone, instance type, tag, etc.
- **Custom Reports**: Save and share custom cost reports.
- **Rightsizing Recommendations**: Get EC2 rightsizing recommendations to reduce costs.

### Reserved Instance & Savings Plans
- **RI Utilization and Coverage**: Track how well you're using your Reserved Instances.
- **Savings Plans Utilization**: Monitor your Savings Plans usage.
- **RI Purchase Recommendations**: Get recommendations for RI purchases based on usage.

## Related Services

| Service | Purpose |
| :--- | :--- |
| **Cost Explorer** | Visualize and analyze costs. |
| **AWS Budgets** | Set alerts when costs or usage exceed thresholds. |
| **Cost and Usage Report** | Detailed raw data export (CSV to S3) for custom analysis. |
| **Compute Optimizer** | Rightsizing recommendations based on utilization metrics. |

## Exam Tips
- **Cost Explorer** = *Visualize* and *forecast* costs.
- **AWS Budgets** = *Alert* when exceeding a budget.
- **Cost and Usage Report** = *Raw data export* to S3 (for Athena/QuickSight analysis).
- Use Cost Explorer's **Rightsizing Recommendations** to identify underutilized EC2 instances.
- Cost Explorer data is available after ~24 hours of account activity.
