---
title: "Blog 2"
date: 2026-08-07
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---
{{% notice warning %}}
⚠️ **Note:** The information below is for reference purposes only. Please **do not copy verbatim** for your report, including this warning.
{{% /notice %}}

# Data Caching Across Microservices in a Serverless Architecture

Organizations are re-architecting traditional monolithic applications into microservices to gain agility and scalability. Since each microservice performs a single function, it may need to retrieve and process data from multiple disparate sources (data stores, legacy systems, or on-premises databases). These real-time queries introduce significant latency. Implementing a caching layer close to the serverless compute layer (AWS Lambda) helps reduce latency and minimizes service-to-service communication.

---

## Use Case 1: On-Demand Cache to Reduce Real-Time Calls

In this scenario, the **Cache-Aside (Lazy Loading)** design pattern is used. An object is only cached when it is requested by a consumer, and the microservice decides if the object is saved to the cache.

### Real-World Workflow
1. **Request Reception:** The Billing microservice receives a request and checks the cache using an `object_key`. If the data exists (cache hit), it returns the response immediately.
2. **Cache Miss Handling:** If the object is missing (cache miss), the Billing service queries various backend systems, compiles the data, sends it to the user, and caches it with a designated Time-to-Live (TTL).
3. **Cache Invalidation:** When a payment is processed by the Payment microservice, the balance cache becomes stale. The Payment service publishes an asynchronous `payment_processed` event to the Event Store.
4. **Cache Manager Action:** The CacheManager microservice listens to the event and deletes/updates the corresponding cache entry.

<img src="https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/07/14/Figure-1.-Reducing-latency-by-caching-frequently-accessed-data-on-demand.png" alt="Figure 1. Reducing latency by caching frequently accessed data on demand" style="max-width:100%; border-radius: 8px; margin: 16px 0;" />

### Recommended AWS Architecture
- **API Gateway:** Exposes API operations.
- **AWS Lambda:** Powers the compute/microservices layer.
- **Amazon ElastiCache:** Serves as the high-speed in-memory data cache.
- **Amazon EventBridge:** Routes custom events asynchronously.

<img src="https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/07/14/Figure-2.-Suggested-AWS-services-for-implementing-use-case-1.png" alt="Figure 2. Suggested AWS services for implementing use case 1" style="max-width:100%; border-radius: 8px; margin: 16px 0;" />

---

## Use Case 2: Proactive Caching of Massive Volumes of Data

During migrations, some legacy backend systems (like mainframes) process data in batch jobs and cannot handle the high call volume from modern front-end applications. In this case, data is proactively identified and loaded into the cache upfront.

### Real-World Workflow
1. **Initial Load & CDC:** An automated process loads data into the cache initially. Subsequent updates are captured from the system of record using a Change Data Capture (CDC) pipeline.
2. **Read-Only Caching:** Microservices read directly from the pre-populated cache instead of triggering real-time backend calls.
3. **On-Demand Refresh:** If a payment updates data, the microservice writes directly to the system of record and triggers an event. The CacheManager then updates the corresponding cache entry.

<img src="https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/07/14/Figure-3.-Eliminating-real-time-calls-by-caching-massive-data-volumes-proactively.png" alt="Figure 3. Eliminating real-time calls by caching massive data volumes proactively" style="max-width:100%; border-radius: 8px; margin: 16px 0;" />

### Recommended AWS Architecture
- **Amazon DynamoDB:** Serves as the key-value database providing low-latency storage.
- **Amazon DynamoDB Accelerator (DAX):** Provides a fully managed, in-memory cache in front of DynamoDB tables to deliver microsecond response times.

<img src="https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/07/14/Figure-4.-Suggested-AWS-services-for-implementing-use-case-2.png" alt="Figure 4. Suggested AWS services for implementing use case 2" style="max-width:100%; border-radius: 8px; margin: 16px 0;" />

---

## Additional Latency Optimization Best Practices
- **Lambda Environment Reuse:** Declare static configurations and data variables outside the handler code to cache state between warm starts.
- **AWS Lambda Extensions:** Run secondary processes alongside the primary Lambda handler to manage caching, configuration, or security keys.
