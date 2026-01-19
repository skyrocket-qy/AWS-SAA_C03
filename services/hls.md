# HLS (HTTP Live Streaming)

**HLS (HTTP Live Streaming)** is an adaptive bitrate streaming communications protocol implemented by Apple Inc. It is the most widely used protocol for video streaming today.

## Overview

HLS works by breaking down a video file into a sequence of small HTTP-based file downloads. Each download loads one short chunk (segment) of an overall potentially unbounded transport stream.

### Key Components
- **Index/Manifest File (`.m3u8`)**: A text file that lists the available streams (different bitrates) and the URLs for the individual video segments.
- **Segments (`.ts` or `.m4s`)**: The actual video/audio data cut into small chunks (usually 2-10 seconds long).

## Why HLS?

- **Standard HTTP**: Uses standard HTTP/S ports (80/443), making it firewall-friendly and compatible with any standard web server.
- **Adaptive Bitrate Streaming (ABR)**: The player can dynamically change the video quality based on the user's current network bandwidth.
- **Scalability**: Because segments are standard files, they can be easily cached by **Amazon CloudFront** edge locations, allowing for massive scale delivery.

## AWS Integration

In a typical AWS media architecture:
1.  **Source**: Raw video is stored in an **Amazon S3** bucket.
2.  **Transcode**: **AWS Elemental MediaConvert** converts the raw video into HLS format (creating the `.m3u8` and segment files).
3.  **Distribution**: **Amazon CloudFront** caches the segments and serves them to global viewers with low latency.

## RTMP vs. HLS (Legacy Comparison)

| Feature | RTMP (Legacy) | HLS (Modern) |
| :--- | :--- | :--- |
| **Protocol** | Custom TCP (Port 1935) | HTTP/S (Port 80/443) |
| **Status** | Deprecated in CloudFront | Current Industry Standard |
| **Caching** | Difficult to cache at scale | **Optimized for CDN Caching** |
| **Playback** | Requires Flash Player | Native in all modern devices |

## Exam Tips

- **Scalability**: If you need to stream video to thousands or millions of users globally, the answer is **S3 + MediaConvert + CloudFront (HLS)**.
- **Performance**: High-resolution video streaming requires CloudFront for caching to reduce latency and origin (S3) load.
- **Protocols**: Remember that **RTMP is deprecated** in CloudFront. Use HLS or DASH for modern streaming requirements.
