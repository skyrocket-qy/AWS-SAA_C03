# AWS Service Catalog

**AWS Service Catalog** allows organizations to create and manage catalogs of IT services that are approved for use on AWS. These IT services can include everything from virtual machine images, servers, software, and databases to complete multi-tier application architectures.

## Key Concepts
- **Portfolio**: A collection of products that can be shared with specific groups of users.
- **Product**: A CloudFormation template packaged for deployment (e.g., a compliant EC2 instance, a database stack).
- **Constraint**: Rules applied to products (e.g., restrict instance types, enforce tags, limit regions).
- **Provisioned Product**: An instance of a product that has been deployed by an end user.

## Key Features
- **Self-Service Portal**: End users can browse and launch approved products without needing deep AWS knowledge.
- **Governance**: Administrators define what resources users can provision and how.
- **Version Control**: Manage multiple versions of products and control which versions are available.
- **Access Control**: Use IAM to control who can create, manage, and consume products.
- **Cross-Account Sharing**: Share portfolios with other AWS accounts or AWS Organizations.

## Use Cases
- **Standardized Environments**: Ensure all deployed resources meet compliance and security standards.
- **Developer Self-Service**: Allow developers to quickly provision pre-approved resources.
- **Cost Control**: Limit which instance types or configurations are available.
- **Governance at Scale**: Enforce policies across multiple accounts using AWS Organizations.

## Exam Tips
- **Approved/Standardized Deployments**: If a question asks about allowing users to deploy **only pre-approved, compliant resources**, the answer is **Service Catalog**.
- **CloudFormation Based**: Products are essentially CloudFormation templates wrapped with governance.
- Differentiate from **AWS Marketplace** (third-party software) — Service Catalog is for internal, organization-defined products.
