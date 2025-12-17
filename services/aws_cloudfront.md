# Amazon CloudFront

Amazon CloudFront is a fast content delivery network (CDN) service that securely delivers data, videos, applications, and APIs to customers globally with low latency and high transfer speeds.

## Key Concepts

*   **Edge Locations**: Global network of data centers where content is cached. When a user requests content, it is served from the nearest Edge Location to minimize latency.
*   **Regional Edge Caches**: Larger caches that sit between the origin and Edge Locations. Broadens the cache width and reduces the load on your origin.
*   **Distributions**: The configuration unit of CloudFront (e.g., associated with your domain name and origin).

## Origins

The source of the content CloudFront delivers.

*   **S3 Bucket**: Best for static content (images, CSS, JS).
    *   **Security (S3 Origin Access)**: To ensure users access content *only* through CloudFront (and not directly via S3 URL), use **Origin Access Control (OAC)** (Recommended/New) or **Origin Access Identity (OAI)** (Legacy).
*   **Custom Origin**: Application Load Balancer (ALB), EC2 instance, or an on-premises server (publicly accessible).

## Key Features

*   **HTTPS Support**: Supports custom SSL/TLS certificates (via ACM) and SNI.
*   **Geo-Restriction**: You can allow or block users from specific countries.
*   **Signed URLs / Signed Cookies**: Restrict access to premium content (e.g., paid video streaming).
*   **Edge Computing**:
    *   **CloudFront Functions**: Lightweight JS functions for high-scale, latency-sensitive manipulations (e.g., header manipulation).
    *   **Lambda@Edge**: More powerful computing at the edge (e.g., complex logic, external calls).
*   **Security Integration**: Integrates with **AWS WAF** (Web Application Firewall) to block attacks and **AWS Shield** for DDoS protection.
