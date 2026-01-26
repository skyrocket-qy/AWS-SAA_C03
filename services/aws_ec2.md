# Amazon EC2

**Amazon EC2** provides resizable compute capacity via virtual servers (instances).

### Key Exam Points
- **Purchasing Options**:
    - **On-Demand**: Pay-as-you-go; highest cost; no commitment.
    - **Spot**: Up to 90% discount; 2-minute interruption warning; use for fault-tolerant/batch workloads.
    - **Reserved (RI)**: 1 or 3-year commitment (Standard vs. Convertible); up to 72% discount.
    - **Savings Plans**: Commitment to $/hour spend; most flexible (applies to EC2, Fargate, Lambda).
    - **Dedicated Hosts**: Physical servers for licensing (BYOL) or strict compliance.
- **Spot Fleet**: Automates launching a mix of Spot and On-Demand instances to meet target capacity.
- **Placement Groups**: (Cluster, Spread, Partition) to optimize performance or availability.
- **Instance Store**: Ephemeral (lost if stopped/failed); highest I/O performance.
