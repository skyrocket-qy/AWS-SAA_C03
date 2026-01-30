# Amazon WorkSpaces

A managed, secure Desktop-as-a-Service (DaaS) solution. It helps you provision either Windows or Linux desktops in just a few minutes and quickly scale to provide thousands of desktops to workers across the globe.

### Key Exam Points
- **Desktop-as-a-Service (DaaS)**: Cloud-based virtual desktop that replaces traditional VDI (Virtual Desktop Infrastructure).
- **Persistent Storage**: Data is saved on the user's volume (D drive) and backed up to S3 automatically.
- **Security**: 
    - Data is encrypted at rest (via KMS) and in transit.
    - Integrates with **AWS Directory Service** (Managed Microsoft AD or AD Connector) for user authentication.
    - No data is stored on the local device used to access the WorkSpace.
- **Bundles**: Pre-configured hardware and software combinations (Value, Standard, Performance, Power, PowerPro, Graphics, GraphicsPro).
- **Pricing**: 
    - **Monthly**: Unlimited usage for a fixed monthly fee.
    - **Hourly**: Low monthly base fee plus a small hourly rate (best for part-time workers).
- **Network**:
    - Requires two subnets in a VPC.
    - Uses a "WorkSpaces Gateway" to stream the desktop to the client.
- **Protocol**: Supports **PCoIP** and **WSP** (Windows Streaming Protocol).

### Use Cases
- Remote work / Work from home.
- Contractors and temporary employees.
- High-security environments (data never leaves the VPC).
- Bring Your Own License (BYOL) for Windows 10/11 (requires dedicated physical hardware).
