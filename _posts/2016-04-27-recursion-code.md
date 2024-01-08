---
layout: post
title: "Recursion Code"
categories: programming
tags: programming
---

* TOC
{:toc}

## Internals of a recursion

```python
def first():
    second()
    print("first")

def second():
    third()
    print("second")

def third():
    print("third")

first()
```

## Factorial

```python
def factorial(n):
    if n == 0:
        return 1
    elif n == 1:
        return 1
    else:
        return n * factorial(n-1)
        
print(factorial(9))
```

## Fibonacci

```python
def fib(n):
    assert n > 0 and int(n) == n, "this is not a positive integer"
    if n == 0:
        return n
    elif n == 1:
        return n
    else:
        return fib(n-1) + fib(n-2)

print(fib(7))
```

## Sum of Digits

```python
def digit_sum(n):
    assert n >= 0 and int(n) == n, "this needs to be a positive integer"

    if n == 0:
        return 0
    else:
        return n % 10 + digit_sum(n//10)

print(digit_sum(555))
```

## Power

```python
def numpow(n, x):
    assert n >= 0 and int(n) == n, "the exponent has to be a positive integer for now"
    if x == 0:
        return 1
    else:
        return n * numpow(n, x-1)

print(numpow(4, 3))
```

## Euclidean GCD

```python
def gcd(x, y):
    assert int(a) == a and int(b) == b, "integers only"
    if x < 0:
        x = -1 * x
    if y < 0:
        y = -1 * y
    if y == 0:
        return x
    else:
        return gcd(y, x % y)

print(gcd(48, 18))
```

## Power (exercise)

```python
def power(base, exponent):
    if exponent == 0:
        return 1
    else:
        return base * power(base, exponent-1)

print(power(2, 0)) # 1
print(power(2, 4)) # 16
```


