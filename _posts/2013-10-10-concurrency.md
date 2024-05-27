---
layout: post
title: "Concurrency"
categories: software_engineering
tags: software_engineering P2P IPFS parallel HA proxy
---

* TOC
{:toc}

##

cache invalidation

parallel slowdown

synchronization

barrier

explicit parallelism

massively parallel

Strong consistency vs eventual consistency (guaranteed but slower or eventually but faster)



Intel Hyper-Threading
simultaneous multithreading



### Load Balancer

"A load balancer distributes incoming client requests among a group of servers, in each case returning the response from the selected server to the appropriate client."

Oracle Real Applications Clusters (RAC)

ALB, application load balancer
NLB, network load balancer

Stickiness, sticky sessions

Stateless sessions



#### High Availability

Redundancy

Active/Passive (failover)

Active/Active (load balancing)



##### HAProxy

HA, high availability

offers high availability, load balancing, proxying for TCP and HTTP-based applications
well suited for websites working under very high loads while needing persistence for layer 7 processing

when HAProxy is started, it will do these three things:

  1. process incoming connections
  2. periodically check server status
  3. exchange information with other HAProxy nodes

## MapReduce

"MapReduce is a programming model and software framework for processing large datasets in parallel across a distributed cluster of computers. It was originally developed by Google and is now an open-source project managed by the Apache Foundation. MapReduce consists of two main components: the Map step, in which the dataset is divided into smaller pieces and each piece is processed independently, and the Reduce step, in which the results of the Map step are combined to produce the final output. This allows MapReduce to process very large datasets efficiently by distributing the work across many machines. It is commonly used for large-scale data processing and analysis tasks, such as those involving big data and machine learning."


