---
layout: post
title: "LeetCode #1221 \"Split a String in Balanced Strings\""
categories: leetcode
tags: leetcode easy
---

## Opening

Easy

Balanced strings are those who have equal quantity of 'L' and 'R' characters.

Given a balanced string s split it in the maximum amount of balanced strings.

Return the maximum amount of splitted balanced strings.

Example 1:
Input: s = "RLRRLLRLRL"
Output: 4
Explanation: s can be split into "RL", "RRLL", "RL", "RL", each substring contains same number of 'L' and 'R'.

Example 2:
Input: s = "RLLLLRRRLR"
Output: 3
Explanation: s can be split into "RL", "LLLRRR", "LR", each substring contains same number of 'L' and 'R'.

Example 3:
Input: s = "LLLLRRRR"
Output: 1
Explanation: s can be split into "LLLLRRRR".

Example 4:
Input: s = "RLRRRLLRLL"
Output: 2
Explanation: s can be split into "RL", "RRRLLRLL", since each substring contains an equal number of 'L' and 'R'

Constraints:
1 <= s.length <= 1000
s[i] = 'L' or 'R'

## Solution

This was a tough problem for me so this writeup is more for me. First, you are already given a balanced string and a useful constraint. The useful constraint is that it is either one item or another, in this case, 'L' or 'R'.

It would've been nice to know that anything that is balanced will always yield a 0. Whether it's count of objects, weight between objects, leafs, etc. I had not realized that insight. For this problem, in short:

<code>given a string, for every balanced string, increase the count by 1
There are a few ways to approach this. You'll want to balance out a simple example first. Say your string is "RL" or "LR."</code>

After you loop through either string, your count should be 1. You take one object and balance against the other object. When you do this, you're using extra space.

<code>R_count = 0
L_count = 0
count = 0
balancing_list = 0
for letter in s:
    balancing_list.append(letter)

    if (balancing_list.count("L") == balancing_list.count("R")):
        count += 1
        balancing_list.clear()</code>

As you can probably tell, the balancing_list variable is used as a balance. When the value of balancing_list is 0, it's a balanced string.

If you are challenged to not use extra space, then you just have to realize another insight (I did not, under the timeframe I gave myself).

The other insight you need is tracking. That is, you're keeping track.

<code>tracking = 0
count = 0
for letter in s:
    if letter == "L":
        tracking += 1
    else:
        tracking -= 1
    if tracking == 0:
        count += 1</code>

We are basically told that we'll never have a lone object as that would mean there is a contradiction in the title.

Because we know that we'll never have a lone object, we can add and subtract until we get a tracking that is equal to zero. Each iteration will involve in an operation until the end of a string.

You just need to return the final count. Thanks for reading!

Originally published at: [LeetCode #1221 "Split a String in Balanced Strings"](https://medium.com/@cassandriel/leetcode-1221-split-a-string-in-balanced-strings-4c7299f8ad9a)
