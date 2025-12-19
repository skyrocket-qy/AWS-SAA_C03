# AWS Resource Groups & Tag Editor

**AWS Resource Groups** and **Tag Editor** are management tools that help you organize and manage your AWS resources.

## AWS Resource Groups

**Resource Groups** let you organize AWS resources into groups using tags or CloudFormation stacks.

### Key Features
- **Group Resources**: Create a custom console view for resources that share common tags (e.g., `Project: MyProject`, `Environment: Production`).
- **Automation**: Perform bulk actions on members of a group (e.g., install updates via Systems Manager).
- **Monitoring**: View aggregated metrics and alarms (CloudWatch) for the group.

### Types of Groups
- **Tag-based**: Resources with specific tags.
- **CloudFormation-stack-based**: Resources created by a specific stack.

## Tag Editor

**Tag Editor** is a tool to manage tags across multiple AWS resources and regions.

### Key Features
- **Find Resources**: Search for resources across regions and resource types.
- **Bulk Tagging**: Add, edit, or delete tags for multiple resources at once.
- **Identify Untagged Resources**: Easily find resources that are missing required tags.

## Exam Tips
- Use **Resource Groups** to "group" resources for application-centric management or automation (Systems Manager).
- Use **Tag Editor** to "find" resources (especially cross-region) or to "bulk tag" resources.
- If the question asks how to apply updates to all EC2 instances in a specific environment, think **Resource Groups** + **Systems Manager**.
