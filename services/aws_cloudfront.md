# Amazon CloudFront

**Amazon CloudFront** is a Content Delivery Network (CDN) that caches content at global **Edge Locations** to reduce latency.

### Key Exam Points
- **Origins**: S3 buckets, ALB, EC2, or custom HTTP servers.
- **S3 Security**: Use **Origin Access Control (OAC)** to restrict S3 access so users must go through CloudFront.
- **Security**: Integrates with **AWS WAF** (firewall) and **AWS Shield** (DDoS).
- **Edge Computing**:
    - **CloudFront Functions**: Lightweight JS for high-scale header/URL manipulation at Edge Locations (< 1ms).
    - **Lambda@Edge**: Full Node.js/Python functions at Regional Edge Caches for complex logic (network calls, body access).
- **Key Use Case**: Set `User-Agent` headers or perform A/B testing at the edge.
