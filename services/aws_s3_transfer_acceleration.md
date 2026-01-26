# Amazon S3 Transfer Acceleration

**S3 Transfer Acceleration** enables fast, secure file transfers over long distances using Amazon CloudFront’s edge locations.

### Key Exam Points
- **Mechanism**: Data is uploaded to a nearby Edge Location and then routed over the optimized AWS backbone network to the S3 bucket.
- **Use Case**: Global customers uploading large files to a centralized bucket across continents.
- **Setup**: Must be enabled on the bucket; use the specific endpoint: `bucketname.s3-accelerate.amazonaws.com`.
- **Differentiator**: Best for **regular** high-speed uploads from varied geographic locations.
