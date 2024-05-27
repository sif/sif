---
layout: post
title: "Quantum Computing"
categories: quantum
tags: quantum
---

* TOC
{:toc}



## 



In regard to the discussion on quantum computers and optimization in supercomputers: A good algorithm is always better than a supercomputer. Unless it's a qc or it's your supercomputer.

> "If you take nothing else from this blog: quantum computers won't solve hard problems instantly by just trying all solutions in parallel."
> Shtetl-Optimized
> Scott Aaronson

Master linear algebra, probability theory



$$\vert a + bi \vert = \sqrt(a^2 + b^2)$$

$$\vert z \vert = \sqrt(z * z_{conjugate})$$

The \|complex numbers\| are best explained here: https://en.wikipedia.org/wiki/Absolute_value#Complex_numbers

In this case, it means modulus. When people say modulus, \|z\| for complex z, it’s the same thing as absolute value, or norm, or any other term to describe “length of a vector”

$$\vert 0>$$ and $$\vert 1>$$ are “directions” in the vector space

$$\vert 0> = (1, 0)$$

$$\vert 1> = (0, 1)$$

a\|0> + b\|1> is just (a, b)

that (a, b) lies in the unit circle means $$a^2 + b^2 = 1$$

but because this is complex unit circle, the requirement is $$\vert a \vert^2 + \vert b \vert^2 = 1$$ where \|a\| is the modulus of a complex number

0.7 \|0> + 0.3 \|1> = (0.7, 0), (0, 0.3) = .72 + .32 = 0.49 + 0.09 = 0.58, 0.58 is not part of the unit vector, thus does not represent a state in a QM state

A QM state is an element of the unit sphere. Unit sphere: $$x^2 + y^2 + z^2 = 1$$

Find the norm of the vector $$\vec{u} = (2, -2, 3, -4)$$.
Since $$\vec{u} \in \mathbb{R}^4$$, we will use the formula $$\vert \vert \vec{u} \vert \vert = \sqrt{u^{2}_{1}+u^{2}_{2}+u^{2}_{3}+u^{2}_{4}} = \sqrt{4+4+9+16} = \sqrt{33}.$$ So the norm of our vector $$\vec{u}$$ is the square root of 33.



- Use of quantum mechanical phenomenon to perform computation. Quantum computing is a subset of quantum information science. Quantum information science is based on the idea that information science depends on quantum effects in physics.
- Qubits, quantum bits, fundamental building block for quantum information processes

Quantum computers CANNOT solve the halting problem



quantum safe



## Quantum algorithms

Shor's algorithm

Grover's algorithm

quantum Fourier transform



## Quantum communication

quantum teleportation

superdense coding



## Quantum cryptography

quantum key distribution

quantum digital signatures

quantum money



## Quantum error correction



## Quantum simulation



## Quantum supremacy

"Quantum supremacy is the point at which a quantum computer can perform a computation that is beyond the capabilities of any classical computer. This could be due to the quantum computer being able to solve a problem that would take a classical computer an impractical amount of time to solve, or due to the quantum computer being able to solve a problem that is provably impossible for any classical computer to solve.

Achieving quantum supremacy is considered to be a major milestone in the development of quantum computers, as it would demonstrate the power and potential of these systems. However, it should be noted that quantum supremacy does not necessarily mean that quantum computers are superior to classical computers in all cases, or that they can solve all problems faster than classical computers. Instead, it simply means that there are certain computational tasks that quantum computers can perform more efficiently than classical computers."


