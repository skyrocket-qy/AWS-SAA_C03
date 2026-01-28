# AWS Application Discovery Service

Helps plan migration by gathering inventory and behavior data from on-premises data centers.

### Key Exam Points
- **Planning Phase**: Used *before* migration to discover local infrastructure.
- **Agentless Discovery**: VM-level info (CPU/RAM/Disk) via VMware vCenter; no OS-level view.
- **Agent-based Discovery**: Detailed info (processes, network dependencies) via installed agents; required for **dependency mapping**.
- **Integration**: Syncs data with **AWS Migration Hub**.
- **Lifecycle**: Used for planning; actual migration is then performed by **[AWS Application Migration Service (MGN)](aws_mgn.md)**.

