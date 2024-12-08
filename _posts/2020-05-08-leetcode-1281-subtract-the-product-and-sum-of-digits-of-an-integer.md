---
layout: post
title: "LeetCode #1281 \"Subtract the Product and Sum of Digits of an Integer\""
categories: leetcode
tags: leetcode easy
---

## Opening

Easy

Given an integer number n, return the difference between the product of its digits and the sum of its digits.

Example 1:
Input: n = 234
Output: 15 
Explanation: 
Product of digits = 2 * 3 * 4 = 24 
Sum of digits = 2 + 3 + 4 = 9 
Result = 24 - 9 = 15

Example 2:
Input: n = 4421
Output: 21
Explanation: 
Product of digits = 4 * 4 * 2 * 1 = 32 
Sum of digits = 4 + 4 + 2 + 1 = 11 
Result = 32 - 11 = 21

Constraints:
1 <= n <= 10^5

## Solution

It's another one of those easy problems that often have a harder variants in another problem listing.

Here we are asked, given a number, to find the result after subtracting the product and sum of digits.

This problem can be easy or hard depending on language. High level languages like Python or R tend to have built-in functions, you can just call whereas low level languages like C or C++, you usually have to write your own calls.

Here is the pseudocode:

<code>given a number
    multiply each digit in the number
    sum each digit in the number
    the multiplied number subtract the summed number, return the result</code>

In Python, it may look something like this:

<code>class Solution:
    def subtractProductAndSum(self, n: int) -> int:
        product = 1
        sum = 0
        for digit in str(n):
            product *= int(digit)
            sum += int(digit)
        return product - sum</code>
        
Be careful not to make mistakes like product = 0. It's easy to forget about and some interviewer might dock points for tiny mistakes like that.

What this does is straightforward. You are to create two starting integers, the sum and product. For each digit in the number, multiply and sum and set to the starting integers.

After the loop finishes, return the result of product subtracting sum. This is O(n). Any other better solution will be variants of O(n). That is, not much better.

The other alternative which is probably a little faster and will work for other languages is using the modulus operator. You just have to figure out how to use % to get each digit.

After you do so, the idea is the same, apply the sum and product to each digit and subtract to get the result.
        
Originally published at: [LeetCode #1281 “Subtract the Product and Sum of Digits of an Integer”](https://medium.com/@cassandriel/leetcode-1281-subtract-the-product-and-sum-of-digits-of-an-integer-c7b79476a01)
