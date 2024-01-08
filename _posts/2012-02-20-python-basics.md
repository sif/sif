---
layout: post
title: "Python Basics"
categories: python
tags: python comprehension
---

* TOC
{:toc}

Haters say Python is "a slow language" or "a glue language", ignore them

Just tell them that Python programming is just: hsssssss hsssss...

<a href="https://www.reddit.com/r/ProgrammerHumor/comments/uwr32m/but_python_is_a_slug_and_c_is_lightning_fast/"><img src="https://github.com/sif/sif/raw/main/files/post_files/5ojrmcqagf191.jpg" /></a>

interpreted, high level, memory safe, general purpose, emphasizes code readability, dynamically typed, automatic garbage collection

passes by assignment

- File I/O
- Modules & Imports
- Regex
- Classes
- Strings
- Threads



## Variables

```python
exponential = 3 ** 2 # 9
remainder = 5 % 2 # 1
integer_division = 5 // 2 # 2
division = 5 / 2 # 2.5
multiplication = 2 * 2 # 4
minus = 2 - 2 # 0
addition = 2 + 2 # 4

an_integer = 5
a_floating_point = 5.0
a_string = "word"
a_raw_string = r"hel\nlo"

number = int("123")
binary_number = int("1111", 2)
```

```python3
def custom_parseInt(number, base=10):
    output = ""
    for character in number:
        if character.isdigit() or (base > 10 and ('a' <= character.lower() <= 'f')):
            output += character
            
    return int(output, base)

print(custom_parseInt("123abc", 10))
```

## Lists, Tuples, Dictionaries



### List

```python3
a_list_example = list()
```

### List Comprehension



### Tuple

```python3
a_tuple_example = (1, 2)
```



### Dictionary

```python3
a_dictionary = {}

a_dictionary["key"] = "value"
```



## Control Flow

```python
if example == "test example":
    print("this works")
else:
    print("this does not")

for 

while 

```



## Functions

```python
def name(entered):
    return entered

```

string operations

```python



```

reading and writing to the console


reading and writing to files


enumerate
chr
ord
lambda
getting individual digits with %



## Built-in Functions

`max(object, key=object.iterable)`

//slicing//[start:end:step]

print()

input()

str()

type()

range(start, stop, step)

* “for x in range(n):”

list.index(element, start, end)

assert

```
function randomRange(myMin, myMax) {
  return Math.floor(Math.random() * (myMax - myMin + 1) + myMin);
}
```

Code Explanation

- Math.random() generates our random number between 0 and approximately 0.9.
- Before multiplying it, it resolves the part between parenthesis (myMax - myMin + 1) because of the grouping operator ( ).
- The result of that multiplication is followed by adding myMin and then "rounded" to the largest integer less than or equal to it (eg: 9.9 would result in 9)

If the values were `myMin = 1`, `myMax= 10`, one result could be the following:

1. Math.random() = 0.8244326990411024
2. (myMax - myMin + 1) = 10 - 1 + 1 => 10
3. a * b = 8.244326990411024
4. c + myMin = 9.244326990411024
5. Math, floor (9.244326990411024) = 9



## Fun



```
>>> import this
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
```



Easter egg: Type "import antigravity" in the Python interpreter.


