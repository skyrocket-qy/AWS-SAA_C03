# Data Transfer and Migration Service Comparison

AWS offers various services to move data to the cloud or between diverse environments. Choosing the right one depends on factors like data volume, available bandwidth, frequency (one-time vs. continuous), and protocol requirements.

## 1. Network Connectivity (Online - Dedicated/VPN)

Connect your on-premises network to AWS.

| Feature | AWS Site-to-Site VPN | AWS Direct Connect (DX) |
| :--- | :--- | :--- |
| **Connection Type** | Encrypted tunnel over the **public internet**. | Dedicated private fiber connection (bypass internet). |
| **Setup Time** | Fast (Minutes/Hours). | Slow (Weeks/Months) to provision physical circuit. |
| **Throughput** | Up to 1.25 Gbps per tunnel (aggregatable). | 1 Gbps, 10 Gbps, or 100 Gbps dedicated ports. |
| **Reliability** | Variable (internet-dependent). | Consistent latency and high reliability. |
| **Security** | IPsec Encryption in transit. | Private, but not encrypted by default (use MACsec or VPN over DX for encryption). |
| **Cost** | Low (hourly connection fee + data transfer). | High (port hours + data transfer). |

## 2. Bulk Data Migration (Online vs. Offline)

Move large datasets to S3, EFS, or FSx.

| Service | Type | Ideal Use Case | Protocols | Key Features |
| :--- | :--- | :--- | :--- | :--- |
| **AWS Snow Family** | **Offline** | **Petabytes/Exabytes** of data. Limited/no internet connectivity. Secure physical transport. | NFS (Snowball Edge) | Rugged devices, edge computing allowed (Snowball Edge), local processing. |
| **AWS DataSync** | **Online** | **Active data**, incremental transfers, or one-time migration over network (VPN/DX/Internet). | NFS, SMB, Object, HDFS | Automated, accelerated protocol, bandwidth throttling, schedule/task based. |
| **AWS Transfer Family** | **Online** | Replacing existing on-prem **SFTP** servers without changing client apps. | SFTP, FTPS, FTP | Fully managed serverless endpoint backed by S3 or EFS. |
| **AWS Storage Gateway** | **Hybrid** | On-prem access to cloud storage (caching, backups, tape replacement). | NFS, SMB, iSCSI, VTL | Low-latency local access to hot data (File/Volume Gateway), Tape backup (Tape Gateway). |
| **S3 Transfer Acceleration** | **Online** | Faster **uploads to S3** from globally dispersed clients over the public internet. | HTTPS | Uses AWS Edge Locations to route traffic via AWS global backbone network. |

## Quick Decision Guide

*   **No Internet / Too Slow?** -> **Snow Family**.
*   **Need standard NFS/SMB migration?** -> **DataSync**.
*   **Need SFTP server?** -> **Transfer Family**.
*   **Need low-latency local access?** -> **Storage Gateway**.
*   **Need dedicated private network?** -> **Direct Connect**.
