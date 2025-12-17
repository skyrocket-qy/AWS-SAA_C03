# Amazon Simple Storage Service (S3)

Amazon S3 is an object storage service offering industry-leading scalability, data availability, security, and performance.

## Key Concepts

*   **Buckets**: A container for objects. Must have a globally unique name across all AWS accounts.
*   **Objects**: The fundamental entities stored in Amazon S3 (files). Max size is 5 TB.
*   **Keys**: Each object is identified by a unique key (name) with region, bucket, and version ID.
*   **Versioning**: Keeps multiple variants of an object in the same bucket. Helps recover from accidental deletion or overwrite.
*   **Strong Consistency**: Read-after-write consistency for PUTs of new objects and internal updates.

## Storage Classes Comparison

| Storage Class | Designed For | Availability Zones | Min Storage Duration | Retrieval Fee | Access Latency |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **S3 Standard** | General purpose, frequently accessed data (Hot). | >= 3 | None | None | Milliseconds |
| **S3 Intelligent-Tiering** | Data with unknown or changing access patterns. Moves data between tiers automatically. | >= 3 | None | None | Milliseconds |
| **S3 Standard-IA** | Infrequently accessed data that needs rapid access (Warm). | >= 3 | 30 days | Yes (per GB) | Milliseconds |
| **S3 One Zone-IA** | Non-critical, reproducible data. Lower cost (20% less than Standard-IA). | **1 AZ** | 30 days | Yes (per GB) | Milliseconds |
| **S3 Glacier Instant Retrieval** | Archive data requiring immediate access. | >= 3 | 90 days | Yes (per GB) | Milliseconds |
| **S3 Glacier Flexible Retrieval** | Archive data accessed 1-2 times per year. | >= 3 | 90 days | Yes (per GB) | Minutes to Hours |
| **S3 Glacier Deep Archive** | Long-term data retention (compliance/legal). Lowest cost. | >= 3 | 180 days | Yes (per GB) | 12-48 Hours |

## Security

*   **Encryption**:
    *   **SSE-S3**: Keys managed by AWS.
    *   **SSE-KMS**: Keys managed by KMS (more control + audit trail).
    *   **SSE-C**: Keys managed by customer (you provide keys).
*   **Access Control**:
    *   **Bucket Policies**: JSON-based policies attached to buckets (Resource-based).
    *   **IAM Policies**: Attached to users/roles (Identity-based).

## Features

*   **Lifecycle Rules**: Automate moving objects to cheaper storage classes or deleting them after a set period.
*   **Replication**:
    *   **CRR**: Cross-Region Replication (Disaster Recovery, Compliance).
    *   **SRR**: Same-Region Replication (Log aggregation, Test env sync).
*   **MFA Delete**: Requires Multi-Factor Authentication to permanently delete an object version or suspend versioning.
