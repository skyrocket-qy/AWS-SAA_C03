# Federation Proxy (Identity Broker)

A **Federation Proxy** (also known as an **Identity Broker**) is an intermediary component that authenticates users against a corporate identity store (e.g., LDAP, Active Directory) and then requests temporary AWS credentials on their behalf.

## Overview

When your organization has existing identities in a corporate directory, you don't want to recreate all users as IAM users in AWS. Instead, you use federation to grant access.

### The Problem
- Users exist in a corporate Identity Provider (IdP) like Active Directory.
- They need access to AWS resources (Console or API).
- You don't want to create duplicate IAM users.

### The Solution: Federation Proxy
A custom application (the "Identity Broker" or "Federation Proxy") sits between the user and AWS:
1.  **Authenticate**: User authenticates to the corporate IdP.
2.  **Assume Role**: The broker calls AWS STS (`AssumeRole` or `GetFederationToken`) to get temporary credentials.
3.  **Access AWS**: The broker returns temporary credentials (or a sign-in URL) to the user.

---

## Key AWS STS API Actions

| API Call | Use Case |
| :--- | :--- |
| `AssumeRole` | When an IAM Role is predefined; common for cross-account access or service-to-service. |
| `AssumeRoleWithSAML` | When using SAML 2.0 IdP (e.g., ADFS, Okta, Ping Identity). |
| `AssumeRoleWithWebIdentity` | When using Web Identity Providers (Google, Facebook, Amazon Cognito). |
| `GetFederationToken` | When the broker itself has IAM user credentials and requests temporary tokens for federated users. Returns credentials scoped by an inline policy. |

---

## Federation Proxy vs. SAML 2.0

| Feature | Custom Federation Proxy | SAML 2.0 Federation |
| :--- | :--- | :--- |
| **Implementation** | Custom code required | Standardized; less code |
| **IdP Requirement** | Any (LDAP, custom DB) | Must support SAML 2.0 |
| **STS Call** | `GetFederationToken` or `AssumeRole` | `AssumeRoleWithSAML` |
| **Best For** | Legacy IdPs without SAML support | Modern enterprise IdPs |

---

## Exam Tips

- **Custom Identity Store**: If the scenario describes a **custom identity store** (non-SAML, non-OIDC), the answer likely involves a **Federation Proxy** calling `GetFederationToken` or `AssumeRole`.
- **SAML 2.0**: If the IdP supports SAML (like ADFS or Okta), prefer direct SAML federation (`AssumeRoleWithSAML`) over a custom broker.
- **Web Identity**: For mobile/web apps authenticating via social logins (Google, Facebook), use **Amazon Cognito** with `AssumeRoleWithWebIdentity`.
- **Temporary Credentials**: All federation methods return **temporary security credentials** (Access Key, Secret Key, Session Token) with a defined expiration.
