---
layout: post
title: "LeetCode #1431 \"Kids With the Greatest Number of Candies\""
categories: leetcode
tags: leetcode easy
---

## Opening

Listed as easy, description:

Given the array candies and the integer extraCandies, where candies[i] represents the number of candies that the ith kid has.

For each kid check if there is a way to distribute extraCandiesamong the kids such that he or she can have the greatestnumber of candies among them. Notice that multiple kids can have the greatest number of candies.

Example 1:
Input: candies = [2,3,5,1,3], extraCandies = 3
Output: [true,true,true,false,true] 
Explanation: 
Kid 1 has 2 candies and if he or she receives all extra candies (3) will have 5 candies --- the greatest number of candies among the kids. 
Kid 2 has 3 candies and if he or she receives at least 2 extra candies will have the greatest number of candies among the kids. 
Kid 3 has 5 candies and this is already the greatest number of candies among the kids. 
Kid 4 has 1 candy and even if he or she receives all extra candies will only have 4 candies. 
Kid 5 has 3 candies and if he or she receives at least 2 extra candies will have the greatest number of candies among the kids.

Example 2:
Input: candies = [4,2,1,1,2], extraCandies = 1
Output: [true,false,false,false,false] 
Explanation: There is only 1 extra candy, therefore only kid 1 will have the greatest number of candies among the kids regardless of who takes the extra candy.

Example 3:
Input: candies = [12,1,12], extraCandies = 10
Output: [true,false,true]

Constraints:
2 <= candies.length <= 100
1 <= candies[i] <= 100
1 <= extraCandies <= 50

## Solution

The challenge is in the optimization. All you have to do is to keep track of the kid with the most amount of candies. Then add the extra candies to everybody else.

The kid with the most amount of candies is obviously always going to return true. You can do this in-place or use up some space for the answer. I chose the latter because it's easier to see.

First, find out the kid with the most candies from the get-go. That will be the max variable. Then for each kid, add the extra candies and see if it is greater than or equal to the max variable.

If it is greater than or equal to the max variable, it is true, otherwise it is false. You then return the answer and voila.

<code>class Solution:
    def kidsWithCandies(self, candies: List[int], extraCandies: int) -> List[bool]:
        ans = []
        most = max(candies)
        for num in candies:
            if num + extraCandies >= most:
                ans.append(True)
            else:
                ans.append(False)
                
        return ans</code>

Originally published at: [LeetCode #1431 "Kids With the Greatest Number of Candies"](https://medium.com/@cassandriel/leetcode-1431-kids-with-the-greatest-number-of-candies-91ab933672e8)
