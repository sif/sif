---
layout: post
title: "LeetCode #1365 \"How Many Numbers Are Smaller Than the Current Number\""
categories: leetcode
tags: leetcode easy
---

## Opening

This is listed as an easy problem. This is their description:

Given the array nums, for each nums[i] find out how many numbers in the array are smaller than it. That is, for each nums[i] you have to count the number of valid j's such that j != i and nums[j] < nums[i].

Return the answer in an array.

Example 1:
Input: nums = [8,1,2,2,3]
Output: [4,0,1,1,3]
Explanation: 
For nums[0]=8 there exist four smaller numbers than it (1, 2, 2 and 3). 
For nums[1]=1 does not exist any smaller number than it.
For nums[2]=2 there exist one smaller number than it (1). 
For nums[3]=2 there exist one smaller number than it (1). 
For nums[4]=3 there exist three smaller numbers than it (1, 2 and 2).

Example 2:
Input: nums = [6,5,4,8]
Output: [2,1,0,3]

Example 3:
Input: nums = [7,7,7,7]
Output: [0,0,0,0]

Constraints:
2 <= nums.length <= 500
0 <= nums[i] <= 100

## Solution

First, you want to find out what you are being asked to do and what you are given. I don't think the constraint helps too much.

nums.length tells you how many items there are in nums. You will have between 2 and 500 numbers. These are small quantities.

nums[i] tells you the number at that index i. The number will not be greater than 100. These are small numbers.

Okay, for each number, we are asked to figure out how many numbers are less than that number in the list. There are a few ways to do this.

First, the pseudocode:

<code>for each number n
    for each number in the list smaller than n, increment a counter
        put the counter in a new list after all numbers have been compared with
return the list</code>

Now the pseudocode describes a brute force which could look something like this:

<code>from typing import List
class Solution:
    def smallerNumbersThanCurrent(self, nums: List[int]) -> List[int]:
        result = []
        for num in nums:
            count = 0
            for comp in nums:
                if num > comp:
                    count += 1
            result.append(count)
        return result</code>

First you intialize an empty list called result. Then you run a loop through nums, sticking each number in num. Starting count to 0, you run a comparison number looping again.

If the number is greater than the comparison number, increment the counter. After doing so, append the count to result and reset count to 0. This will be O(n²).

This should work given the constraint but it is slow. Remember when I said there are a few ways to solve this? The next solution I am going to introduce is a bit better but it's more complex.

What you can do is sort the number and get the result there. Simply sort nums, then at count downwards if the following number is smaller. This may not be clear so let me use one of the example.

<code># Input
nums = [6,5,4,8]
new_nums = sorted(nums, reverse=True)
new_nums # [8,6,5,4]
# Output
[3,2,1,0]</code>

The built-in sorted function by Python uses Timsort. It's a hybrid merge and insertion sort variant. The literature says this yields a O(n log(n)) worst case scenario in time complexity.

But wait, order matters! The correct answer is still: [2,1,0,3]

This solution involves hash table and enumeration. Of course, why wouldn't it? Here is a slightly different take to it.

<code>from typing import List 
class Solution:
    def smallerNumbersThanCurrent(self, nums: List[int]) -> List[int]:
        result = {}
        for i, n in enumerate(sorted(nums)):
            if n not in result:
                result[n] = i
                
        return [result[n] for n in nums]</code>
        
First you initialize an empty dictionary called result. In the loop, you will enumerate over the sorted list. This will allow you to assign an index to each number. For example, if we use the same example, we get:

<code>i  n
0  4
1  5
2  6
3  8</code>

If a number n is not in result, then stick it somewhere in the result hash table. The key will be n, the value will be i. When you call result, it should look like this: {4: 0, 5: 1, 6: 2, 8: 3}

The insight is the fact that you do not need to put in a number if it already exists in the hash table.

The return combines the insight I mentioned earlier and can be rewritten as:

<code>answer = []
for n in nums:
    answer.append(result[n])
return answer</code>

The newly rewritten code is a bit easier to read as it do away with the vagueness that is just a listed result[n]. It says, initiate a new list called answer.

Then, for each number in nums, append to answer according to the number we see in result.

We have two container objects here.

A hash object, result: {4: 0, 5: 1, 6: 2, 8: 3}

A list object, nums: [6,5,4,8]

During the first iteration, take the first number 6, then append the value which is 2. Second iteration, take the next number 5, append 1. Do this for the rest of the numbers and you will have the answer.

As usual, the brute force mostly test if you can solve this problem manually while the more optimized version test if you know standard library function calls that may already solve your problem.

Originally published at: [LeetCode #1365 "How Many Numbers Are Smaller Than the Current Number"](https://medium.com/@cassandriel/leetcode-1365-how-many-numbers-are-smaller-than-the-current-number-1c8354ee5d84)
