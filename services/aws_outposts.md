# AWS Outposts

**AWS Outposts** is a fully managed service that extends AWS infrastructure, AWS services, APIs, and tools to virtually any datacenter, co-location space, or on-premises facility for a truly consistent hybrid experience.

## Key Concepts
- **Hybrid Cloud**: It allows you to run AWS services on-premises.
- **Hardware**: AWS actually strips racks and servers (Outposts) to your location and installs them.
- **Extension of Region**: It works as an extension of an AWS Region. You can extend your VPC into the Outpost.

## Use Cases
- **Low Latency**: Applications that require single-digit millisecond latency to end-users or on-premises systems (e.g., high-frequency trading, industrial automation).
- **Local Data Processing**: Processing large datasets locally to save on data transfer costs or time (e.g., medical imaging, media content creation).
- **Data Residency**: Keeping data within a specific country or state to meet regulatory requirements.

## Networking
- **Local Gateway (LGW)**: A logical component that routes traffic to your on-premises network. It is similar to an IGW but for the local network.
- **Direct Connect**: You usually connect your Outpost back to the AWS Region via AWS Direct Connect or a VPN.

## Exam Tips
- Think **"AWS on-premises"**. If a question asks about running AWS infrastructure in your own data center, the answer is likely Outposts.
- **Latency & Residency**: Key drivers for adoption.
- **Managed Service**: Even though it's on-prem, AWS manages, monitors, and patches the infrastructure.
