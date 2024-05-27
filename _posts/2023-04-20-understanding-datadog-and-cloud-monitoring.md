---
layout: post
title: "Understanding Datadog & Cloud Monitoring"
categories: datadog
tags: cloud datadog
---

(Originally published at: <a href="https://www.nyedis.com/post/understanding-datadog-cloud-monitoring">Understanding Datadog & Cloud Monitoring</a>)

If you have ever worked with large and complex systems, then you know how important monitoring is. Even more so if the system isn't entirely in your control, like the cloud. The Shared Responsibility Model that AWS works with goes into details of who is responsible for what. A common analogy used is a car. If you lease a car, the dealer handles making sure the car works before leasing it to you. Your responsibility is to ensure that the car still works at the end of the lease.

As a large bank, there is an additional layer on top of that. For example, AWS is responsible for building out the infrastructure. We need to ensure that the uptime is there for the infrastructure, and act accordingly. For many of our services, it's absolutely critical that we can respond to various events and to do that, we need to build out monitoring.

While I write about AWS, this applies to other cloud services like Azure and OCI (Oracle Cloud Infrastructure). The general idea applies – if I need to react, I need to know. And to do that, I need to be able to perform observations. This will give customers the reliability and performance they can rely on when banking. This is also the availability part in the CIA triad which is a security component that we also care about.

One of my favorite cloud observability tools is Datadog. It has a cute mascot and makes real-time monitoring easy to do. It provides another perspective and adds a layer of redundancy. I like Splunk but what if the Splunk sidecar is down? What if for some reason it stops taking in logs? Datadog can cover for Splunk (and the reverse is true as well).

Datadog lets me focus on structured data. (For unstructured data, I can just use Splunk.) For example, if I'm working on an app issue, I would like to be able to differentiate between the upstream and downstream effects.

Structured data includes things that you would find in AWS services like RDS, along with customer's transaction history. I could build many dashboards and each can focus on specific things. Here is an example list and the questions you could ask:

- Overall health of the system ("are we up?")
- Network connectivity ("how many dropped connections are there?")
- CPU ("is our CPU utilization within expected range?")
- Memory ("are we experiencing abnormal memory use?")

Even a layperson can come up with more questions that Datadog can answer. Here are some more examples. We can have Datadog tell us if customers are experiencing latency or if our load balancers are unable to serve.

A real life example that I can share with you is that recently, we had a Splunk alert pop up that gave us a warning about a failure in one of our apps. I knew it was hosted on one of our EKS pods so I first checked to see if that was the issue. I opened up our EKS dashboard on Datadog and asked: Is the node status showing green? Let’s say we should see 10, do we see 10? Was there any node condition that shows it through an error?

I was able to see that a few of our EKS pods were down. I documented this incident and notified the appropriate team. I was able to get Splunk to confirm this was an indeed the culprit by getting a timechart. This reinforced my case by providing more evidence.

Without Datadog, it would have taken us a lot longer to figure out, possibly many hours. I'd have to ask different teams for access to systems I probably shouldn't have access to. I may even need to submit a ticket to reach out to AWS.

With Datadog, I can be armed with knowledge that I've done my due diligence. Datadog greatly reduced the toil for us.



Sifer Aseph

Cybersecurity Engineer @ Nyedis
