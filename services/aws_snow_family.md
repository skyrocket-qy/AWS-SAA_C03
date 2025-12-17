# AWS Snow Family

The AWS Snow Family consists of physical devices used to migrate data into and out of AWS and to run computing operations at the edge (in environments with limited or no internet connectivity).

## Family Members

### 1. AWS Snowcone
*   **Description**: The smallest, most portable, and rugged member of the Snow Family. Roughly the size of a tissue box.
*   **Capacity**:
    *   **HDD**: 8 TB usable.
    *   **SSD**: 14 TB usable.
*   **Key Features**:
    *   Weighs 4.5 lbs (2.1 kg).
    *   Battery operated (optional).
    *   **AWS DataSync agent pre-installed** for online data transfer.
*   **Use Cases**: IoT data collection, healthcare, drone data, content distribution, edge computing in mobile environments.

### 2. AWS Snowball Edge
*   **Description**: A rugged, briefcase-sized device for larger data migration and edge computing.
*   **Types**:
    *   **Storage Optimized**: Up to 80 TB (HDD) or 210 TB (NVMe) usable storage.
    *   **Compute Optimized**: More vCPUs (up to 104) and memory, optional GPU, for running EC2 instances and Lambda functions.
*   **Use Cases**: Data center decommissioning, disaster recovery, large scale data collection, local processing (ML/Video).

### 3. AWS Snowmobile
*   **Description**: An Exabyte-scale data transfer service used to move massive amounts of data to AWS. It is a 45-foot ruggedized shipping container pulled by a semi-trailer truck.
*   **Capacity**: Up to **100 PB** per Snowmobile.
*   **Use Cases**: Extremely large data center migrations (e.g., video libraries, genomic sequences, seismic data).

## Comparison Table

| Feature | Snowcone | Snowball Edge | Snowmobile |
| :--- | :--- | :--- | :--- |
| **Capacity (Usable)** | 8 TB / 14 TB | 80 TB / 210 TB | 100 PB |
| **Portability** | Backpack / Drone | Checked Luggage / Courier | Semi-trailer Truck |
| **Typical Data Volume** | Terabytes | Petabytes | Exabytes |
| **Online Transfer** | Yes (DataSync) | No (Offline Only) | No (Offline Only) |
