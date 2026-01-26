# AWS IAM Identity Center (Single Sign-On)

**IAM Identity Center** is the recommended service for managing centralized SSO access to AWS accounts and SaaS apps.

### Key Exam Points
- **Multi-Account Access**: Users log into a single portal to access all authorized accounts/roles in an **AWS Organization**.
- **Permission Sets**: Templates for IAM roles that apply across managed accounts.
- **Identity Sources**: Supports internal directory, **Active Directory** (via AD Connector or Managed AD), or external SAML IdPs (Okta, Azure AD).
- **Use Case**: Centralized governance for dozens/hundreds of accounts; simpler than managing individual SAML federations.
- **ABAC**: Supports Attribute-Based Access Control using user attributes.
