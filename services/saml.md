# SAML 2.0 (Security Assertion Markup Language)

**SAML 2.0** is the XML standard for exchanging authentication/authorization data between an Identity Provider (IdP) and a Service Provider (SP).

### Key Exam Points
- **Workflow**: Identity Provider (Okta, ADFS) -> SAML Assertion -> browser redirect -> AWS STS (`AssumeRoleWithSAML`) -> Temporary Credentials.
- **IAM Setup**: Upload the **SAML Metadata document** from the IdP to create an IAM Identity Provider.
- **Role Trust**: The IAM Role's trust policy must allow the SAML IdP as the Principal.
- **Single Sign-On (SSO)**: The primary answer for "SSO with existing corporate identities using standard protocols."
- **vs. Web Identity**: SAML is for enterprise; **Cognito** is for social/mobile web identities.
