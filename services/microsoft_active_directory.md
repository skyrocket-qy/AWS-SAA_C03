# Microsoft Active Directory & AD FS

**Active Directory (AD)** is a central user database, while **AD FS** provides SAML-based federation for SSO.

### Key Exam Points
- **SAML Federation**: User -> AD FS -> SAML Token -> STS (`AssumeRoleWithSAML`) -> AWS Console.
- **AWS Managed Microsoft AD**: A managed AD in the cloud; supports **Forest Trusts** (Sync/Share with on-premises).
- **AD Connector**: A **proxy** (no caching) for using on-premises AD with AWS services (WorkSpaces, QuickSight).
- **Tip**: Use **AD FS** for general AWS access; use **AD Connector** for specific AWS application integration.
- **Availability**: Always deploy in at least **two AZs**.
