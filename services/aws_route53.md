# Amazon Route 53

**Amazon Route 53** is a highly available and scalable DNS, domain registration, and health checking service.

### Key Exam Points
- **Routing Policies**:
    - **Simple**: Returns one/all records (no health checks).
    - **Weighted**: Distributes traffic by % (A/B testing).
    - **Latency**: Best performance for the user's region.
    - **Failover**: Active-Passive setup for DR.
    - **Geolocation**: Based on user country/continent (compliance).
    - **Geoproximity**: Based on geography + bias (requires Traffic Flow).
    - **Multi-value Answer**: Up to 8 healthy records (simple load balancing).
- **Alias Records**: Free queries for AWS resources (ELB, S3, CloudFront); preferred over CNAME.
- **Health Checks**: Monitors endpoints and triggers failover; can monitor CloudWatch Alarms for private resources.
- **DNSSEC**: Protects against spoofing/man-in-the-middle attacks.
