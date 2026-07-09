---
title: "Blog 3"
date: 2026-07-08
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---
{{% notice warning %}}
⚠️ **Note:** The information below is for reference purposes only. Please **do not copy verbatim** for your report, including this warning.
{{% /notice %}}

# Optimizing your AWS Infrastructure for Sustainability, Part III: Networking

Optimizing the network layer is a critical component of designing sustainable cloud architectures on AWS. By reducing the physical distance data travels and minimizing the overall size of transmitted data, organizations can decrease resource consumption and lower their carbon footprint. This post covers key strategies to improve networking efficiency for sustainability.

---

## 1. Reducing the Network Traveled per Request

Data transfer efficiency is heavily influenced by the routing paths and distance. Organizations should aim to keep data local and process it closer to the user.

- **Read Local, Write Global:** Choose AWS Regions closest to the majority of users. For geographically distributed users, maintain local read-only copies of data (e.g., using Amazon RDS cross-Region read replicas or Amazon DynamoDB global tables).
- **Use a Content Delivery Network (CDN):** Amazon CloudFront caches static content at global Edge locations, shortening the physical distance data must travel from origin servers.

<img src="https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/10/21/Figure-1.-Comparison-of-accessing-an-S3-bucket-directly-versus.jpg" alt="Figure 1. Comparison of accessing an S3 bucket directly versus via CloudFront" style="max-width:100%; border-radius: 8px; margin: 16px 0;" />

- **Optimize CloudFront Cache Hit Ratio:** Fine-tune headers, query strings, and cookies forwarding settings to maximize cache hits, preventing unnecessary roundtrips to the origin.
- **Leverage Edge Services:** Use edge compute capabilities like CloudFront Functions or Lambda@Edge for simple tasks (routing, headers manipulation) and AWS IoT Greengrass for edge compute on IoT devices.

---

## 2. Reducing the Size of Data Transmitted

Minimizing the payload size directly reduces the energy required to transmit packets across the network.

- **Serve Compressed Files:** Enable automatic compression (e.g., Gzip or Brotli) on CloudFront to compress static resources before delivery.
- **Enhance EC2 Network Performance:** Enable Jumbo frames (MTU up to 9001 bytes) inside VPCs to increase packet payload sizes and reduce network processing overhead.
- **Optimize APIs:**
  - Compress REST API payloads.
  - Choose **Edge-optimized API endpoints** for geographically dispersed users.
  - Choose **Regional API endpoints** for backend services located in the same region to avoid unnecessary routing overhead.
  - Implement API response caching.

---

## 3. Monitoring and Metrics for Networking Sustainability

Monitoring network behavior helps identify bottlenecks and idle data paths. You can leverage:
- **CloudFront Cache Hit Rate** in CloudWatch metrics.
- **Amazon S3 Data Transfer** (Bytes In/Out).
- **Amazon EC2 Network Packets** (NetworkPacketsIn/NetworkPacketsOut).
- **AWS Trusted Advisor** to check CloudFront content delivery optimization and forwarded headers.

<img src="https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/10/21/Figure-2.-Overview-of-services-that-integrate-with-CloudWatch-and-Trusted-Advisor-for-monitoring-metrics.jpg" alt="Figure 2. Overview of services that integrate with CloudWatch and Trusted Advisor" style="max-width:100%; border-radius: 8px; margin: 16px 0;" />
