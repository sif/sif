---
layout: post
title: "LeetCode #709 \"To Lower Case\""
categories: leetcode
tags: leetcode easy
---

## Opening

Implement function ToLowerCase() that has a string parameter str, and returns the same string in lowercase.

Example 1:
Input: "Hello"
Output: "hello"

Example 2:
Input: "here"
Output: "here"

Example 3:
Input: "LOVELY"
Output: "lovely"

## Solution

There are different solutions to this depending on situation. For example, a solution to this as an interview question would be different than if you were to answer this for practicing.

The pseudocode is simple:

<code>loop through each letter in the word
    if capitalized, lower case it</code>
     
If this were an interview question, interviewer is likely going to want an ASCII solution. You just have to memorize or hopefully be able to ask for what the ASCII range is for lower and upper case letters.

This is what it could look like in Python:

<code>class Solution:
    def toLowerCase(self, str: str) -> str:
        newWord = ''
        
        for letter in word:
            if 65 <= ord(letter) <= 91:
                newWord += chr(ord(letter) + 32)
            else:
                newWord += letter
        return newWord</code>
        
If this is for personal practice, you could just use a one-liner:

<code>class Solution:
    def toLowerCase(self, str: str) -> str:
        return str.lower()</code>

Once you have the chr() and ord() function setup for the ASCII range, you simply run the loop and you will get your answer. For the personal solution, you simply just run the lower() string method and you will get your answer.

Originally published at: [LeetCode #709 "To Lower Case"](https://medium.com/@cassandriel/leetcode-709-to-lower-case-69d91b05a4a)
