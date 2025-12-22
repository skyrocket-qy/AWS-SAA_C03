# AWS Directory Service (Active Directory)

**AWS Directory Service** provides multiple directory options for customers who want to use Microsoft Active Directory (AD) or Lightweight Directory Access Protocol (LDAP) in AWS.

## Directory Types

### AWS Managed Microsoft AD
- **Full Microsoft AD** running on Windows Server, managed by AWS.
- Supports AD-aware applications, Group Policy, trusts with on-premises AD.
- **Two-way trust**: Users can authenticate from either on-premises or AWS.
- Deployed across two AZs for high availability.
- Use Case: Enterprises needing a full AD experience for workloads like SharePoint, .NET apps, SQL Server.

### AD Connector
- **Proxy** to redirect directory requests to your on-premises Microsoft AD.
- No caching, no data stored in AWS.
- Users authenticate against your on-premises AD.
- Use Case: Use on-premises AD for AWS services (e.g., WorkSpaces, AWS Management Console SSO) without syncing.

### Simple AD
- Low-cost, **Linux Samba-based** directory compatible with basic AD features.
- Does NOT support trusts or advanced AD features (Group Policy, MFA).
- Use Case: Small environments needing basic user directory without full AD.

## Integration with AWS Services
- **Amazon WorkSpaces**: Virtual desktops authenticated via AD.
- **Amazon RDS for SQL Server**: Windows Authentication.
- **AWS SSO (IAM Identity Center)**: Centralized access using AD credentials.
- **Amazon EC2**: Join Windows instances to domain.
- **FSx for Windows File Server**: SMB file shares.

## Exam Tips
- **Managed Microsoft AD** = Full AD with trusts (two-way trust with on-premises).
- **AD Connector** = Proxy to on-premises AD (no data in AWS, no caching).
- **Simple AD** = Basic, low-cost, Linux-based (no trusts, no advanced features).
- If the question mentions "trust relationship" or "replicate users", choose **Managed Microsoft AD**.
- If the question says "use existing on-premises AD without storing data in AWS", choose **AD Connector**.
