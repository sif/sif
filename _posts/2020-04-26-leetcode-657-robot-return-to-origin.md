---
layout: post
title: "LeetCode #657 \"Robot Return to Origin\""
categories: leetcode
tags: leetcode easy
---

## Opening

This is marked as easy. The description:

There is a robot starting at position (0, 0), the origin, on a 2D plane. Given a sequence of its moves, judge if this robot ends up at (0, 0) after it completes its moves.

The move sequence is represented by a string, and the character moves[i] represents its ith move. Valid moves are R (right), L (left), U (up), and D (down). If the robot returns to the origin after it finishes all of its moves, return true. Otherwise, return false.

Note: The way that the robot is "facing" is irrelevant. "R" will always make the robot move to the right once, "L" will always make it move left, etc. Also, assume that the magnitude of the robot's movement is the same for each move.

Example 1:
Input: "UD"
Output: true 
Explanation: The robot moves up once, and then down once. All moves have the same magnitude, so it ended up at the origin where it started. Therefore, we return true.

Example 2:
Input: "LL"
Output: false
Explanation: The robot moves left twice. It ends up two "moves" to the left of the origin. We return false because it is not at the origin at the end of its moves.

## Solution

You really need to think about this one if you don't play with geometry often. There are many solutions to this one but if you arrive at a geometric insight, you only need one or two lines for this. If not, brute force works just as well.

Because of the given constraint, the movements always correspond to one another. That is, up corresponds with down and left corresponds with right. The up direction has no bearing on left or right and so on.

It is tempting to assign a value to each direction and that is what we will do. We are given a string input. We also expect a boolean output. We will also define the origin.

First, the naive solution in pseudocode.

<code>given the movement directions, move the robot in the following direction
    if at the end of the movement, the robot is at the origin, return true, otherwise return false</code>

The Python may look like this:

<code>class Solution:
    def judgeCircle(self, moves: str) -> bool:
        origin = {"X": 0, "Y": 0}
        for move in moves:
            if move == "U":
                origin["X"] += 1
            elif move == "D":
                origin["X"] -= 1
            elif move == "L":
                origin["Y"] -= 1
            elif move == "R":
                origin["Y"] += 1
        coordinateSum = 0
        
        for coordinate in origin:
            if origin[coordinate] != 0:
                coordinateSum += 1
        return coordinateSum == 0</code>
        
We first start the origin as X = 0 and Y = 0. Then we iterate through the moves. As we do so, we modify the origin according to the moves. We set a coordinate sum that we use to determine if it is equal to zero.

If this is so, we return true, else false. It is a long way to do this when you only need one insight. During the interview, you might be nervous and use this. This is better than nothing. What is better than this though, is if you had the insight.

One trick is to think about the outcome first. All the problem is asking is if the robot is back at the origin. You could use a hash table or a count, both hold similar idea on this approach.

In Python, there is a count method you could use. In another language like C++, you'll use an equivalent or write your own count method. If you were to write your own count method, it'd probably be O(4 * n) runtime as you have four direction multiplied by the amount of moves.

This is what using the count may look like:

<code>class Solution:
    def judgeCircle(self, moves: str) -> bool:
        return moves.count("U") == moves.count("D") and moves.count("L") == moves.count("R")</code>
        
This is what a one liner looks like (or two or three, depending on whether or not you count the class and def). The insight is after adding the corresponding moves, they should equal to 0 at X and Y.

If U and D are equal and L and R are equal, then it doesn't matter what the moves look like. Anyway, this is the ideal solution to write during the white board part of the interview.

Originally published at: [LeetCode #657 "Robot Return to Origin"](https://medium.com/@cassandriel/leetcode-657-robot-return-to-origin-41da363b2303)
