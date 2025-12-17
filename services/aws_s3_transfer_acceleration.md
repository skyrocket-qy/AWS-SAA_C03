# Amazon S3 Transfer Acceleration

Amazon S3 Transfer Acceleration enables fast, easy, and secure transfers of files over long distances between your client and an S3 bucket.

## Key Concepts

*   **How it Works**: It takes advantage of **Amazon CloudFront’s globally distributed Edge Locations**. As the data arrives at an Edge Location, data is routed to Amazon S3 over an optimized network path (AWS Backbone Network).
*   **Use Cases**:
    *   You have customers that upload to a centralized bucket from all over the world.
    *   You transfer gigabytes to terabytes of data on a regular basis across continents.
    *   Significantly higher speeds are required than standard Internet upload.

## Configuration

*   **Activation**: You must enable Transfer Acceleration on the bucket.
*   **Endpoint URL**: Instead of the standard endpoint, you use the accelerate endpoint:
    *   Standard: `mybucket.s3.us-east-1.amazonaws.com`
    *   Accelerated: `mybucket.s3-accelerate.amazonaws.com`

## Considerations

*   **Cost**: Additional cost applies for using Transfer Acceleration.
*   **Speed Comparison Tool**: AWS provides a speed comparison tool to see the benefit from different locations.
