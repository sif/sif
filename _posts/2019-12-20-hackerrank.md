---
layout: post
title: "HackerRank"
categories: competitive_programming
tags: hackerrank
---

* TOC
{:toc}

## Python

### Say "Hello, World!" With Python

```python3
print("Hello, World!")
```

### Python If-Else

```python2
if __name__ == '__main__':
    n = int(raw_input().strip())

    if n % 2 != 0:
        print("Weird")
    if n % 2 == 0 and (2 <= n <= 5):
        print("Not Weird")
    if n % 2 == 0 and (6 <= n <= 20):
        print("Weird")
    if n % 2 == 0 and n > 20:
        print("Not Weird")
```

### Arithmetic Operators

```python3
if __name__ == '__main__':
    a = int(input())
    b = int(input())

    print(a + b)
    print(a - b)
    print(a * b)
```

### Python: Division

```python3
if __name__ == '__main__':
    a = int(input())
    b = int(input())

    print(a // b)
    print(a / b)
```

### Loops

```python3
if __name__ == '__main__':
    n = int(input())
    i = 0

    for num in range(n):
        print(num * num)
```

### Print Function

```python3
if __name__ == '__main__':
    n = int(input())
    
    for i in range(n):
        print(i+1, end="")
```

### Write a function

```
def is_leap(year):
    leap = False
    
    if year % 400 == 0:
       leap = True
    elif year % 100 == 0:
        leap = False
    elif year % 4 == 0:
        leap = True
        
    return leap
```

### Find a string

```
def count_substring(string, sub_string):
    count = 0
    
    for letter in range(len(string)):
        if string[letter:].startswith(sub_string):
            count += 1

    return count

if __name__ == '__main__':
    string = input().strip()
    sub_string = input().strip()
    
    count = count_substring(string, sub_string)
    print(count)
```

###

```

```


