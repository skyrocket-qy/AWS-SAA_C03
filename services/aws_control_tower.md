# AWS Control Tower

**AWS Control Tower** provides the easiest way to set up and govern a secure, multi-account AWS environment based on AWS best practices.

## Key Concepts

### Landing Zone
- **Definition**: A well-architected, multi-account baseline that follows best practices. It's the foundation set up by Control Tower.
- **Includes**: Pre-configured organizational units (OUs), accounts, AWS SSO, and guardrails.

### Guardrails
- **Definition**: High-level rules that provide governance for your overall AWS environment. Think of them as pre-packaged policies.
- **Types**:
    - **Preventive Guardrails**: Stop account configurations that can lead to policy violations. Implemented using **Service Control Policies (SCPs)**.
    - **Detective Guardrails**: Detect non-compliant resources. Implemented using **AWS Config Rules**.
- **Categories**: Mandatory, Strongly Recommended, Elective.

### Account Factory
- **Definition**: Automates provisioning of new AWS accounts based on configurable templates.
- Uses **AWS Service Catalog** behind the scenes.

## Key Features
- Automated setup of a multi-account environment.
- Built-in blueprints for security and compliance (using guardrails).
- Centralized logging (CloudTrail + Config logs to a dedicated Log Archive account).
- **Account Factory** for self-service account provisioning.
- Dashboard for visibility across all enrolled accounts.

## Exam Tips
- **Control Tower = Multi-account governance** (landing zone + guardrails).
- For "easiest way to set up a multi-account environment", think **Control Tower**.
- **Preventive = SCPs**, **Detective = Config Rules**.
- Control Tower uses **AWS Organizations** under the hood.
- Related services: AWS Organizations, AWS SSO (IAM Identity Center), AWS Config.
