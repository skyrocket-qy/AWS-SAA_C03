# AWS Storage Gateway

**AWS Storage Gateway** is a hybrid cloud storage service providing on-premises access to cloud storage.

### Key Exam Points
- **S3 File Gateway**: NFS/SMB access to files stored as **objects in S3**; includes local caching.
- **FSx File Gateway**: SMB access to **FSx for Windows File Server** with local caching.
- **Volume Gateway**: iSCSI block storage.
    - **Cached**: Data in S3, frequent data cached locally.
    - **Stored**: Data locally, periodic EBS snapshots stored in S3.
- **Tape Gateway**: Replaces physical tapes with **virtual tapes** backed by S3/Glacier (VTL).
- **Deployment**: Virtual Appliance (VMware/Hyper-V) or hardware appliance on-premises.
- **Common Use Case**: Disaster recovery, data migration to S3, and cloud-backed local file shares.
