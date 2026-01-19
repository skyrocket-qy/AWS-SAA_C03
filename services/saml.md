# SAML 2.0 (Security Assertion Markup Language)

**SAML 2.0** is an XML-based open standard for exchanging authentication and authorization data between parties, in particular, between an **Identity Provider (IdP)** and a **Service Provider (SP)**.

## SAML Federation with AWS

SAML 2.0 is the standard for implementing **Single Sign-On (SSO)** between an enterprise identity store and AWS.

### The Workflow

1.  **Authenticate**: The user navigates to the enterprise portal and authenticates against the corporate IdP (e.g., ADFS, Okta, OneLogin).
2.  **Assertion**: The IdP generates a SAML Assertion (an XML document) containing the user's identity and attributes.
3.  **Redirect**: The browser is redirected to the AWS SAML endpoint (`https://signin.aws.amazon.com/saml`).
4.  **STS Exchange**: AWS verifies the assertion and calls **STS** (`AssumeRoleWithSAML`) to obtain temporary security credentials.
5.  **Access**: The user is signed into the AWS Console or granted API access.

### Configuration Steps
- **IAM Identity Provider**: You must download the **SAML Metadata Document** from your IdP and upload it to AWS IAM to create a "SAML Identity Provider."
- **IAM Role**: Create a role where the **Trust Policy** allows the SAML Identity Provider as the principal (`Principal: { Federated: "arn:aws:iam::..." }`).
- **SAML Attributes**: The IdP must be configured to send specific attributes (claims), notably the `Role` and `RoleSessionName`.

---

## SAML vs. Web Identity Federation

| Feature | SAML 2.0 | Web Identity Federation |
| :--- | :--- | :--- |
| **Typical IdP** | Enterprise (ADFS, Okta) | Social (Google, Facebook, Amazon) |
| **STS Call** | `AssumeRoleWithSAML` | `AssumeRoleWithWebIdentity` |
| **AWS Service**| IAM Identity Providers | **Amazon Cognito** (Recommended) |

---

## Exam Tips

- **SSO**: If the question asks for "Single Sign-On" for "Existing Corporate Identities" using a "Standard Protocol," the answer is **SAML 2.0**.
- **AssumeRoleWithSAML**: This is the specific STS API call used in SAML federation.
- **Trust Relationship**: The Role used for SAML federation must trust the SAML IdP created in IAM.
- **Automation**: Use SAML to avoid the overhead of managing individual IAM users for every employee.
