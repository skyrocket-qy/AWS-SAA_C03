# AWS Global Accelerator

AWS Global Accelerator is a networking service that improves the availability and performance of the applications that you offer to your global users.

## Key Concepts

*   **Global Network**: It uses the highly available and congestion-free AWS global network to direct internet traffic from your users to your applications on AWS.
*   **Static IP Addresses**: It provides two static public IP addresses (Anycast IPs) that act as a fixed entry point to your application endpoints, such as:
    *   Application Load Balancers
    *   Network Load Balancers
    *   Amazon EC2 instances
    *   Elastic IP addresses
*   **Traffic Routing**: It directs traffic to the optimal endpoint based on performance, reacting instantly to changes in network health or configuration.

## How It Works

1.  **Users** connect to the static IP addresses provided by Global Accelerator.
2.  Traffic enters the AWS global network at the **Edge Location** closest to the user.
3.  Traffic is routed through the AWS global network to the **Endpoint Group** in the closest healthy AWS Region.
4.  The request is delivered to the **Endpoint**.

## Components

*   **Accelerator**: Directs traffic to optimal endpoints over the AWS global network.
*   **Listeners**: Process inbound connections from clients based on protocol (TCP/UDP) and port.
*   **Endpoint Groups**: Associated with a specific AWS Region. Include one or more endpoints in the region.
*   **Endpoints**: The resources (ALB, NLB, EC2, EIP) where traffic is routed.

## Benefits

*   **Performance**: Improved application performance by reducing latency, jitter, and packet loss.
*   **Availability**: Continuous health monitoring of application endpoints and instant failover to healthy endpoints (within seconds) without DNS caching issues.
*   **Ease of Management**: Static IP addresses mean you don't have to update client-side DNS records or firewall allow-lists when you move endpoints or scale.
*   **Security**: By exposing only the Global Accelerator static IPs, you can keep your backend resources (endpoints) private or protected by security groups that only allow traffic from Global Accelerator.

## Comparison with Amazon CloudFront

| Feature | Amazon CloudFront | AWS Global Accelerator |
| :--- | :--- | :--- |
| **Primary Goal** | **Cache content** at Edge Locations (Content Delivery). | **Optimize network path** over AWS global network (Performance/Availability). |
| **Protocol Support** | **HTTP/HTTPS** (Layer 7). | **TCP/UDP** (Layer 4) and HTTP/HTTPS. |
| **Caching** | **Yes** (Static and Dynamic content). | **No** (Traffic is proxied to origin). |
| **IP Addresses** | **Dynamic** (Resolved via DNS to Edge Location IP). | **2 Static Anycast IPs** (Fixed entry points). |
| **Ideal For** | Website content, videos, APIs, static assets. | Gaming (UDP), IoT (MQTT), VoIP, non-HTTP apps, or requiring fixed IPs. |
| **WAF Support** | **Yes** | **Yes** (Indirectly, if endpoint is ALB). |
