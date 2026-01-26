# AWS Service Catalog

**AWS Service Catalog** allows organizations to create and manage a catalog of approved IT services for users to provision.

### Key Exam Points
- **Governance**: Ensures compliance by limiting users to **pre-approved, standardized** resources (products).
- **Structure**: Administrators organize products into **Portfolios** and share them with specific IAM users/groups.
- **Constraints**: Rules that limit how products are deployed (e.g., allowed instance types, required tags).
- **Use Case**: Self-service portal for developers to launch compliant infrastructure (via CloudFormation) without direct access to full AWS services.
- **vs. Marketplace**: Service Catalog is for internal, company-approved products; Marketplace is for 3rd-party software.
