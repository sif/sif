---
layout: post
title: "Systems Design"
categories: systems_engineering
tags: systems_engineering shard
---

* TOC
{:toc}

hysterical raisins



- SQL vs NoSQL



to speed up your API performance:

- see if you can use caching, store the result of expensive computation
- connection pool
  - this is not usually doable with serverless architecture
- N+1 query problem, the solution to reduce round trip to the database is something like: fetch all data, then fetch all subset of data from this data you just fetched
- use pagination via limits and offset parameters
- JSON serialization
- compression
- for high throughput systems, use asynchronous logging

don't make optimization the first thing because they may introduce unnecessary complexity

get rid of bottlenecks first



## Cache

"A cache is a temporary storage area for frequently accessed data. Caches are used in a variety of systems to improve performance by reducing the time and effort required to access data. For example, a web browser might use a cache to store recently visited web pages, so that they can be quickly loaded from the cache instead of being downloaded from the internet again. Similarly, a database might use a cache to store recently accessed data, so that it can be quickly retrieved from the cache instead of being read from disk.

Caches are typically implemented in memory, which allows them to store and retrieve data much more quickly than other types of storage. This is because memory is much faster than disk storage, and it is also volatile, which means that it is erased when the system is turned off. Caches are managed by a cache manager, which is responsible for controlling which data is stored in the cache, how long it is stored, and how it is accessed and updated."

Remote Dictionary Server

Photon Redis is similar to Elasticache



## Batch Write

"A batch write is a process for efficiently storing or updating large amounts of data in a database or other storage system. Batch writes are often used in scenarios where the data is generated in large batches, such as from a data pipeline or a batch processing job, and it needs to be stored in the database in a way that minimizes the impact on performance and availability."



## [Load Balancer](https://www.afterlifesong.com/software_engineering/2013/10/10/concurrency.html)

## Sharding

"Sharding is a way of dividing a large dataset or workload into smaller parts that can be stored or processed separately. The goal of sharding is to distribute the data or workload across multiple machines or systems in order to improve performance and scalability. For example, a database that is too large to fit on a single machine can be "sharded" by dividing the data into smaller chunks and storing each chunk on a different machine. This allows the database to handle more requests and process more data in parallel, which can improve performance."


