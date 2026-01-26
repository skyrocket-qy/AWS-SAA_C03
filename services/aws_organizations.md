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
