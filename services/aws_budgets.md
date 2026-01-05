# AWS Budgets

**AWS Budgets** gives you the ability to set custom budgets to track your cost and usage from the simplest to the most complex use cases.

## Key Features

- **Custom Budgets**: Set budgets based on cost, usage, reservation utilization, or reservation coverage.
- **Alerts**: Receive alerts via email or Amazon SNS (Simple Notification Service) when your actual or forecasted cost/usage exceeds your budget threshold.
- **Actions**: Configure AWS Budgets Actions to automatically execute responses (e.g., stop EC2 instances, apply IAM policies) when a threshold is breached.
- **Forecasting**: View forecasted costs based on your usage patterns.
- **Reporting**: Receive periodic budget reports via email.

## Budget Types

1.  **Cost Budgets**: Plan how much you want to spend on a service.
2.  **Usage Budgets**: Plan how much you want to use one or more services (e.g., number of EC2 instance hours).
3.  **Reservation Utilization Budgets**: Define a utilization threshold and receive alerts when your RI utilization drops below that threshold.
4.  **Reservation Coverage Budgets**: Define a coverage threshold and receive alerts when the number of instance hours covered by RIs drops below that threshold.
5.  **Savings Plans Utilization/Coverage Budgets**: Similar to RI budgets but for Savings Plans.

## Exam Tips

- **Proactive Alerts**: AWS Budgets is the primary tool for **setting alerts** when costs exceed a defined limit.
- **Forecast vs. Actual**: Alerts can be triggered on **actual** spend or **forecasted** spend.
- **Actions**: Remember that Budgets can trigger **actions** (via Chatbot to Slack, or Systems Manager to stop instances), not just send emails.
- Difference from **Cost Explorer**: Cost Explorer is for **analyzing** historical data and trends; Budgets is for **planning** and **alerting**.

## Integration
- **Amazon SNS**: For sending notifications.
- **AWS Chatbot**: Send alerts to Slack or Amazon Chime.
- **Service Control Policies (SCPs)** / **IAM**: Can be used as automated actions to restrict resource creation when budget is exceeded.
