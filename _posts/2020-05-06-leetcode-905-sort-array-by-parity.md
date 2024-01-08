---
layout: post
title: "LeetCode #905 \"Sort Array By Parity\""
categories: leetcode
tags: leetcode easy
---

## Opening

Easy

Given an array A of non-negative integers, return an array consisting of all the even elements of A, followed by all the odd elements of A.

You may return any answer array that satisfies this condition.

Example 1:
Input: [3,1,2,4]
Output: [2,4,3,1]
The outputs [4,2,3,1], [2,4,1,3], and [4,2,1,3] would also be accepted.

Note:
1 <= A.length <= 5000
0 <= A[i] <= 5000

## Solution

This is one of those problems with multiple accepted solutions. That is, your solution can produce a slightly different variant to the solution and still be considered correct as long as it fits the bill.

You are given an input of a list of integers. Your output is a list of integers that's sorted by even numbers followed by odd numbers. Here is a pseudocode:

<code>for number in a list
    if number is even, put it in the first half of the list
    else if number is odd, put it in the second half of the list</code>
    
In Python, it might look something like:

<code>class Solution:
    def sortArrayByParity(self, A: List[int]) -> List[int]:
        odd = []
        even = []
        for item in A:
            if (item % 2 == 0):
                even.append(item)
            else:
                odd.append(item)
        newList = even + odd
        return newList</code>

I solved this in a way that you could try to optimize to make it more impressive for interviews. This should be fine too if you don't have a lot of time.

First you create two empty lists. One empty list for even numbers and another for odd numbers.

You then loop through the given input and perform modulus operations. You put the numbers in their respective bin. Once there is no more numbers, you combine the list, even first then odd and return that.

This is O(n). No matter what happens, you have to check each numbers to get to each one.

You can try to make this Pythonic and go with list comprehension.

<code>class Solution:
    def sortArrayByParity(self, A: List[int]) -> List[int]:
        return ([item for item in A if item % 2 == 0] + [item for item in A if item % 2 == 1])</code>
        
Originally published at: [LeetCode #905 "Sort Array By Parity"](https://medium.com/@cassandriel/leetcode-905-sort-array-by-parity-8253fd10f556)
