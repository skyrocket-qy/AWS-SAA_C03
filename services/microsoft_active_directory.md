# Microsoft Active Directory & AD FS

**Microsoft Active Directory (AD)** is the standard directory service for Windows-based networks, while **AD FS (Federation Services)** is the component that allows it to speak "SAML" to external services like AWS.

## Key Concepts

### Microsoft Active Directory (AD)
- **Role**: The centralized database of users, groups, and computers.
- **Authentication**: Uses **Kerberos** and **NTLM**.
- **Querying**: Uses **LDAP** (Lightweight Directory Access Protocol).

### AD FS (Active Directory Federation Services)
- **Role**: Acts as the **Identity Provider (IdP)** in a federation setup.
- **Function**: Authenticates users against the internal AD and generates a **SAML 2.0 Assertion** (token) for AWS.
- **Access**: Usually exposed to the internet (via a WAP - Web Application Proxy) so employees can log into AWS from anywhere.

---

## AWS Integration Patterns

### 1. SAML 2.0 Federation (Most Common)
- **Workflow**: User -> AD FS -> SAML Token -> AWS STS (`AssumeRoleWithSAML`) -> AWS Console.
- **Prerequisite**: A Trust Relationship must be established between AD FS and AWS IAM.

### 2. AWS Managed Microsoft AD
- **What it is**: A managed AD service running in the AWS Cloud.
- **Trust Relationship**: You can establish a **One-way or Two-way Forest Trust** between your on-premises AD and your AWS Managed Microsoft AD.

### 3. AD Connector
- **What it is**: A directory gateway (proxy) that redirects directory requests to your on-premises Microsoft Active Directory.
- **Use Case**: Best for using existing AD credentials with AWS services like WorkSpaces, QuickSight, or Client VPN without caching credentials in the cloud.

---

## AD Connector vs. AWS Managed Microsoft AD

| Feature | AD Connector | AWS Managed Microsoft AD |
| :--- | :--- | :--- |
| **Identity Storage** | On-premises only | In AWS (with optional trust) |
| **Trust Support** | No | **Yes (Forest Trusts)** |
| **SSO Support** | Via IAM Identity Center | Via IAM Identity Center |
| **Management** | AWS manages the proxy | AWS manages the Domain Controllers |

---

## Exam Tips

- **AD FS = SAML**: If a question mentions AD FS, the federation protocol is always **SAML 2.0**.
- **Managed AD Trusts**: If you need to log into AWS using your on-premises AD credentials and want to manage resources natively in an AD environment in the cloud, use **AWS Managed Microsoft AD with a Trust Relationship**.
- **AD Connector vs. Federation**: Use **AD Connector** for AWS service integration (WorkSpaces, etc.). Use **Federation (SAML)** for AWS Console/CLI access for thousands of users.
- **High Availability**: Always deploy AD Connectors or Managed AD in at least **two Availability Zones**.
