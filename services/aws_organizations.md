# AWS Organizations & Service Control Policies (SCPs)

**AWS Organizations** is a service for centrally managing and governing multiple AWS accounts. **Service Control Policies (SCPs)** are a key feature for access control.

## AWS Organizations

### Key Concepts
- **Organization**: The root container for all your AWS accounts.
- **Organizational Units (OUs)**: Groups of accounts within an organization. You can nest OUs within other OUs.
- **Management Account**: The account that creates the organization (formerly called "master account"). Has full control. SCPs do NOT apply to the management account.
- **Member Accounts**: All other accounts in the organization.

### Features
- **Consolidated Billing**: Single payment method for all accounts. Aggregate usage for volume discounts.
- **Service Control Policies (SCPs)**: Apply permission guardrails to accounts/OUs.
- **Tag Policies**: Standardize tags across resources.
- **Backup Policies**: Centrally manage AWS Backup plans.

---

## Service Control Policies (SCPs)

### What are SCPs?
- JSON policies that specify the **maximum permissions** for member accounts or OUs.
- SCPs do **NOT** grant permissions on their own—they only **restrict** what IAM policies can allow.
- Think of SCPs as a "permission boundary" for an entire account.

### How SCPs Work
1. By default, an SCP named `FullAWSAccess` is attached (allows everything).
2. You can attach "deny" SCPs to restrict specific actions.
3. Even if an IAM policy allows an action, if an SCP denies it, the action is **denied**.
4. SCPs apply to all users and roles in the account, **including the root user**.

### SCP Strategies
- **Deny List (Default)**: Start with `FullAWSAccess`, then attach SCPs that deny specific actions (e.g., deny leaving the organization).
- **Allow List**: Remove `FullAWSAccess`, then attach SCPs that only allow specific actions.

### Common SCP Use Cases
- Prevent member accounts from leaving the organization.
- Restrict access to specific AWS Regions.
- Prevent disabling of CloudTrail or GuardDuty.
- Enforce tagging compliance.

---

## Exam Tips
- **SCPs do NOT apply to the Management Account**.
- SCPs affect **all users and roles**, including **root**.
- SCPs are about **restricting permissions**, not granting them.
- For "restrict actions across all accounts in an OU", think **SCP**.
- For "easiest way to set up multi-account governance", think **Control Tower** (uses Organizations + SCPs).
