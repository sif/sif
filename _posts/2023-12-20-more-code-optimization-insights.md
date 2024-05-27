---
layout: post
title: "More Code Optimization Insights"
categories: optimization 
tags: optimization
---

(Originally published at: <a href="https://nyedis.com/more-code-optimization-insights">More Code Optimization Insights</a>)

I explored some code optimization in my previous writing. I covered some basic ones that will allow your team to easily clean up hundreds or even thousands of lines of code. In this installment, I want to take the next step and cover more code optimizations that’ll help.

Of course, there are other factors that will help improve your software. The previous ones I’ve provided, your team can use for free. The bigger your budget (and team), the easier and faster you can do this. This will allow you to improve security and ultimately deliver a great customer experience.

You may ask, “how is this the case?” If your codebase is so difficult to understand, that only a few senior members of your team can understand it, you cannot possibly improve your code faster than your competitor whose entire team understands the codebase, including its junior members.

If your company isn’t willing to bring in more resources, bugs will remain out in the wild longer and customer experience will become stale. This is from the Linus’s law, which states, “given enough eyeballs, all bugs are shallow”. The more formal statement is: “Given a large enough beta-tester and co-developer base, almost every problem will be characterized quickly and the fix obvious to someone.”

There are companies out there that only hire senior engineers. Yet if you assign a senior engineer to do something that a junior engineer could, you’re not utilizing resources effectively. (Yes, companies like this do exist. \[1\]) Junior engineers could provide a fresh pair of eyes and catch something that a senior may have missed.

Time and time again we see that these large companies that only hire senior engineers get hacked because there aren’t a lot of resources dedicated to what would be considered junior level tasks. As customers, we’re surprised. “How? Don’t they have the state-of-the-art stuff?” The idea that “seniors don’t make mistake” is false. They do make mistakes, they’re human after all.

The other factor include things like good system design, documentation, flexible deadlines, etc. You would be surprised to find out how many sins are committed out there and your team may be one of them. Poor documentation, unwillingness to communicate knowledge, etc. Tribal knowledge is one of the worst.

First thing you can do in your codebase is to look for “falsy” checks. This means looking at checks that do something like this:

if not 0:
return “0 is falsy, I will therefore do something”

One of the solution is to be explicit and commenting. To be explicit, this would be better:

\# Check the variable x against a specific value 0
if x == 0:
return “now I am checking a specific variable against a specific value, now I will do something”

By doing this, you allow other members of your team (including the business team, not just the technical team) to know what your intentions are.

This will allow you to avoid (what is technically legal) code like double negatives. Like so:

if not not 0:
return “this is actually legal”

I tested this as well and found that this is legal too:

if not not not 0:
return “surprisingly legal”

Of course, I don’t recommend either. They should be avoided but they are legal. I encourage you to play around as some of this is language-specific behavior.

To touch on a little system design, the second thing you can look at is cache. Starting out, you might store cache in heap memory and use as needed. As your complexity grows, you may want to store them in something like a Gemfire.

Suppose you have an object that is frequently accessed but rarely changed, like products or an output (configuration, calculation, etc.), you could move that to the caching system.

Say you code has a Product class and you have something like:

product_cache = {product.id: product for product in load_products_from_database()}

You could do this instead:

from GemfireClient import *
client = GemfireClient(hostname=”localhost”, port=8080)
my_catalog_repo = client.create_repository(“catalog”)
my_catalog_repo.save(product)

The idea is similar in different caching systems like Redis and Gemfire. Hopefully this was helpful and provides something for you and your team to think about.

Sifer Aseph

Cybersecurity Engineer @ Nyedis

\[1\] https://isaaclyman.com/blog/posts/junior-developers/
