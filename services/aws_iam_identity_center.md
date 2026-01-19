# AWS IAM Identity Center (Successor to AWS Single Sign-On)

**AWS IAM Identity Center** is the recommended service for managing single sign-on (SSO) access to AWS accounts and business applications. It provides a central place to manage users and their access to all AWS accounts in an **AWS Organization**.

## Key Features

- **Centralized Management**: Manage user identities and permissions across multiple AWS accounts from a single location.
- **Identity Store Options**:
    - **Identity Center Directory**: Create and manage users directly in IAM Identity Center.
    - **Active Directory (AD)**: Connect to self-managed AD (on-premises or on EC2) or AWS Managed Microsoft AD.
    - **External IdP**: Connect to external SAML 2.0 Identity Providers (e.g., Okta, Azure AD).
- **Multi-Account Access**: Users log into a single web portal and see all accounts and roles they are authorized to access.
- **SaaS Application Integration**: Pre-integrated support for many SaaS apps (e.g., Salesforce, Box, Microsoft 365).

## Permission Sets

In IAM Identity Center, you don't assign policies directly to users in each account. Instead, you use **Permission Sets**:
- A Permission Set is a template for an IAM role that IAM Identity Center creates in your managed accounts.
- You can include AWS managed policies or custom inline policies.
- **Assignment**: You assign a User (or Group) to an AWS Account with a specific Permission Set.

---

## IAM Identity Center vs. IAM Federation (SAML)

| Feature | IAM Identity Center | IAM SAML Federation |
| :--- | :--- | :--- |
| **Scope** | Cross-account (AWS Organizations) | Individual account focus |
| **Management** | Centralized in one AWS account | Managed per account |
| **User Experience**| Integrated AWS access portal | Custom IdP portal/URL |
| **Complexity** | Easier for multi-account setups | More configuration per account |

---

## Exam Tips

- **AWS Organizations**: IAM Identity Center works at the **Organization** level. It is the best choice for managing access to dozens or hundreds of accounts.
- **Centralized Login**: Whenever a scenario asks for a "single portal" or "centralized login" for an entire organization, think **IAM Identity Center**.
- **External AD**: You can connect your on-premises Active Directory to IAM Identity Center using **AD Connector** or **AWS Managed Microsoft AD**.
- **ABAC**: IAM Identity Center supports **Attribute-Based Access Control (ABAC)**, allowing you to use user attributes (like `CostCenter`) in your permission sets.
