---
layout: post
title: "Probability"
categories: math
tags: math probability prob
---

* TOC
{:toc}

Pierre de Fermat, Blaise Pascal

Probability Theory

Bernoulli & Random Variables

Expected Value

Monte Carlo method

"The law of averages states that the observed frequency of an event will tend to approach the expected frequency of the event as the number of observations increases. This means that the more times an experiment is repeated, the more likely it is that the observed frequency of the event will match the expected frequency of the event. The law of averages is a commonly used principle in statistics and probability theory, and it is often used to make predictions about the likelihood of certain events occurring."

Pascal's wager (debunked)

"The Monty Hall problem is a famous probability puzzle named after the American television game show host Monty Hall. The problem is based on a scenario in which a contestant is presented with three doors, behind one of which is a prize. The contestant is asked to choose one of the doors, and then the host opens one of the other doors to reveal an empty room. The host then asks the contestant if they would like to switch to the other unopened door or stick with their original choice. The question is, should the contestant switch doors, or stick with their original choice? The correct answer is that the contestant should switch doors, as this increases their chances of winning the prize from 1/3 to 2/3."

"Standard deviation is a measure of how much the values in a dataset vary from the mean."

Variance is how spread out the data points are. $$ Var = \sum (x - avg)^2 / N $$

Permutation – order matters P(n, r) = n! / (n-r)!

Combination – order doesn’t matter = C(n, r) = n! / \[r! (n-r)!\]
Also: P(n, r) / r!

Probability of two independent events: P(X, Y) = P(X)P(Y)

Probability of one event OR another event: P(X OR Y) = P(X) + P(Y) – P(X, Y)

With replacement

Without replacement

n choose m = m! / [(m-n)! * n!]

Sum Rule

* Discrete sum = P(A) = P(A, B) + P(A, ~B)
* Series sum = P(A) = P(A, B_1) + P(A, B_2) + … + P(A, B_n)

Conditional Probability = $$ P(A \vert B) = P(A, B) / P(B) $$

* (relevant outcomes) / (total outcome remaining in universe, when B is true) 
* read as “what is the probability of A given B?” 

Product Rule = $$ P(A, B) = P(A \vert B) \times P(B) $$

Also Multiplication Rule

Bayes’ Theorem = $$ P(A \vert B) = P(B \vert A) \times P(A) / P(B) $$

* If B happens, what is the probability of A occurring?
* The result is called posterior probability
* The prior probability is before any observation were made
* This theorem connects $$ P(A \vert B) $$ and $$ P(B \vert A) $$ and is essentially a formula for turning the conditional probability around. This is called inverse probability.
* There is apparently a debate on whether statistical inference should be based on $$ P(B \vert A) $$ or the inverse probability. 

Forward probability (also known as likelihood)

"The principle of indifference is a principle in probability theory that states that, when faced with a set of equally likely outcomes, each outcome should be assigned the same probability. This principle is also known as the principle of insufficient reason, and it is used to assign probabilities to events when there is no information or evidence to indicate that one outcome is more likely than another.

The principle of indifference is based on the idea that, in the absence of any evidence to the contrary, all outcomes are equally likely. For example, if you are flipping a fair coin, the principle of indifference states that the probability of heads and the probability of tails should both be 0.5, because there is no evidence to suggest that one outcome is more likely than the other.

The principle of indifference is an important concept in probability theory, as it provides a way to assign probabilities to events when there is no information or evidence to guide the decision. However, the principle of indifference is not always applicable, and it may not always lead to the correct or optimal probabilities in certain situations. For example, if there is some evidence or information that suggests that one outcome is more likely than another, the principle of indifference should not be used to assign probabilities."

Binomial theorem = (n choose s) * p^s * (1 – p)^(n – s)

* s = success
* n = trial
* p = probability of 1 success
* (n choose s) * probability raised to successes * failure to the power of failed trials

<img src="https://github.com/sif/sif/raw/main/files/post_files/treediagram.png" />

If a machine strikes a coin exactly the same place, same force, same everything, will it always land the same way?

Type I error

Type II error

Infinite monkey theorem



## Counting



## Conditional



## Poisson



## Probability Problems and Solutions

What additional statement, added to the three below, forms a probability distribution?

- I missed only my first class today
- I missed only my second class today
- I missed both my first and second class today

**“I did not miss my first or second class today”**

My friend takes 10 cards at random from a 52-card deck, and places them in a box. Then he puts the other 42 cards in a second, identical box. He hands me one of the two boxes and asks me to draw out the top card. What is the probability that the first card I draw will be the Ace of Spades?

**1/52**

I will go sailing today if it does not rain. Are the following two statements Independent or dependent?

**Dependent**

The probability that I will go sailing today AND the fair six-sided die will come up even on the next roll is .3. If these events are independent, what is the probability that I will go sailing today?

- **P(sailing) * P(dice) = .3**
- **P(sailing) = .3 / P(dice)**
- **P(sailing) = .3 / .5**

**.6**

If it rains, I do not go sailing. 

It rains 10% of days; I go sailing 3% of days.

If it does not rain, what is the (conditional) probability that I go sailing?

**Multiplication Rule.**

**It does not rain 90% of days then.**

**P(I go sailing \| it does not rain) = P(I go sailing and it does not rain) / P(it does not rain) = 0.03 / 0.9 = 0.0333**

I am at my office AND not working 2% of the time. I am at my office 10% of the time. What is the conditional probability that I am not working, if I am at my office?

**Multiplication Rule.**

**P(I am not working \| I am at my office) = P(I am not working and I am at my office) / P(I am at my office) = 2% / 10% = 20%**

The factory quality control department discovers that the conditional probability of making a manufacturing mistake in its precision ball bearing production is 4% on Tuesday, 4% on Wednesday, 4% on Thursday, 8% on Monday, and 12% on Friday.

The Company manufactures an equal amount of ball bearings (20%) on each weekday. What is the probability that a defective ball bearing was manufactured on a Friday?

**12%/(4%+4%+4%+8%+12%)=0.375**

An Urn contains two white marbles and one black marble. A marble is drawn from the Urn without replacement and put aside without my seeing it. Then a second marble is drawn, and it is white. What is the probability that the unknown removed marble is white, and what is the probability that it is black?

**p(the first marble is white \| the second marble is white) = .5**

**p(the first marble is black \| the second marble is white) = .5**

What is the probability, if I flip a fair coin with heads and tails ten times in a row, that I get at least 8 heads?

**C(10,8)*(0.5)^8*(0.5)^2+ C(10,9)*(0.5)^9*(0.5)^1+ C(10,10)*(0.5)^10=0.0546875**

Suppose I have either a fair coin or a bent coin, and I don’t know which. The bent coin has a 60% probability of coming up heads.

I throw the coin ten times and it comes up heads 8 times. What is the probability I have the fair coin vs. the probability I have the bent coin? 

**Assume at the outset there is an equal (.5,.5) prior probability of either coin.**

* **Please note that in order to fit the entire formula in the feedback, probability has been abbreviated to "prob."**

**E=event that there are 8 heads out of the 10 tossA= fair coinB= bent coinP(A)=P(B)=0.5P(E\|A)= C(10,8)*0.5^8*0.5^2=0.04395P(E\|B)= C(10,8)*0.6^8*0.4^2=0.12093P(A\|E)=P(E,A)/P(E)=[P(E\|A)P(A)]/[P(E\|A)P(A)+P(E\|B)P(B)]=0.2665P(B\|E)=P(E,B)/P(E)=[P(E\|B)P(B)]/[P(E\|A)P(A)+P(E\|B)P(B)]=0.73344**

I have two coins. One is fair and has a probability of coming up heads of .5. The second is bent and has a probability of coming up heads of .75. If I toss each coin once, what is the probability that at least one of the coins will come up tails?

**1 – 0.5 * 0.25 = 1 – 0.125 = .875**

What is the probability, when drawing 5 cards from a fair 52-card deck, of drawing a "full house'' (three of a kind and a pair) in the form AAABB?

**This hand has the pattern AAABB where A and B are from distinct kinds. The number of such hands is (13-choose-1)(4-choose-3)(12-choose-1)(4-choose-2). The probability is 0.001441.**


