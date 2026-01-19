# LDAP (Lightweight Directory Access Protocol)

**LDAP** is a mature, open, vendor-neutral, industry-standard application protocol for accessing and maintaining distributed directory information services over an IP network.

## LDAP and AWS

In the context of AWS and the SAA-C03 exam, LDAP is typically discussed as a **Corporate Identity Store** that needs to be integrated with AWS for authentication and authorization.

### Integration Patterns

1.  **Custom Identity Broker (Federation Proxy)**:
    - Used when the LDAP server does **not** support SAML 2.0.
    - Your custom application (broker) authenticates the user against LDAP.
    - The broker then calls **AWS STS** (`AssumeRole` or `GetFederationToken`) to obtain temporary credentials.
    - This is the most common "harder" integration scenario for LDAP.

2.  **AWS Managed Microsoft AD (via AD Connector)**:
    - If you are using Active Directory (which uses LDAP under the hood), you can use the **AD Connector** to proxy authentication requests to your on-premises LDAP/AD server.

3.  **Amazon Cognito User Pools**:
    - While Cognito doesn't support LDAP directly as a social provider, you can use a Lambda function ("Pre Sign-up" or "Custom Authentication") to validate credentials against an LDAP server.

---

## LDAP vs. SAML 2.0

| Feature | LDAP | SAML 2.0 |
| :--- | :--- | :--- |
| **Type** | Directory Access Protocol | XML-based Data Format (Federation) |
| **Primary Use** | Storing/Querying user data | Single Sign-On (SSO) |
| **Port** | 389 (LDAP) / 636 (LDAPS) | 443 (HTTPS) |
| **AWS Ease of Use**| Requires custom Broker/Proxy | Native Support (IAM Identity Providers) |

---

## Exam Tips

- **"Custom Identity Store"**: If a question mentions a "custom identity store" or an "LDAP server without SAML support," look for the **Identity Broker** or **Federation Proxy** solution.
- **`GetFederationToken`**: This STS API call is often associated with custom identity brokers authenticating against LDAP or other custom databases.
- **LDAPS**: Always use **LDAPS (LDAP over SSL)** when discussing secure communication between your cloud VPC and an on-premises LDAP server.
- **Direct Connect / VPN**: Integrating with an on-premises LDAP requires a secure, private connection (Site-to-Site VPN or Direct Connect).
