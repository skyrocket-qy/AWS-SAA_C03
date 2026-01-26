# LDAP (Lightweight Directory Access Protocol)

**LDAP** is a standard protocol for accessing distributed directory services (e.g., Active Directory).

### Key Exam Points
- **Identity Store**: Typically represents an on-premises corporate directory in SAA-C03 questions.
- **Integration**:
    - **Identity Broker**: Use a custom proxy calling **STS (`GetFederationToken` or `AssumeRole`)** if the LDAP store doesn't support SAML.
    - **AD Connector**: Use if the LDAP store is part of an Active Directory environment.
- **Security**: Use **LDAPS** (LDAP over SSL) for secure communication over VPN/Direct Connect.
- **vs. SAML**: SAML is for SSO (federation); LDAP is for querying/authenticating against the directory.
