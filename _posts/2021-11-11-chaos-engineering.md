---
layout: post
title: "Chaos Engineering"
categories: reliability_engineering
tags: reliability_engineering
---

* TOC
{:toc}



"- Simulating the failure of an entire region or datacenter.
- Partially deleting Kafka topics over a variety of instances to recreate an issue that occurred in production.
- Injecting latency between services for a select percentage of traffic over a predetermined period of time.
- Function-based chaos (runtime injection): Randomly causing functions to throw exceptions.
- Code insertion: Adding instructions to the target program and allowing fault injection to occur prior to certain instructions.
- Time travel: Forcing system clocks out of sync with each other.
- Executing a routine in driver code emulating I/O errors.
- Maxing out CPU cores on an Elasticsearch cluster."
https://www.oreilly.com/library/view/chaos-engineering/9781491988459/ch01.html



## Gremlin

Have telemetry built to supplement Gremlin metrics



### Resource

CPU

Memory

IO

Disk



### State

Shutdown

Time Travel

Process Killer



### Network

Blackhole
"Black-hole attacks occur when a router deletes all messages it is supposed to forward. From time to time, a router is misconfigured to offer a zero-cost route to every destination in the Internet. This causes all traffic to be sent to this router. Since no device can sustain such a load, the router fails."

Latency

Packet Loss

DNS



## Resiliency Testing

Failure Modes & Effect Analysis (FMEA)

Build Scenarios



### Game Days

Practical Scenarios

Failure Modes
Test Mechanism(s)
Expected Results



### Table-Top Exercises

Theoretical Scenarios

Failure Modes
Explore Hypothetically
Capture Preparedness


