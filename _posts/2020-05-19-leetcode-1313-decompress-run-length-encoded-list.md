---
layout: post
title: "LeetCode #1313 \"Decompress Run-Length Encoded List\""
categories: leetcode
tags: leetcode easy
---

## Opening

Easy

We are given a list nums of integers representing a list compressed with run-length encoding.

Consider each adjacent pair of elements [freq, val] = [nums[2*i], nums[2*i+1]] (with i >= 0). For each such pair, there are freq elements with value val concatenated in a sublist. Concatenate all the sublists from left to right to generate the decompressed list.

Return the decompressed list.

Example 1:
Input: nums = [1,2,3,4]
Output: [2,4,4,4]
Explanation: The first pair [1,2] means we have freq = 1 and val = 2 so we generate the array [2].
The second pair [3,4] means we have freq = 3 and val = 4 so we generate [4,4,4].
At the end the concatenation [2] + [4,4,4] is [2,4,4,4].

Example 2:
Input: nums = [1,1,2,3]
Output: [1,3,3]

Constraints:
2 <= nums.length <= 100
nums.length % 2 == 0
1 <= nums[i] <= 100

## Solution

There is a list of integers and you have to expand them. It’s a test on loop understanding.

<code>for every two items
    expand the item based on the frequency</code>

In Python, it may look something like:

<code>class Solution:
    def decompressRLElist(self, nums: List[int]) -> List[int]:
        decompressed = []
        
        for i in range(0, len(nums)-1, 2):
            decompressed = decompressed + nums[i] * [nums[i+1]]
    
        return decompressed</code>
        
Start off with an empty decompressed list. For every pair, decompress, then append the number that expanded based on frequency to the list in that order.

Don’t use append, it would actually just multiply the number. By doing what I did here, you would multiply the number as a list object by the frequency.

Originally published at: [LeetCode #1313 “Decompress Run-Length Encoded List”](https://medium.com/@cassandriel/leetcode-1313-decompress-run-length-encoded-list-dd7e269eabc3)
