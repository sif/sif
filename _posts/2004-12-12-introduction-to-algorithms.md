---
layout: post
title: "Introduction to Algorithms"
categories: books
tags: books CLRS
---

Cormen Leiserson Rivest Stein (CLRS)

It is a good idea to just focus on reading, skipping problems. Then coming back to doing problems. Haven't done it since page 40.

2.3-7

$$ \lg{n} = \log_2{n} $$

## Foundations

### The Role of Algorithms in Computing

"1.1-1 Give a real-world example that requires sorting or a real-world example that requires computing a convex hull." 

Sorting - somewhat tautological, but sorting by price
Convex hull - "Imagine walking around a garden. If you only turn right (and never turn left) and still end up where you started, you would have traced out a convex hull." (https://www.reddit.com/r/compsci/comments/20j8rj/eli_5_convex_hulls/), self-driving cars

"1.1-2 Other than speed, what other measures of efficiency might one use in a real-world setting?" 

Power
Memory

"1.1-3 Select a data structure that you have seen previously, and discuss its strengths and limitations." 

Array - which makes it easy to access but size is fixed

"1.1-4 How are the shortest-path and traveling-salesman problems given above similar? How are they different?"

Similar in that they are both graphs and focus on minimizing cost
Different in that shortest-path is between 2 points and in class P while TSP is between all points and in class NP

"1.1-5 Come up with a real-world problem in which only the best solution will do. Then come up with one in which a solution that is “approximately” the best is good enough."

Only the best will do - medical, self-driving vehicles
Approximation is fine - games

"Why are NP-complete problems interesting? 

First, although no efficient algorithm for an NP-complete problem has ever been found, nobody has ever proven that an efficient algorithm for one cannot exist. In other words, no one knows whether or not efficient algorithms exist for NP-complete problems. 

Second, the set of NP-complete problems has the remarkable property that if an efficient algorithm exists for any one of them, then efficient algorithms exist for all of them. This relationship among the NP-complete problems makes the lack of efficient solutions all the more tantalizing.

Third, several NP-complete problems are similar, but not identical, to problems for which we do know of efficient algorithms. Computer scientists are intrigued by how a small change to the problem statement can cause a big change to the efficiency of the best known algorithm. 
                    
You should know about NP-complete problems because some of them arise surprisingly often in real applications. If you are called upon to produce an efficient algorithm for an NP-complete problem, you are likely to spend a lot of time in a fruitless search. If you can show that the problem is NP-complete, you can instead spend your time developing an efficient algorithm that gives a good, but not the best possible, solution."

"1.2-1 Give an example of an application that requires algorithmic content at the application level, and discuss the function of the algorithms involved." 

File Explorer - applying a sorting algorithm
Games - applying a clipping algorithm

"1.2-2 Suppose we are comparing implementations of insertion sort and merge sort on the same machine. For inputs of size n, insertion sort runs in $$ 8n^2 $$ steps, while merge sort runs in 64n lg n steps. For which values of n does insertion sort beat merge sort?”

For insertion sort to beat merge sort for input size of n, $$ 8n^2 $$ must be less than 64n lg n

$$ 8n^2 < 64n \lg{n} $$
$$ n < 8 \lg{n} $$
$$ \frac{n}{8} < \lg{n} $$
$$ 2^\frac{n}{8} < n $$

"1.2-3 What is the smallest value of n such that an algorithm whose running time is $$ 100n^2 $$ runs faster than an algorithm whose running time is $$ 2^n $$ on the same machine?"

$$ 100n^2 $$ must be smaller than $$ 2^n $$
Plug in numbers from n=1 to n=20
n=15 is when $$ 100n^2 $$ starts to run faster than $$ 2^n $$

"1-1 Comparison of running times 

For each function f(n) and time t in the following table, determine the largest size n of a problem that can be solved in time t, assuming that the algorithm to solve the problem takes f (n) microseconds."

In f(n) microseconds, largest size of problem that can be solved is n. To find the largest size of problem that can be solved in time t, we need to solve the following equation for n

f(n)=t in microseconds

For $$ n=10^6 $$

lg n = $$ 2^{10^6} $$
$$ \sqrt{n} $$
n = $$ 10^6 $$
n lg n
$$ n^2 $$
$$ n^3 $$
$$ 2^n $$
n!

https://www.reddit.com/r/algorithms/comments/38ppb1/understanding_introduction_to_algorithms_problem/

<img src="https://github.com/sif/sif/raw/main/files/post_files/clrs 1-1.png" />

## Getting Started

### Insertion Sort



### Merge Sort


