# AWS Application Migration Service (AWS MGN)

The primary service for lift-and-shift migrations (rehosting) to AWS. It simplifies and automates the process of migrating applications from physical, virtual, or cloud servers to AWS.

### Key Exam Points
- **Migration Strategy**: Specifically designed for **Rehost (Lift-and-Shift)**.
- **Continuous Replication**: Performs **block-level, asynchronous replication** of the source disks into a staging area in your AWS account.
- **Minimal Downtime**: Applications remain active during replication; downtime only occurs during the final cutover.
- **Broad Support**: Works with physical servers, VMware vSphere, Microsoft Hyper-V, and other cloud providers (GCP, Azure).
- **Staging Area**: Uses low-cost EC2 instances and EBS volumes to minimize costs during the replication phase.
- **Post-Launch Actions**: Can automate optimization of migrated instances (e.g., installing AWS systems manager agent, converting licenses).
- **Replacement**: It is the successor to **CloudEndure Migration**.
