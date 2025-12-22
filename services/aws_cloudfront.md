# Amazon CloudFront

Amazon CloudFront is a fast content delivery network (CDN) service that securely delivers data, videos, applications, and APIs to customers globally with low latency and high transfer speeds.

## Key Concepts

*   **Edge Locations**: Global network of data centers where content is cached. When a user requests content, it is served from the nearest Edge Location to minimize latency.
*   **Regional Edge Caches**: Larger caches that sit between the origin and Edge Locations. Broadens the cache width and reduces the load on your origin.
*   **Distributions**: The configuration unit of CloudFront (e.g., associated with your domain name and origin).

## Origins

The source of the content CloudFront delivers.

*   **S3 Bucket**: Best for static content (images, CSS, JS).
    *   **Restricting S3 Access**: To ensure users access content *only* through CloudFront (not directly via S3 URL):
        *   **Origin Access Control (OAC)** *(Recommended/New)*:
            - Supports all S3 buckets in all AWS Regions.
            - Supports S3 **server-side encryption with KMS (SSE-KMS)**.
            - Supports dynamic requests (PUT/DELETE) to S3.
        *   **Origin Access Identity (OAI)** *(Legacy)*:
            - A special CloudFront identity that you associate with your distribution.
            - S3 bucket policy grants access only to this OAI.
            - Does **NOT** support SSE-KMS or dynamic requests.
            - Being replaced by OAC.
*   **Custom Origin**: Application Load Balancer (ALB), EC2 instance, or an on-premises server (publicly accessible).

## Key Features

*   **HTTPS Support**: Supports custom SSL/TLS certificates (via ACM) and SNI.
*   **Geo-Restriction**: You can allow or block users from specific countries.
*   **Signed URLs / Signed Cookies**: Restrict access to premium content (e.g., paid video streaming).
*   **Security Integration**: Integrates with **AWS WAF** (Web Application Firewall) to block attacks and **AWS Shield** for DDoS protection.

## Edge Computing

### CloudFront Functions
- **Lightweight JavaScript** functions for high-scale, latency-sensitive operations.
- Runs at **Edge Locations** (closer to users).
- Use Case: Simple header manipulation, URL rewrites, cache key normalization.
- Sub-millisecond startup, millions of requests/second.

### Lambda@Edge
- **Full Lambda functions** (Node.js or Python) running at Regional Edge Caches.
- More powerful than CloudFront Functions (can make network calls, access request body).
- **Trigger Points**:
    - **Viewer Request**: After CloudFront receives a request from a viewer.
    - **Origin Request**: Before CloudFront forwards the request to the origin.
    - **Origin Response**: After CloudFront receives the response from the origin.
    - **Viewer Response**: Before CloudFront returns the response to the viewer.

#### Common Use Cases
- **User-Agent Header**: Inspect the `User-Agent` header to serve different content based on device type (mobile vs. desktop).
- **A/B Testing**: Route users to different origin versions.
- **Authentication/Authorization**: Validate tokens at the edge before reaching the origin.
- **Dynamic Content Generation**: Generate personalized responses at the edge.
- **SEO**: Serve pre-rendered pages to bots.

### CloudFront Functions vs Lambda@Edge

| Feature | CloudFront Functions | Lambda@Edge |
| :--- | :--- | :--- |
| **Language** | JavaScript only | Node.js, Python |
| **Execution Location** | Edge Locations | Regional Edge Caches |
| **Triggers** | Viewer Request/Response only | All 4 triggers |
| **Network Access** | No | Yes |
| **Request Body Access** | No | Yes (Origin triggers) |
| **Max Execution Time** | < 1 ms | 5 sec (Viewer) / 30 sec (Origin) |
| **Scale** | Millions of requests/sec | Thousands of requests/sec |

## Exam Tips
- Use **Lambda@Edge** to inspect/modify `User-Agent` or other headers for device-specific content.
- Use **CloudFront Functions** for simple, high-volume tasks (header manipulation, redirects).
- Lambda@Edge functions must be deployed in **us-east-1** (N. Virginia).
