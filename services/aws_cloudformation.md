# AWS CloudFormation

AWS CloudFormation is a service that gives you an easy way to model a collection of related AWS and third-party resources, provision them quickly and consistently, and manage them throughout their lifecycles, by treating infrastructure as code.

## Key Concepts

*   **Infrastructure as Code (IaC)**: Managing and provisioning computer data centers through machine-readable definition files, rather than physical hardware configuration or interactive configuration tools.
*   **Template**: A JSON or YAML formatted text file that acts as a blueprint for building your AWS resources.
*   **Stack**: The set of AWS resources that are created and managed as a single unit when you instantiate a template.
*   **ChangeSet**: A preview of the changes that CloudFormation will make to your stack before you apply them. (Like a "dry run" or `terraform plan`).

## Key Features

### 1. Drift Detection
*   **Concept**: Checks if the actual configuration of a stack's resources differs from the configuration expected by the template.
*   **Use Case**: Identify and correct unmanaged changes made directly via the Console or CLI (Configuration Drift).

### 2. StackSets
*   **Concept**: Create, update, or delete stacks across **multiple accounts** and **AWS Regions** with a single operation.
*   **Use Case**: Deploying a standard IAM Role or VPC configuration to all accounts in an AWS Organization.

### 3. Nested Stacks
*   **Concept**: Stacks created as part of other stacks using the `AWS::CloudFormation::Stack` resource.
*   **Use Case**: Reusing common templates (e.g., a standard Load Balancer configuration) within larger infrastructure templates.

### 4. Cross-Stack Reference
*   **Mechanism**: Use `Fn::Export` in one stack to export a value, and `Fn::ImportValue` in another stack to import it.
*   **Constraint**: You cannot delete the source stack while another stack is importing its exported values.

## Important Intrinsic Functions

*   `Fn::Ref` (or `!Ref`): Returns the value of the specified parameter or resource.
*   `Fn::GetAtt` (or `!GetAtt`): Returns the value of an attribute of a resource (e.g., getting the PublicIP of an EC2 instance).
*   `Fn::ImportValue` (or `!ImportValue`): Returns the value of an output exported by another stack.
*   `Fn::Sub` (or `!Sub`): Substitutes variables in a string.
