---
layout: post
title: "Thinking About Optimization Strategies"
categories: optimization 
tags: optimization
---

(Originally published at: <a href="https://nyedis.com/thinking-about-optimization-strategies">Thinking About Optimization Strategies</a>)

There are a lot of optimization techniques but what’s not often covered is how to think about this. It’s near the end of 2023 and I wanted to cover this as a bridge to other software engineering topics.
 
When looking at software, you’ll want to consider the forest. Before you start planting any tree, you’ll want to resolve any critical production issue. After that, the first thing you should look at is maintainability and readability.
 
The very first thing you can do is focus on established standards. This depends on the language base but let’s say your application is developed in mainly Python or Java. Here are some examples. In Python, variables are typically snake_case (see PEP 8). In Java, variables are typically camelCase. Function and class naming standards may be different from variable naming standards. If you can easily see the variable names by glancing at the code, feel free to do so. Otherwise I recommend using a code linter.
Look for variables that have names like “x” or “ii”. If you cannot read the code like it’s English (or as close to it as possible), ask whoever wrote this to give it a better name. Something like this is acceptable: fetch_price, calculate_trajectory
Use docstrings for Python for classes, comment wherever possible, etc. Follow best practices like DRY (don’t repeat yourself), etc.
 
There are a lot of resources on this. Your code will be a lot more readable once you have gotten through this. This makes the next steps much easier to do. Linus Torvalds once said something about making code less complex which will help you do really complex things in the long run: “The answer to that is that if you need more than 3 levels of indentation, you’re screwed anyway, and should fix your program.”
 
One way to check for complexity is to use the Cyclomatic complexity. The formula for this is: CC = E – N + 2P
 
E is edge, which represents a path
N is node, which represents a block of function
P is connected components, representing individual programs
 
You can draw a graph and plug in the numbers accordingly. Then you just need to tackle code with high complexity (typically those with 10+). Those with medium (6-10) or low (0-5), you can come back to later. This score chart is actually according to Code Complete.
 
But this is probably not necessary. Sometimes high complexity is justified due to the nature of the problem. If time is an issue, you just need to focus on the obvious ones. Writing good unit tests can help catch issues like this. Writing tests will also ensure that when you refactored your code, you did not change the intended behavior.
 
Once your code is easier to understand, you can start looking for things like:
Performance improvements
Resource utilization
Codebase reduction
Scalability enhancement
 
Any of these can be a book on its own. Here is a short summary of each one.
Performance improvements: you can start by measuring the impact the target has on the system. Consider running a profiler. A well-known tool like JMeter works. You can look at the time (execution time, loading time, etc.) and figure out what’s acceptable and what’s not.
 
Resource utilization: one of my favorite tool is Dynatrace but there are others as well. It all depends on what you are monitoring but the idea is to find the obvious bottlenecks and reduce resource utilization where possible. Is it hogging up all the bandwidth in the network? Is the memory constantly overloaded? The list goes on (CPU cycles, disk space, etc.).
 
Codebase reduction: first start by quantifying everything. For example, figure out what files you have that are duplicates. If you see multiple Bootstrap files in different folders, is it possible to use a Bootstrap CDN instead?
 
Scalability enhancement: find out what your min-max baseline is. The goal is to assess your product’s ability to handle more user or data without degradation in performance and experience. You need to understand your operational capacity under varying loads. You can start by conducting load and stress test. You can also do this to the environment that your application runs on as well. A lot of this hinges on the architectural decisions that was made and may need to be modified.
 
Of course, there are a lot more. I’ve been with clients have teams dedicated to this effort. They tend to be the most successful at delivering the best experience for customers because they can quickly pivot for the market.
 
Sifer Aseph

Cybersecurity Engineer @ Nyedis
