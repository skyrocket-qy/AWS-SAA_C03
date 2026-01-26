# Amazon Redshift vs. AWS Lake Formation

### Comparison Overview
- **Redshift (Data Warehouse)**: **Schema-on-Write** (structured); high-performance SQL analytics; storage is coupled with compute (though Spectrum decouples).
- **Lake Formation (Data Lake Layer)**: **Schema-on-Read** (unstructured/semi-structured); manages permissions and blueprints on top of **Amazon S3**.

### Key Exam Points
- **Security**: Lake Formation provides centralized, **fine-grained (row/column level)** access control for S3 data.
- **Integration**: The "Lake House" architecture uses **Redshift Spectrum** to query data managed by Lake Formation in S3.
- **Use Case**: 
    - **Redshift**: High-speed BI reporting and dashboards.
    - **Lake Formation**: Managing access to raw logs and large datasets in S3 for multiple services (Athena, EMR).
