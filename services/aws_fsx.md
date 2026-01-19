# Amazon FSx

**Amazon FSx** provides fully managed third-party file systems optimized for specific workloads.

## FSx for Lustre

**FSx for Lustre** is a high-performance file system for compute-intensive workloads like machine learning, HPC, video processing, and financial modeling.

### Key Features
- **High Throughput**: Hundreds of GB/s throughput, millions of IOPS, sub-millisecond latencies.
- **S3 Integration**: Can be linked to an S3 bucket to automatically load data from S3 and write results back.
- **Deployment Options**:
    - **Scratch**: Temporary storage, no replication. Best for short-term processing.
    - **Persistent**: Replicated within a single AZ. Best for longer-term storage and sensitive data.
- **POSIX-compliant**: Works with Linux-based AMIs.

### Use Cases
- Machine Learning training datasets.
- High Performance Computing (HPC).
- Video rendering.
- Electronic Design Automation (EDA).

---

## FSx for Windows File Server
- Fully managed Windows-native file system.
- Supports **SMB protocol**, Windows NTFS, and Active Directory integration.
- Use Case: Windows-based applications, SharePoint, SQL Server.

## FSx for NetApp ONTAP
- Fully managed NetApp ONTAP file system.
- Supports NFS, SMB, and iSCSI(block storage) protocols.
- Use Case: Migrating on-premises NetApp workloads to AWS.

## FSx for OpenZFS
- Fully managed ZFS file system.
- Use Case: Migrating ZFS workloads or applications requiring ZFS features (snapshots, compression).

---

## Exam Tips
- **FSx for Lustre** = **HPC, ML, high-throughput** workloads + **S3 integration**.
- **FSx for Windows** = **SMB**, Active Directory, Windows apps.
- **FSx for NetApp ONTAP** = Multi-protocol (NFS + SMB + iSCSI), hybrid cloud.
- **Scratch vs Persistent**: Scratch = no replication (temporary), Persistent = replication (durable).
- Lustre is **Linux only**; Windows File Server is for **Windows**.
