# Federation Proxy (Identity Broker)

A **Federation Proxy** is an intermediary that authenticates users against a corporate ID store and requests temporary AWS credentials.

### Key Exam Points
- **Custom IdP**: Use when the corporate store (LDAP, DB) does **not** support SAML 2.0.
- **STS API Actions**:
    - `AssumeRole`: Basic role assumption.
    - `AssumeRoleWithSAML`: For SAML 2.0 IdPs (Okta, ADFS).
    - `AssumeRoleWithWebIdentity`: For social logins (via Cognito).
    - `GetFederationToken`: Often used by custom proxies to get scoped credentials.
- **Cognito**: Preferred for mobile/web apps with social or guest identities.
- **Temporary Credentials**: All methods return short-lived access keys and tokens.
