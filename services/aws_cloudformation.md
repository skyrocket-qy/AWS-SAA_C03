# AWS CloudFormation

**AWS CloudFormation** is an Infrastructure as Code (IaC) service that models and provisions AWS resources using templates (JSON/YAML).

### Key Exam Points
- **Stack**: A collection of resources managed as one unit.
- **ChangeSet**: A preview of proposed changes before execution (dry run).
- **Drift Detection**: Identifies if resources have changed outside of CloudFormation.
- **StackSets**: Deploy stacks across **multiple accounts and regions** simultaneously.
- **Nested Stacks**: Reusable templates referenced within other templates for modularity.
- **Cross-Stack Reference**: Use `Export` and `ImportValue` to share outputs between stacks.
