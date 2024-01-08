---
layout: post
title: "Hash Table"
categories: data_structures
tags: data_structures hash_table hash_map
---

* TOC
{:toc}

## Runtime Complexity

lookup 
append 
insert 
delete 



## Space Complexity



## Hash Map

Hash table stores data with key-value pair

- Uses hash function to store data and it is typically not in order
- A hash table is typically called by a key and returns a unique value
- Can be implemented with associative arrays or binary search trees
- One challenge of designing a hash table is avoiding collision; one way to avoid collision is to have an array of said possible collision
- key = index hash(key) % array_length
- The key formula is to prevent collision



## Hash Function

A hash function accepts a key and returns an output unique only to that specific key known as hashing

This provides a one to one correspondence to map information

Hash functions return a unique address in memory for that data



## Collision

A hash collision is when a hash function returns the same output for two distinct inputs



### Separate Chaining


