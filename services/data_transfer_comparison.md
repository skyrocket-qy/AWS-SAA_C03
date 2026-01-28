# Data Transfer and Migration Comparison

### Online Connectivity
- **Site-to-Site VPN**: Encrypted tunnel over **public internet**; fast setup; variable performance.
- **Direct Connect (DX)**: Dedicated **private connection**; bypasses internet; consistent performance; slow setup (weeks).

### Bulk Data Migration
- **Snow Family (Offline)**: Physical devices for **petabyte/exabyte** scale; best for limited/no internet.
- **DataSync (Online)**: Automated, accelerated transfers for **active data** (NFS, SMB, S3).
- **Transfer Family (Online)**: Managed **SFTP/FTP** entry point for S3 or EFS.
- **S3 Transfer Acceleration**: Faster **S3 uploads** over the internet via CloudFront Edge Locations.
- **Storage Gateway (Hybrid)**: On-premises caching and access to cloud storage.
- **Application Migration Service (MGN)**: [Automated server migration](aws_mgn.md) (Rehost/Lift-and-Shift).

