# AWS Lake Formation

**AWS Lake Formation** simplifies setting up, securing, and managing an S3-based data lake.

### Key Exam Points
- **Security**: Centralized, **fine-grained access control** (column-level, row-level, and cell-level permissions).
- **Automation**: Uses **Glue Crawlers** and **ETL** to ingest and catalog data from multiple sources.
- **Sharing**: Allows secure **cross-account** data sharing without copying data.
- **Integration**: Provides a unified permissions layer for Athena, Redshift Spectrum, and EMR.
- **Use Case**: Use when you need complex permissions (e.g., "User A can only see columns 1-3") on S3 data.
