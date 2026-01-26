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
