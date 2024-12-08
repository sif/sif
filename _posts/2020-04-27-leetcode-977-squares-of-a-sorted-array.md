---
layout: post
title: "LeetCode #977 \"Squares of a Sorted Array\""
categories: leetcode
tags: leetcode easy
---

## Opening

This is marked as easy and the description says:

Given an array of integers A sorted in non-decreasing order, return an array of the squares of each number, also in sorted non-decreasing order.

Example 1:
Input: [-4,-1,0,3,10]
Output: [0,1,9,16,100]

Example 2:
Input: [-7,-3,2,3,11]
Output: [4,9,9,49,121]

Note:
1 <= A.length <= 10000
-10000 <= A[i] <= 10000
A is sorted in non-decreasing order.

## Solution

The problem gives us one list input and expect a list output. The type of items in both lists are integers. For the most part, it's straight forward.

Because of this, during the interview, you might be expected to give something flashy, no matter what language you choose.

First, the pseudocode for a quick solution:

<code>square all of the numbers in the array
sort the numbers in the array
return the array</code>

In Python, it may look something like:

<code>class Solution:
    def sortedSquares(self, A: List[int]) -> List[int]:
        B = []
        for number in A:
            B.append(number * number)
        return sorted(B)</code>
        
We'll first allocate some space for a new list. Then we iterate through the given input A and append to the new list as we square each number in A. After that, we return the new list sorted.

This is O(n * m), n for numbers in A and m for the operations. This is especially so if you rolled your own sort. We could improve this in one go. It may look something like:

<code>class Solution:
    def sortedSquares(self, A: List[int]) -> List[int]:
        return sorted(number * number for number in A)</code>

This is "flashy" and probably ideal in an interview. It's not too risky and allows you to move onto another problem. If you do this from the get-go, this is a O(n log(n)) where n is elements in A.

If you have time and you want to give it your all, you could use a double pointer. One pointer would handle positive numbers and the other negative numbers. Then we merge the two. This is a sort of mini-divide and conquer algorithm.

<code>class Solution(object):
    def sortedSquares(self, A: List[int]) -> List[int]:
        solution = []
        length_of_A = len(A)
        positive = 0
        while positive < length_of_A and A[positive] < 0:
            positive += 1
        negative = positive - 1
        while 0 <= negative and positive < length_of_A:
            if A[negative] * A[negative] < A[positive] * A[positive]:
                solution.append(A[negative] * A[negative])
                negative -= 1
            else:
                solution.append(A[positive] * A[positive])
                positive += 1
        while negative >= 0:
            solution.append(A[negative] * A[negative])
            negative -= 1
        while positive < length_of_A:
            solution.append(A[positive] * A[positive])
            positive += 1
        return solution</code>

First, we allocate some memory for a list to merge to. To divide A, we need to find the length of A. Let's make up an example. How about this:

<code>A = [-2, -1, 1, 2, 3]</code>

As I noted earlier, we will need one pointer for positive numbers and another for negative. They are aptly named positive and negative. Positive starts at 0. So long as positive is less than 5 and the item at position of A at `positive` index is less than 0, we'll increment it.

Negative then is just one less positive. With this example, we should have positive at 2 at this point and negative at 1. This means the positive pointer starts at A[2] == 1 and negative pointer starts at A[1] == -1.

The while loop will run from 0 to 1 and 2 to 4. If you square the item at the positive and negative index and the item at negative index is less than positive, then decrement the negative pointer and append to the solution list.

Otherwise, increment the positive pointer and append to the solution list the squared number. This will give you [1, 1, 4, 4]. The last two set of while loops finishes up the program. In this case, it will run the second while loop as 4 is < 5.

This would give us O(n) which is fastest solution we can come up with for this problem. It's a bit risky because you have much more to write and if it doesn't compile, you look bad. If it's your only problem, you could give this a shot.

Originally published at: [LeetCode #977 "Squares of a Sorted Array"](https://medium.com/@cassandriel/leetcode-977-squares-of-a-sorted-array-bae104b90ac2)
