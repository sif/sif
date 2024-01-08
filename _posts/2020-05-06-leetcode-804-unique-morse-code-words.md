---
layout: post
title: "LeetCode #804 \"Unique Morse Code Words\""
categories: leetcode
tags: leetcode easy
---

## Opening

Easy

International Morse Code defines a standard encoding where each letter is mapped to a series of dots and dashes, as follows: "a" maps to ".-", "b"maps to "-...", "c" maps to "-.-.", and so on.

For convenience, the full table for the 26 letters of the English alphabet is given below:

<code>[".-","-...","-.-.","-..",".","..-.","--.","....","..",".---","-.-",".-..","--","-.","---",".--.","--.-",".-.","...","-","..-","...-",".--","-..-","-.--","--.."]</code>

Now, given a list of words, each word can be written as a concatenation of the Morse code of each letter. For example, "cba" can be written as "-.-.. - …", (which is the concatenation "-.-." + "-…" + ".-"). We'll call such a concatenation, the transformation of a word.

Return the number of different transformations among all words we have.

Example:
Input: words = ["gin", "zen", "gig", "msg"]
Output: 2
Explanation: 
The transformation of each word is:
"gin" -> "--...-."
"zen" -> "--...-."
"gig" -> "--...--."
"msg" -> "--...--."
There are 2 different transformations, "--...-." and "--...--.".

Note:
The length of words will be at most 100.
Each words[i] will have length in range [1, 12].
words[i] will only consist of lowercase letters.

## Solution

You are given two things actually. On top of the input list, you are given the conversion dictionary. This will allow you to convert each letter to Morse code.

At the top of your file, you should put something like this:

<code>morse_table = [".-","-...","-.-.","-..",".","..-.","--.","....","..",".---","-.-",".-..","--","-.","---",".--.","--.-",".-.","...","-","..-","...-",".--","-..-","-.--","--.."]</code>

This way, your code can reference it. In some languages, you could even make this a constant as you're unlikely to change this. Our pseudocode could look something like this:

<code>given the morse table
given the words, for each word
    convert each letter in the word to morse
    put the morse into a dictionary
return dictionary count</code>

In Python, it might look like this:

<code>class Solution:
    def uniqueMorseRepresentations(self, words: List[str]) -> int:
        table_count = {}
        morse = ""
        alphabet_table = []
        for num in range(97, 123):
            alphabet_table.append(chr(num))
        for word in words:
            for letter in word:
                morse += morse_table[alphabet_table.index(letter)]
            if morse not in table_count:
                table_count[morse] = 1
            else:
                table_count[morse] += 1
            morse = ""
        return len(table_count)</code>
        
First, you create a table for where you'll put the morse code after each loop. Then construct an empty string for morse code use.

Then, to help make the morse table useful, you will need to create an alphabet table. It is possible that you won't have this memorized. I know I don't.

Ask for the ASCII table or the values for lower case alphabets. It's 97 to 123 for lower case (and 65 to 90 for upper case).

If for some reason, you can't generate this, here you go:

<code>['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']</code>

Using the chr() function, you will get a character from an integer. For each letter in each word, find the index of the alphabet at the morse table, and construct a morse out of it.

Stick the morse code into the table and if it already exists, just increment it. Then reset the morse code.

Once this is complete, just return the length of the table and you will have your answer.

Originally published at: [LeetCode #804 "Unique Morse Code Words"](https://medium.com/@cassandriel/leetcode-804-unique-morse-code-words-60dd7b29a863)
