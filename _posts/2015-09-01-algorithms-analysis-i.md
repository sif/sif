---
layout: post
title: "Algorithms Analysis I"
categories: algorithms
tags: algorithms algorithm_analysis analysis logarithmic_cost_measurement asymptotic_analysis
---

* TOC
{:toc}

> "Science is what we understand well enough to explain to a computer. Art is everything else we do."
> Donald Knuth

MIT Introduction To Algorithms
Algorithmic Thinking, Peak Finding
Models of Computation, Document Distance
Insertion Sort, Merge Sort
Heaps and Heap Sort
Binary Search Trees, BST Sort
AVL Trees, AVL Sort
Counting Sort, Radix Sort, Lower Bounds for Sorting
Hashing with Chaining
Table Doubling, Karp-Rabin
Open Addressing, Cryptographic Hashing
Integer Arithmetic, Karatsuba Multiplication
Square Roots, Newton's Method
Breadth-First Search (BFS)
Depth-First Search (DFS), Topological Sort
Single-Source Shortest Paths Problem
Dijkstra
Bellman-Ford
Speeding up Dijkstra
Dynamic Programming I: Fibonacci, Shortest Paths
Dynamic Programming II: Text Justification, Blackjack
Dynamic Programming III: Parenthesization, Edit Distance, Knapsack
Dynamic Programming IV: Guitar Fingering, Tetris, Super Mario Bros.
Computational Complexity
Topics in Algorithms Research



Write out the algorithms step by step by hand



time analysis
space analysis



## Simple Definition

An algorithm must follow these to be called an algorithm:
1. produce a at least one output
2. operate on data
3. must terminate

## Stricter Definition

All classical algorithms must:
- Solve a well-defined problem
- Eventually terminate
- Be correct
- Perform well (performance typically measured in time & space)

## Correctness

An algorithm is correct if, for every input instance, it halts with the correct output.

But.. an incorrect algorithm can be useful if its error rate can be controlled.



## Cost Model

- Uniform Cost Model
- Logarithmic Cost Model

We typically count operation. We generally worry about best case, worst case and average case running time.



## Big-O

Any algorithm that runs in constant time, O(1), cannot be improved upon. 

There are no algorithms that run faster with bigger input

By definition, there are no algorithms that have negative Big-O complexity



## Run-time Analysis

- Worst case (represented by big-O and little-o, upper bound)
- Average case (represented by big-Theta and little-theta, tight bound)
- Best case (represented by big-Omega and little-omega, lower bound)

Focus on big-O and big-θ first

Behavior for growth is called asymptotic growth and understanding it is called asymptomtic analysis

Analysis typically ignore constants

**Order of growth**, fastest to slowest (n as input, time as output): O(1) < O(log n) < O(n) < O(n log n) < O(n^2) < O(n^3) < O(2^n) < O(n!) < O(n^n) 

- Binary search is generally logarithmic
- Linear search is generally linear
- Divide and conquer is generally nlog(n)
- Multiplication of N*N matrices is generally O(n^2)
- Traversal of 3d arrays is generally O(n^3)

Consider edge cases, corner cases

Loop invariant

Use induction to prove:

- base case
- induction case

repeated doubling / halving
O(log N) or O(2^n)

- T(n) = 5n + T(n/3)
- T(n/3) = 5n/3 + T(n/9) - T(n/9) = 5n/9 + T(n/27)
- T(n/27) = 5n/27 + T(n/81)
- T(n/81) = 5n/81 + T(n/243)
- T(n) = 5n + 5n/3 + 5n/9 + 5n/27 + 5n/81 + T(n/243)



## 

Invariant, quite literally, means something that does not change or vary.



Think about what you are proving; induction is good for proving something for natural numbers

Ideally, this means you must prove that an algorithm:

1. performance (time complexity)
2. efficiency (typically space complexity)
3. correctness
4. optimality



Induction Proof

1. Base Case
2. Induction Hypothesis
    1. Weak Induction
    2. Strong Induction
3. Inductive Step



## Space-time Analysis

"The "Space-Time Tradeoff" refers to the idea that, in computer science, it is often possible to improve the performance of an algorithm by using more memory, or vice versa."



## [Optimizations](https://www.afterlifesong.com/algorithms/2002/04/19/optimizations.html)

*"Can we do better?"*

## [Linear Programming](https://www.afterlifesong.com/algorithms/2002/04/19/optimizations.html)

## Algorithms Analysis Problems and Solutions


