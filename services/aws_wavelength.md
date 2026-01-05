# AWS Wavelength

**AWS Wavelength** combines the high bandwidth and ultra-low latency of 5G networks with AWS compute and storage services.

## Key Concepts
- **Edge Computing**: Wavelength embeds AWS compute and storage services within the telecommunications providers’ data centers at the edge of the 5G network.
- **Ultra-Low Latency**: By reaching application traffic from 5G devices without leaving the mobile operator’s network, Wavelength avoids the latency that would result from multiple hops to the internet to reach application servers.

## Use Cases
- **Mobile Edge Computing (MEC)**: Applications that require single-digit millisecond latencies.
- **Gaming**: Delivering high-fidelity game streaming to mobile devices.
- **AR/VR**: Rendering complex environments for augmented and virtual reality in real-time.
- **Connected Vehicles**: Enabling real-time data exchange for autonomous driving and vehicle-to-everything (V2X) communication.
- **ML Inference**: Running machine learning inference at the edge for smart factories and healthcare.

## Networking
- **Carrier Gateway**: A logical component that allows traffic to flow from the Wavelength Zone to the carrier's network and specific devices.
- **Wavelength Zone**: An AWS infrastructure deployment that embeds AWS compute and storage services within telecommunication providers’ data centers.

## Exam Tips
- **5G Network**: The keyword is **5G**. If a question mentions low latency for mobile devices using 5G, the answer is AWS Wavelength.
- Differentiate from **Outposts** (On-premises) and **Local Zones** (Extension of Region near large population centers, but not specifically inside a telecom 5G network).
