---
layout: post
title: "LeetCode #1108 \"Defanging an IP Address\""
categories: leetcode
tags: leetcode easy
---

## Opening

This is listed as an easy problem. This is their description:
Given a valid (IPv4) IP address, return a defanged version of that IP address.
A defanged IP address replaces every period "." with "[.]".

Example 1:
Input: address = "1.1.1.1"
Output: "1[.]1[.]1[.]1"

Example 2:
Input: address = "255.100.50.0"
Output: "255[.]100[.]50[.]0"

Constraints:
The given address is a valid IPv4 address.

## Solution

After reading this, you'll want to ask yourself, what exactly am I asked to do? What am I given?

It is likely that the object given will be a string type. The constraint helps because it won't be something invalid like "255,100-50.0". It will always be in the "xxx.xxx.xxx.xxx" format.

The expected output is an address with defanged periods which looks like this: [.]

You are expected to replace all of the periods with the defanged period. No matter what happens, you'll have no choice but to iterate character by character and check.

Even if you were to use some standard library function like replace, it does just that, only in an "optimized way." You also have to consider some base cases and edge cases.

Since it's not given, you can make some assumptions. LeetCode don't always make it clear what kind of tests they will use but in the real world, it's safe to make these assumptions (or ask). For example, if it's an empty string, you can just return an empty string without doing anything else.

Here is the pseudocode:

<code>loop through each character in a string
    if the character is a period, replace with [.]
return the new address</code>

In Python, it could look something like this:

<code>class Solution:
    def defangIPaddr(self, address: str) -> str:
        defanged_address = ''
        for character in address:
            if character != '.':
                defanged_address += character
            else:
                defanged_address += "[.]"
    return defanged_address</code>
    
Because this is done in one pass, it should be O(n) runtime, with n being characters in the string. Here is a slightly better version:

<code>class Solution:
    def defangIPaddr(self, address: str) -> str:
        defanged_ip = address.replace(address[address.find('.')], "[.]")
return defanged_ip</code>

The only problem is that this hides a lot from you. You pass in the address and what you want to replace and out comes a magically new string.

The trick is knowing what the interviewer wants. There are risks either way. If you provide the brute force solution because you want to show you know how to do this step by step, it's possible they'll think you only know how to brute force.

But if you use the better or a typically optimized solution, they'll think you've seen the problem before or memorized the syntaxes. I've been hit with both kinds of interviewers before.

If you ask, they can get impatience with you. The best thing to do depends on what is happening during the interview. If you're running out of time because this is your second problem or something, then go with an optimized solution.

If you have time and it's your only one, you can explain to them "I have two solutions for this, one using brute force, the other is an optimized form. Would you like me to go through each one?" Usually, they'll tell you what they want.

Conclusion? This is largely a string problem. This tests whether you understand basic looping and maybe know some standard library function.

Originally published at: [LeetCode #1108 “Defanging an IP Address”](https://medium.com/@cassandriel/leetcode-1108-defanging-an-ip-address-f1618a567763)
