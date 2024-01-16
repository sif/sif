---
layout: post
title: "Simple Code Optimization Insights"
categories: optimization 
tags: optimization
---

(Originally published at: <a href="https://nyedis.com/simple-code-optimization-insights">Simple Code Optimization Insights</a>)

In most if not all of my engagements with clients, I’ve had to write code. What I’ve found is that there is a common recurring theme. Different teams will push code as soon as possible, then revisit it later on.

Why would they do that? A few reasons. Better understanding of the problem. Bugs. Technology upgrades. These are the major ones. Does that mean you optimize as soon as you get the chance?

Donald Knuth once said that “premature optimization is the root of all evil”. He’s not wrong, but I think people often misunderstand this. The keyword is premature. You do optimize as soon as you ge the chance but only if it’s not premature optimization.

If your team hasn’t nailed down the requirements, it’s definitely premature. Reqirements change all the time, especially early on. What’s the point of optimizing something you’ll throw away later? Poor understanding of the problem. Optimizing will make the problem even harder to understand.

Optimized code is usually harder to understand. There are other time management related issues like not working on more critical issues and not anticipating potential software changes. The trick is to figure out the best time to optimize, then do so.

I’ve compiled a small list of things I’ve learned over the years. Here are two:

Avoid run-on logic. For example, if your code includes some kind of identifier, it’ll often look like this:

def check_code(var):
if var == 123 or var == 456 or var == 789 or var == 111 or var == 222 or var == 333 or var == “abc” or var == “def” or var == “ghi” or var == “ sif” or var == “at” or var == “nye” or var == “dis”:
return True

It may not seem like much here but in the real world, I’ve seen hundreds of identifiers like this in one function. It’ll have a lot of “and” and “not” and other operators.

Sometimes they’ll have several functions because the new engineer doesn’t want to mess with the previous engineer’s work. It’s hard to read a wall of text like this. Think program code, gift code, etc.

Here is the best practice:

company_code = [123, 456, 789, 111, 222, 333, “abc”, “def”, “ghi”, “sif”, “at”, “nye”, “dis”]

You can even do this (you might have to depending on your language choice):

int_company_code = [123, 456, 789, 111, 222, 333]

str_company_code = [“abc”, “def”, “ghi”, “sif”, “at”, “nye”, “dis”]

You might even improve some complexity but at the very least, you’ve improved readability.

On the topic of complexity, this is tricky to work with. Academia will give you an algorithm that is really slow and then teach you how to optimize it. This optimized algorithm runs at some ideal speed or uses up the least possible amount of memory. And while you’re learning, you’ll find it deals with tasks like sorting cards or searching for a simple string.

<img src="https://nyedis.com/wp-content/uploads/2023/12/database.jpg" />

I wish it was that simple. The problems in real world are hard. There are a lot of moving parts and problems are never straightforward. Some complexity is expected and that’s okay.

Sometimes your team might use a tool that checks for complexity. They might try to reduce the complexity, but in doing so, they could make their code harder to read or inadvertently introduce new bugs. Or worse, if it was never properly tested, you now don’t know if the newly optimized code work as intended.

One easy optimization is to find repeating code and put it into a function. It happens so often because different engineers will work on different part of the software but will need the same components. Components like validation logic or database connection code or UI components. There are so much more: configuration data, error handling, formatting, etc.

For example, if you see something like this repeating:

if code == 123 or code == “abc”:
return True

Feel free to put that into a function (or a module) and then replace everything with the function.

Sifer Aseph

Cybersecurity Engineer @ Nyedis
