# AWS Storage Gateway

**AWS Storage Gateway** is a hybrid cloud storage service that provides on-premises access to virtually unlimited cloud storage.

## Gateway Types

### S3 File Gateway
- **Protocol**: NFS (v3, v4.1) and SMB (v2, v3).
- **Use Case**: Store files as objects in S3 with low-latency local caching.
- **Storage**: Maps files 1:1 to S3 objects. Supports versioning and lifecycle policies.
- **Authentication**: Integrates with **Active Directory (AD)** for SMB access control.
- **Metadata**: Preserves POSIX metadata (permissions, timestamps) in S3 object metadata.
- **Best For**: Data migration to S3, data lakes, and on-premises applications needing S3 access via standard file protocols.

### FSx File Gateway
- **Protocol**: SMB (v2, v3).
- **Use Case**: Low-latency, cached access to **Amazon FSx for Windows File Server**.
- **Storage**: Data is managed in a remote FSx for Windows cluster.
- **Integration**: Requires joining an **Active Directory** domain (on-premises or AWS Managed).
- **Best For**: Optimizing access to Windows file shares from remote offices or branches.

### Volume Gateway
- **Protocol**: iSCSI
- **Use Case**: Block storage volumes backed by S3.
- **Modes**:
    - **Cached Volumes**: Primary data in S3, frequently accessed data cached locally.
    - **Stored Volumes**: Primary data stored locally, asynchronously backed up to S3 as EBS snapshots.
- **Best For**: Backup, disaster recovery, migration of block storage.

### Tape Gateway
- **Protocol**: iSCSI VTL (Virtual Tape Library)
- **Use Case**: Replace physical tape infrastructure with cloud storage.
- **Storage**: Virtual tapes stored in S3, archived to S3 Glacier or Glacier Deep Archive.
- **Best For**: Backup applications (Veeam, Veritas, etc.) using tape.

## Key Features
- **On-Premises Deployment**: Runs as a VM (VMware, Hyper-V, KVM) or hardware appliance.
- **Local Caching**: Low-latency access to frequently used data.
- **Bandwidth Management**: Throttle upload bandwidth.
- **Encryption**: Data encrypted in transit (SSL) and at rest (S3 SSE).

## Exam Tips
- **S3 File Gateway** = NFS/SMB → S3 (files as objects).
- **FSx File Gateway** = SMB → FSx for Windows (Windows file shares).
- **Volume Gateway (Cached)** = iSCSI, data in S3, cache locally.
- **Volume Gateway (Stored)** = iSCSI, data locally, backup to S3.
- **Tape Gateway** = Virtual tapes → S3 → Glacier (for backup software).
- For "hybrid cloud storage" or "on-premises access to cloud", think **Storage Gateway**.
