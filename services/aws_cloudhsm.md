# AWS CloudHSM

**AWS CloudHSM** provides dedicated, single-tenant Hardware Security Modules for cryptographic key management.

### Key Exam Points
- **Compliance**: Meets **FIPS 140-2 Level 3** (KMS is generally Level 2).
- **Single-Tenancy**: Dedicated hardware; no sharing with other customers.
- **Control**: User has **exclusive** control of keys; AWS admins cannot access them.
- **Integration**: Runs inside your **VPC**; requires manual management of redundancy and backups.
- **When to choose**: Strict regulatory requirements (Level 3) or need for dedicated hardware.
