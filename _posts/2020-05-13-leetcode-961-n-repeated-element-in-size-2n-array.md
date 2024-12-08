---
layout: post
title: "LeetCode #961 \"N-Repeated Element in Size 2N Array\""
categories: leetcode
tags: leetcode easy
---

## Opening

Easy

In a array A of size 2N, there are N+1 unique elements, and exactly one of these elements is repeated N times.

Return the element repeated N times.

Example 1:
Input: [1,2,3,3]
Output: 3

Example 2:
Input: [2,1,2,5,3,2]
Output: 2

Example 3:
Input: [5,1,5,2,5,3,5,4]
Output: 5

Note:
4 <= A.length <= 10000
0 <= A[i] < 10000
A.length is even

## Solution

There are a couple of approaches to this problem. What we have is a list of integers where there is at least one repeat of an integer in there. We want to find that repeated integer.

To help us along, we will write down a simple pseudocode.

<code>given a list of ints, grab a number
    if there is another copy of the number, return the number</code>

As usual, we go with Python to convert this pseudocode into something useful. You can use any language you're comfortable with.

<code>class Solution:
    def repeatedNTimes(self, A: List[int]) -> int:
        seen = {}
        for item in A:
            if item not in seen:
                seen[item] = 1
            else:
                seen[item] += 1
        most = max(seen, key=lambda i: seen[i])
        return most</code>

So, in order to "grab a number," we just have to loop through the given list and put it into a dictionary. We use this dictionary to tell us what we've seen.

First, we create the dictionary, then loop through A. If the number is not in the dictionary, put it in and assign a value of 1. That is, it's seen only once.

Now, this solution also solves another problem. After the loop, if there is another number that also repeats, then you want to give the one that gives you the most.

You use the max() function and run a lambda expression to give you the item with the most repeat. Originally, I was going to roll out my own max() function but this would make the solution longer than necessary.

Perhaps the only challenge is remembering how to use max() and lambda calls. If you forgot, just roll out your own max() where you find the biggest number.

Originally published at: [LeetCode #961 "N-Repeated Element in Size 2N Array"](https://medium.com/@cassandriel/leetcode-961-n-repeated-element-in-size-2n-array-589a89a334f1)
