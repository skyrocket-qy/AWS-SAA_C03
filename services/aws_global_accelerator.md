# AWS Global Accelerator

**AWS Global Accelerator** improves application availability and performance for global users using the AWS internal network.

### Key Exam Points
- **Static IPs**: Provides **two static Anycast IP addresses** as a fixed entry point.
- **Mechanism**: Traffic enters the AWS network at the Edge Location closest to the user, bypassing the public internet to reach application endpoints (ALB, NLB, EC2).
- **Failover**: Instant failover to healthy endpoints without DNS caching issues.
- **vs. CloudFront**: 
    - **CloudFront**: Focuses on **caching** (HTTP/HTTPS) at the edge.
    - **Global Accelerator**: Focuses on **network path optimization** (TCP/UDP) over the global network. No caching.
- **Use Case**: Gaming (UDP), VoIP, or apps requiring fixed IP addresses.
