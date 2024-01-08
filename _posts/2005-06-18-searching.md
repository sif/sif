---
layout: post
title: "Searching"
categories: algorithms
tags: algorithms BFS DFS A-star
---

* TOC
{:toc}

## Constraints

In an unsorted list, if you need to find an item, you can do no better than looking at each item one by one.



## Linear Search (Sequential Search)

Worst Case: 
Best Case: 
Average Case:

O(n)

```
test = [11, 22, 33, 44, 55, 66, 77, 88, 99, 111]

def linear_search(data, target):
    i = 0

    for number in data:
        i += 1
        if number == target:
            return i

    return None

print(linear_search(test, 33))
print(linear_search(test, 100))
```



## Binary Search

Worst Case: O(log n)
Best Case: O(1)
Average Case: O(log n)

Worst case space complexity: O(1)

relies on divide and conquer strataegy to find a value within an already-sorted collection

```
test = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

def iterative_binary_search(data, target):
    size_of_data = len(data)

    low = 0
    high = len(data) - 1
    mid = 0

    while low <= high:
        mid = high + low // 2

        if data[mid] < target:
            low = mid + 1
        elif data[mid] > target:
            high = mid - 1
        else:
            return mid

    return -1

print(iterative_binary_search(test, 5))
print(iterative_binary_search(test, 100))
```



## Breadth-First Search

Worst Case: 
Best Case: 
Average Case: 

An algorithm that searches a graph or tree

It starts by looking at every node on the same level, then moves to the next level
It often moves from left to right, this means that bottom-right most node will be looked at last

Optimal for searching when the structure is wider than it is deep

Uses a queue to store information about the object it traverses

Can be more memory intensive than DFS

Useful for when you know the element you are looking for is close by

Useful when you have multiple cores

BFS will find the shortest path



## Depth-First Search

Worst Case: 
Best Case: 
Average Case: 

An algorithm that searches a graph or tree

It traverses down a tree until it can go no further, then it comes back trying the right / next child of the nodes on a branch 

Uses a stack

Optimal for searching when the structure is deeper than it is wide

The use case depends

Useful for when you know the element is in one specific branch and you need to go furthest down possible

Useful when you need to see the whole tree

Generally, uses less memory than BFS

Can be implemented recursively



## Dijkstra's Algorithm

Worst Case: 
Best Case: 
Average Case:

Dijkstra's algorithm uses [priority queue](https://www.afterlifesong.com/data_structures/2006/07/03/queue.html



## A*

Worst Case: 
Best Case: 
Average Case: 


