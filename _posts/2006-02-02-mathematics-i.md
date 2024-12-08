---
layout: post
title: "Mathematics I"
categories: math
tags: math definition
---

<img src="https://github.com/sif/sif/raw/main/files/post_files/saint_curious_george.png" />

* TOC
{:toc}

http://www.geometer.org/curriculum.pdf
If that's down, please see backup <a href="https://www.afterlifesong.com/files/curriculum.pdf">here</a>.

Is mathematics complete? For example, is there a way to prove every true statement? Does every statement have a proof?

Is mathematics consistent? For example, is it free of contradiction?

Is mathematics decidable? For example, is there an algorithm that can always determine whether a statement follows from the axioms?

History: intuitionism vs formalism

The answer? No. Godel's incompleteness theorem.



## Motivation

If you see sin and you think "sin", you're probably religious. If you see sin and you think "sine function with the domain of all reals and a range of -1 to 1 inclusive," you're probably an engineer at NYU.

The hardest math class is any math class before 8AM.
The hardest math class is any math class after 4PM.

https://en.wikipedia.org/wiki/Math_55

["Mathematician on TikTok gives example of how ‘insane’ high-level math can be: ‘[It] goes into its own universe’"](https://www.intheknow.com/post/mathematician-math-rocket-science-tiktok/)



## Proofs

Proof is how we go from premises to conclusions.

["Prove that the axioms of mathematics are complete and consistent. Express your answer in Mayan hieroglyphics."](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-042j-mathematics-for-computer-science-fall-2010/recitations/MIT6_042JF10_rec01.pdf)

<img src="https://github.com/sif/sif/raw/main/files/post_files/1333525376076.png" />



### Axioms

Basic statements assumed to be true, also known as postulates

First principle



### Conjecture

A statement that has not been proved



### Theorem

A statement that has been proved



#### Lemma

An intermediate theorem in a proof



### Counterexamples

All you need is one counterexample



## Theorems

Andrew Wiles
Fermat’s Last Theorem; $$x^n + y^n = z^n$$ has no positive integer solutions, where n >= 3

Infinite prime numbers (proof by contradiction); Euclid’s theorem

Prime number theorem; distribution of prime numbers

Banach-Tarski Paradox

Fundamental Theorem of Arithmetic; all integers greater than 1 are products of prime numbers, basically it means that prime numbers are “individual atoms” that make up all other natural numbers

Fundamental Theorem of Algebra; 

Fundamental Theorem of Calculus;



Existence

Uniqueness

Zeno’s paradoxes



### Gödel’s incompleteness theorem

"Godel was the first to have realized that when he proved his incompleteness theorem, namely that arithmetic sufficies for all of programming, theoretically speaking. So in this sense you are correct. 

Supplemental: we do need some sort of iteration or recursion, as was noted in the comments. By "arithmetic" here I mean general recursive functions which have recursion built in. There is a form of "conditional" in recursion, namely the distinction between zero and a successor."
https://cs.stackexchange.com/questions/64664/why-does-computer-have-branch-and-jump-instructions



## Paradoxes

Russell’s paradox; “does the set of all sets which do not contain themselves contain itself?”

Liar’s Paradox; the next sentence is true. The previous sentence is false.



## Techniques

identities (p=q)

implication (p->q)



The Law of Bad Proofs: When your proof is wrong, you can prove anything.



### Direct Proof

Also known as proof by construction)

$$p \to q$$



#### Proof by Geometry



#### Proof by Induction

- this proof only works when you are working over a set that is countable
- prove a basis step
- then state the inductive hypothesis
- let this element be called the nth element, assume the truth of this statement and show that it remains true for the nth + 1 element



### Indirect Proof

#### Proof by Contradiction

- assert the truth of p and not q, then derive something false
- but since the initial statement is only true when p->q is false, p->q must be true



#### Proof by Contrapositive

- not q->not p
- assume not q and derive not p



## Some Random Definitions



An integer number n is even if and only if there exists a number k such that n = 2k.

An integer number n is odd if and only if there exists a number k such that n = 2k + 1.

Two integers a and b are consecutive if and only if b = a + 1.



## Some Random Proofs

Theorem: Square root of 2 is irrational.

Proof:

1. Suppose $$\sqrt 2$$ is rational. 
2. This means $$\sqrt 2$$ can be rewritten as $$\sqrt 2 = \frac{p}{q}$$.
3. We may also assume there are no common factors (or we'd have to cancel them out).
4. Squaring both sides gives: $$2 = \frac{p^2}{q^2}$$.
5. This implies: $$2q^2 = p^2$$.
6. $$p^2$$ is even. The only way for this to be true is if p itself is even.
7. $$p^2$$ is divisible by 4. Hence $$q^2$$ and therefore q must be even.
8. So p and q are both even which is a contradiction to our assumption that they have no common factors.
9. This proves that the square root of 2 cannot be rational. 
10. (Just show that p and q are even numbers.)

Theorem: If a and b are consecutive integers, then the sum of a + b is odd.

Proof

1. Assume that a and b are consecutive integers.
2. Because a and b are consecutive we know that b = a + 1.
3. Thus, the sum a + b may be re-written as 2a + 1. 
4. Thus, there exists a number k such that a + b = 2k + 1 so the sum a + b is odd.

Theorem: If n and m are both odd, then n + m is even.

Proof

1. Suppose n and m are odd integers.
2. Then n = 2k + 1 and m = 2l + 1, for some k, l $$\in Z$$, by the definition of an odd integer.
3. Therefore n + m = (2k+1) + (2l+1) = 2(k + l + 1).
4. Since k and l are integers, so is k + l + 1.
5. Hence n + m + = 2p, with p = k + l + 1 $$\in Z$$.
6. By the the definition of an even integer, this shows that n + m is even.



<img src="https://github.com/sif/sif/raw/main/files/post_files/20110404.gif" />
