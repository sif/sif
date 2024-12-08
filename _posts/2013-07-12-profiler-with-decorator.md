---
layout: post
title: "Profiler with Decorator"
categories: python
tags: python performance_profiling decorator
---

A decorator is a higher-order function that takes in another function as input and returns a new function. You can even apply multiple decorators to the same function. Decorators allow you to change the function's behavior without changing its code. It's a powerful technique borrowed from the functional programming world.

Let's say you have a function that adds two numbers and you want to know how long it took to execute:

```
import time

def adder(a, b):
    time.sleep(3)
    return a + b
    
result = adder(1, 2)
print(f"Result: {result}")
```

It includes a sleep() function to simulate the function taking time to execute. You can try running this on its own and see.

Now, this decorator will tell you how long it took:

```
def timer_decorator(func):
    def wrapper(*args, **kwargs):
        start_time = time.time()
        result = func(*args, **kwargs)
        end_time = time.time()
        print(f"{func.__name__} executed in {end_time - start_time:.10f} seconds")
        return result

    return wrapper

@timer_decorator
```

All you have to do is put this together and you will see it in action:

```
import time

def timer_decorator(func):
    def wrapper(*args, **kwargs):
        start_time = time.time()
        result = func(*args, **kwargs)
        end_time = time.time()
        print(f"{func.__name__} executed in {end_time - start_time:.10f} seconds")
        return result

    return wrapper

@timer_decorator
def adder(a, b):
    time.sleep(3)
    return a + b

result = adder(1, 2)
print(f"Result: {result}")
```
