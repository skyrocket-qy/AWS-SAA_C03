# HLS (HTTP Live Streaming)

**HLS** is the standard protocol for adaptive bitrate video streaming over HTTP/S.

### Key Exam Points
- **Architecture**: Breaks video into small chunks (segments) referenced by a manifest file (`.m3u8`).
- **Scalability**: Designed for massive scale via **Amazon CloudFront** caching (Edge Locations).
- **AWS Workflow**: S3 (Storage) -> **MediaConvert** (Transcode to HLS) -> CloudFront (Distribution).
- **Adaptive Bitrate (ABR)**: Automatically adjusts video quality based on the user's network speed.
- **vs. RTMP**: RTMP is legacy/deprecated; HLS is the modern, scalable standard for CDNs.
