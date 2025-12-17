# Elastic Load Balancing (ELB)

Elastic Load Balancing automatically distributes incoming application traffic across multiple targets, such as EC2 instances, containers, and IP addresses, in multiple Availability Zones.

## Load Balancer Types

### 1. Application Load Balancer (ALB)
*   **Layer**: Layer 7 (HTTP/HTTPS).
*   **Routing**: Advanced request routing based on content (host, path, header, query string, source IP).
*   **Targets**: EC2, ECS (containers), Lambda functions, IP addresses.
*   **Key Features**:
    *   **WAF Integration**: Supports Web Application Firewall.
    *   **HTTP/2 & WebSocket** support.
    *   **Redirects**: Can redirect HTTP to HTTPS.

### 2. Network Load Balancer (NLB)
*   **Layer**: Layer 4 (TCP/UDP/TLS).
*   **Performance**: Ultra-high performance, capable of handling millions of requests per second with ultra-low latency.
*   **IP Addresses**: Uses **static IP addresses** (one per AZ). Can also use Elastic IPs.
*   **Key Features**:
    *   **Source IP Preservation**: Preserves the client side IP address.
    *   **TLS Offloading**.

### 3. Gateway Load Balancer (GWLB)
*   **Layer**: Layer 3 (Gateway + Load Balancing).
*   **Use Case**: Deploy, scale, and manage virtual appliances (firewalls, IDS/IPS, deep packet inspection systems).
*   **Mechanism**: Uses **GENEVE** protocol on port 6081.

### 4. Classic Load Balancer (CLB)
*   *Legacy*. Supports both Layer 4 and Layer 7 but has fewer features than ALB/NLB.

## Key Features

*   **Heath Checks**: Periodically monitors the health of registered targets.
*   **Cross-Zone Load Balancing**: Distributes traffic evenly across all registered instances in all enabled Availability Zones.
*   **Sticky Sessions (Session Affinity)**: Binds a user's session to a specific target.

## Comparison Table

| Feature | Application Load Balancer (ALB) | Network Load Balancer (NLB) | Gateway Load Balancer (GWLB) |
| :--- | :--- | :--- | :--- |
| **Layer** | Layer 7 (HTTP/HTTPS) | Layer 4 (TCP/UDP) | Layer 3 (Gateway + Appliance) |
| **Use Case** | Web applications, Microservices, Containers | High performance, Gaming, Static IPs | Firewalls, Intrusion Detection |
| **IP Address** | Dynamic (DNS Name) | Static (1 per AZ) | n/a (GENEVE Endpoint) |
| **PrivateLink** | Supported (as target) | Supported (as provider) | Supported (as provider) |
