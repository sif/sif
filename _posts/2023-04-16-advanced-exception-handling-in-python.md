---
layout: post
title: "Advanced Exception Handling in Python"
categories: python
tags: python exception_handling
---

At work, there was a push to do more testing in code. Under looming deadline, a lot of people write code just to get it out there. Problem is, it works until it doesn't. Resources are tight so they'll move on to the next task.

I'd like to see more exception handling. Exception handling lets software run and fail gracefully. It makes it easier to debug and maintain.

A basic one looks something like this:
 
```
try:
    x = int(input("Enter a numerator: "))
    y = int(input("Enter a denominator: "))
    result = x / y
    print(f"{x} divided by {y} is {result}.")
except ZeroDivisionError:
    print("Error:\nDivision by zero is not allowed.")
except ValueError:
    print("Error:\nPlease enter a valid number.")
```

It works well in simple use cases. You get two numbers and divide them. They fail if the user inputs anything other than numbers or a zero in the denominator.

What if I told you that you can do better?

```
# Defining a custom exception error
class InvalidNumberError(ValueError):
    def __init__(self, message):
        super().__init__(message)

# Defining a division function
def divide(x, y):
    if not isinstance(x, (int, float)) or not isinstance(y, (int, float)):
        raise InvalidNumberError("Please enter a valid number.")
    if y == 0:
        raise ZeroDivisionError("Division by zero is not allowed.")
    return x / y

try:
    x = input("Enter a numerator: ")
    y = input("Enter a denominator: ")
    result = divide(x, y)
    print(f"{x} divided by {y} is {result}.")
except (InvalidNumberError, ZeroDivisionError) as e:
    print(f"Error:\n{e}")
```

Try running these code on your own. You might wonder why I did something like this if it does exactly the same thing. Because notice how much more control I have over this. I can now define my own exception classes beyond the built-in ones.

If it's hard to visualize how this is an important, imagine you're at a bank. You'll have services that cannot fail. You will write better code when you think in terms of how your software can fail. Simple `try` and `except` just aren't enough. You need to be able to be able to catch all possible error scenarios. 

By doing this, you will be able to build more secure software.

It probably need not be said since it's relatively old news but I'll put it here anyway. Going forward, when I write about Python, I'm writing about Python 3. Python 2's EOL was in January 1, 2020.
