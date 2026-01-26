# Amazon Simple Storage Service (S3)

**Amazon S3** is an object storage service providing industry-leading scalability and availability.

### Key Exam Points
- **Consistency**: Strong read-after-write consistency for all operations.
- **Storage Classes**:
    - **Standard**: Frequently accessed (Hot).
    - **Intelligent-Tiering**: Unknown/changing patterns (auto-moves data).
    - **Standard-IA / One Zone-IA**: Infrequently accessed (Warm); lower cost but has retrieval fees.
    - **Glacier (Instant/Flexible/Deep)**: Archival (Cold); retrieval times from milliseconds to 48 hours.
- **Features**:
    - **Versioning**: Protects against accidental deletion.
    - **Lifecycle Rules**: Automates transitions/deletions.
    - **Replication**: CRR (Cross-Region) for DR; SRR (Same-Region) for logs/sync.
    - **MFA Delete**: Extra security for deletions.
- **Security**: IAM policies (Identity), Bucket policies (Resource), and encryption (SSE-S3, SSE-KMS, SSE-C).
- **Object Lock**: Write-Once-Read-Many (WORM) for compliance.
