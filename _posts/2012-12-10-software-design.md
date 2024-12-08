---
layout: post
title: "Software Design"
categories: software_engineering
tags: software_engineering microservices design_pattern
---

* TOC
{:toc}

## Design Principles

- KISS, keep it simple stupid
- DRY, don’t repeat yourself
- SOLID, single responsibility principle, open-closed principle, Liskov substitution principle, interface segregation principle, dependency inversion principle
- YAGNI, you ain’t gonna need it



## Design Patterns

Circuit breaker



Gang of Four
Erich Gamma, Richard Helm, Ralph Johnson, John Vlissides

- Creational
  - Singleton
  - Abstract Factory
  - Prototype
  - Builder
  - Factory Method

- Structural
  - Adapter
  - Bridge
  - Decorator
  - Composite
  - Facade
  - Flyweight
  - Proxy

- Behavior
  - Template Method
  - Mediator
  - Observer
  - Chain of Responsibility
  - Command
  - Interpreter
  - Iterator
  - Memento
  - State
  - Strategy
  - Visitor

> "When I see patterns in my programs, I consider it a sign of trouble. The shape of a program should reflect only the problem it needs to solve. Any other regularity in the code is a sign, to me at least, that I'm using abstractions that aren't powerful enough-- often that I'm generating by hand the expansions of some macro that I need to write."
> Paul Graham

"Peter Norvig demonstrates that 16 out of the 23 patterns in Design Patterns are simplified or eliminated by language features in Lisp or Dylan."



A proven solution or best practice to a common problem



## Service-Oriented Architecture



### Microservice

Microservices allows you to break your app into smaller parts that communicate with each other
This makes it simpler to scale the application based on traffic and provides separation of concerns so that you can work on one part of the app at a time


