# AWS Directory Service

**AWS Directory Service** provides options for using Microsoft Active Directory (AD) or LDAP in AWS.

### Key Exam Points
- **Managed Microsoft AD**: Full AD on Windows; supports **Trust Relationships** (two-way trust with on-premises AD).
- **AD Connector**: A **proxy** to on-premises AD; no data cached in AWS; no trust relationship needed.
- **Simple AD**: Low-cost **Linux-based** AD; basic features only; no trust support.
- **Scenarios**:
    - Full AD & Trusts -> **Managed Microsoft AD**.
    - Link to on-premises AD (no sync) -> **AD Connector**.
    - Small, simple environment -> **Simple AD**.
