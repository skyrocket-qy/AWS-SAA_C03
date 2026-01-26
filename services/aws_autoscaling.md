# Amazon EC2 Auto Scaling

**Amazon EC2 Auto Scaling** maintains application availability by automatically adding or removing EC2 instances based on demand.

### Key Exam Points
- **Capacity Settings**:
    - **Minimum Size**: Lower limit of instances.
    - **Maximum Size**: Upper limit of instances.
    - **Desired Capacity**: Target number of instances running now (ASG maintains this).
- **Health Checks**: Use **ELB Health Checks** (not just EC2) to replace instances if the application itself fails.
- **Launch Template**: Modern method (recommended); supports versioning and Spot offset.
- **Termination Policy**: Default strategy prioritizes balancing across AZs, then oldest launch template/configuration.
- **Scaling Policies**: (Target Tracking, Step Scaling, Simple Scaling, Predictive).
