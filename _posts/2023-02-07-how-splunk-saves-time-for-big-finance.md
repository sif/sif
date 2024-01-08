---
layout: post
title: "How Splunk Saves Time for Big Finance"
categories: splunk 
tags: splunk observability
---

(Originally published at: <a href="https://www.nyedis.com/post/how-splunk-saves-time-for-big-finance">How Splunk Saves Time for Big Finance</a>)

When you work for one of the largest bank in the world, your work is often scrutinized. Every action you take must be justified. This is to protect all of the parties involved, the parties being the bank itself, the customers and hopefully you.

Given the size of the bank and all of the activities that go on, it’s impossible for any one team to track. The answer isn’t always to hire more people though that helps. The answer is multi-faceted and multi-layered. One of them is the use of Splunk.

Splunk is a useful tool for those in the observability and resiliency space. The need for large systems to be reliable and available at an absolute minimum for acceptable customer experience means you will need to be able to know what is going on at any given time without fail.

It is not very hard to learn to use Splunk especially if you have any technical background. Here is a real world example (with details fictionalized). Let’s say we have a ticket where a customer is experiencing some issue.

Naturally, you (should) have many questions. Questions like, “who is this customer?” “What is the problem?” With a relatively simple query in Splunk, you can find out:

<code>index=”bank_customer_system” sourcetype=”customer_profile” username=”abc123”
| eval status=if(httpCode!=200, “Problem”+”: “+httpCode)
| stats count(url) by url, status, time, response, request, traceId, user_agent
| sort by time</code>

It reads intuitively. In the starting line, you’re telling Splunk to pull a user from a log which is stored in some bucket. In the following lines, if there are entries in the log, it will output a list of web actions taken by the user and sorted by time. It will be in several columns which you can sort if you don’t want to sort by time.

If you did not have Splunk, you would have to chase down the right team for the knowledge and piece all of this together manually. You would need to reach out to the responsible Customer Service Representative who spoke to the customer on the phone and the Support team who made changes (if any) and so on.

You will probably still need to talk to them, but at least the scenario changes from “who is the customer and what is the issue?” to “how can we best help this customer?” This is one of the many tools used and why the bank remains competitive.

‍

Sifer Aseph

Cybersecurity Engineer @ Nyedis
