---
layout: post
title: "LeetCode #283 \"Moving Zeroes\""
categories: leetcode
tags: leetcode easy
---

## Opening

Easy

Given an array nums, write a function to move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Example:
Input: [0,1,0,3,12]
Output: [1,3,12,0,0]

Note:
You must do this in-place without making a copy of the array.
Minimize the total number of operations.

## Solution

You are given a list input and the problem expects a list output. Your job is to take all of the zeroes and put it at the end of the list. It's easy to overthink this one.

You have to do this in-place. You cannot make a copy of the array or else it would be too easy. You have to do this optimally too.

So, there is a very tiny trick to this. Doing in-place means you cannot make a copy of the array but you can make a temporary placeholder.

There are a couple of solutions to this. The first is simple swapping but you'd have to contend with the fact that it may not be optimal. You could also use two pointers but you risk it being long and making syntax mistakes.

First, the pseudocode:

<code>looping through the list
    if the number is a 0
        put the zero at the end of the list, do this until all zeroes are at end of list</code>

The quickest solution in Python in a scenario where you may not have enough time:

<code>class Solution:
    def moveZeroes(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        for number in nums:
            if number == 0:
                nums.remove(number)
                nums.append(0)</code>

This is O(n²) because you have to push the list down everytime you remove something. Two pointers is probably best:

<code>class Solution:
    def moveZeroes(self, nums: List[int]) -> None:
        index = 0
        for item in range(len(nums)):
            if nums[item] != 0:
                temp = nums[item]
                nums[item] = nums[index]
                nums[index] = temp
                index += 1</code>

This is a little unintuitive but it's O(n). Your first thought might be to take the 0 and swap until it's at the end of the list. This one is the opposite.

First, set the index to zero. Loop through the list. While the item is not a 0, swap it with the index. Then increment the index.

As long as your loop invariant is correct, the algorithm should be correct. In this case, it would be making sure that for all indices less than index, there is no zero.

For the visually inclined, simply put a print statement to track index and you should see the index for nonzero should be less than index for zeroes.

If you want to be more Pythonic, you could do this instead with the swaps:

<code>nums[item], nums[index] = nums[index], nums[item]</code>

One challenge about interviewing is you want to be optimized in your solution but also Pythonic and pretty. It's hard because of the time constraint and you can forget a lot while nervous.

Originally published at: [LeetCode #283 "Moving Zeroes"](https://medium.com/@cassandriel/leetcode-283-moving-zeroes-65fb388c96f3)
