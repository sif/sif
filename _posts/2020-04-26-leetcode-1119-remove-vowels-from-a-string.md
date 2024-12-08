---
layout: post
title: "LeetCode #1119 \"Remove Vowels from a String\""
categories: leetcode
tags: leetcode easy
---

## Opening

This is marked as an easy problem. It is also a locked problem. The gist of it is that it involves removing vowels from strings.

## Solution

As usual, you need to think about what you are asked to do and what you are given. You are given a string. You need to remove the vowels from the string.

This problem defines a vowel as : 'a', 'e', 'i', 'o', 'u'

Let's make up an example. Say you are given a string:

<code>sentence = "The urgent care center was flooded with patients after the news of a new deadly virus was made public."</code>

You want to remove all of the vowels and return the result after doing so.

One way is to brute force, checking each character.

<code>for each character in a string
    if it's a vowel
        remove it</code>
        
In Python, it might look something like this:

<code>class Solution:
    def removeVowels(self, S: str) -> str:
        vowels = ['a', 'e', 'i', 'o', 'u']
        new_string = ""
        for letter in range(len(S)):
            if S[letter] not in vowels:
                new_string += S[letter]
        return new_string</code>
        
First we define the list of vowels and set an empty string that we can write to. We loop through the string by index of letter. For each letter, if the letter is not in the vowels list, append to the new string. After all this, return the new string.

It's O(n * 5) in runtime because for each character it runs through, it has to run through the vowels list.

We probably can't do better because no matter what you do, you have to check each character to be sure. You could try to use regular expression:

<code>import re
class Solution:
    def removeVowels(self, S: str) -> str:
        return re.sub('[aeiou]', '', S)</code>

But regular expression is notoriously unreliable.

There is also a replace or join function but you still have to iterate through every character. You also have to be careful in case you forget how to use replace or join.

So, if you forget, don't risk it and fall back to doing it manually since you aren't allowed to look it up during white board. If you sense your interviewer is tolerant, ask for a reminder on how to use replace or join.

Originally published at: [LeetCode #1119 "Remove Vowels from a String"](https://medium.com/@cassandriel/leetcode-1119-remove-vowels-from-a-string-a1ff5db32d37)
