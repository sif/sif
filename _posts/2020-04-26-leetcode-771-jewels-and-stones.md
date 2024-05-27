---
layout: post
title: "LeetCode #771 \"Jewels and Stones\""
categories: leetcode
tags: leetcode easy
---

## Opening

This is marked as easy. This is the description:

You're given strings J representing the types of stones that are jewels, and Srepresenting the stones you have. Each character in S is a type of stone you have. You want to know how many of the stones you have are also jewels.

The letters in J are guaranteed distinct, and all characters in J and S are letters. Letters are case sensitive, so "a" is considered a different type of stone from "A".

Example 1:
Input: J = "aA", S = "aAAbbbb"
Output: 3

Example 2:
Input: J = "z", S = "ZZ"
Output: 0

Note:
S and J will consist of letters and have length at most 50.
The characters in J are distinct.

## Solution

You're given two inputs. Both are strings. Your expected output is an integer.

The constraints are given in the Note section. S represents stones that you own while J represents stones that are jewels. There are at least two ways to solve this.

The first is, as always, brute force. First, pseudocode:

<code>for each letter in S
    if the letter is in J
        increment a counter</code>

In Python this might look something like:

<code>class Solution:
    def numJewelsInStones(self, J: str, S: str) -> int:
        jewel_counter = 0
        for stone in S:
            if stone in J:
                jewel_counter += 1
        return jewel_counter</code>

Because the constraint is only 50 in S and 50 in J, it is okay if you were to run this program a few times. It can be improved by using a hash table.

As it is now, it is O(n * m) runtime. The n and m are J and S, because they could be any size. For each S, you have to check every J.

Using hash table, you could improve the runtime to O(n + m). A hash table solution could look like this:

<code>class Solution:
    def numJewelsInStones(self, J: str, S: str) -> int:
        jewel_counter = 0
        jewel_table = set()
        for jewel in J:
            jewel_table.add(jewel)
        for stone in S:
            if stone in jewel_table:
                jewel_counter += 1
        return jewel_counter</code>

For each S, you only have to search for J. The search for J in a hash solution is faster than the J check in brute force.

If you remember how to use a hash object from the get go, a set is ideal. Start with this and you'll finish with an optimized solution.

Originally published at: [LeetCode #771 "Jewels and Stones"](https://medium.com/@cassandriel/leetcode-771-jewels-and-stones-1ebc53a1da56)
