---
layout: post
title: "Recursion and Iteration"
categories: programming
tags: programming
---

* TOC
{:toc}

## Power of two recursively

```python
def poweroftwo(n):
    if n == 0:
        return 1
    else:
        power = poweroftwo(n-1)
        return power * 2

print(poweroftwo(3))
```

## Power of two iteratively

```python
def poweroftwoit(n):
    i = 0
    power = 1
    while i < n:
        power *= 2
        i += 1
    return power

print(poweroftwoit(32))
```

## Decimal to binary recursively

```python
def decimal_to_binary(number):
    if number == 0:
        return 0
    else:
        return number % 2 + 10 * decimal_to_binary(number // 2)

print(decimal_to_binary(52))
```

## Decimal to binary iteratively

```python
def decimal_to_binary_it(number):
    remainder = ""
    while number != 0:
        remainder += str(number % 2)
        number = number // 2

    return remainder[::-1]

print(decimal_to_binary_it(52)) # 110100
```


