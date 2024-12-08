---
layout: post
title: "Discrete Mathematics"
categories: math
tags: math discrete_math Discrete_Structures
---

* TOC
{:toc}

> “Mathematics is the surest way to immortality. If you make a big discovery in mathematics, you will be remembered after everyone else will be forgotten.”
> Paul Erdos

De Morgan’s Law

The negation of a disjunction is the conjunction of the negations

The negation of a conjunction is the disjunction of the negations

## [Logic](https://www.afterlifesong.com/philosophy/2002/12/01/logic.html)

Kleene closure

Symbolic logic, the use of symbols to denote propositions, terms, and relations in order to assist reasoning

- Associative, x(yz) = (xy)z
- Commutative, x+y = y+x
- Distributive, x(y+z) = xy + xz

Propositions, a declarative statement that is either true or false, not both, often denoted by single letters p, q, r, s, t, etc. These single letters are boolean variables or logic variables.

Paradox, “this sentence is false.”

Truth value

Truth Table

Compound propositions are formed by simple propositions called components. 

Connective

Tree diagram

George Boole
Boolean expressions

Conjunctions

| p | q | $$ p \land q $$ |
| -- | -- | -- |
| T | T | T |
| T | F | F |
| F | T | F |
| F | F | F |

Disjunctions

| p | q | $$p \vee q$$ |
| -- | -- | -- |
| T | T | T |
| T | F | T |
| F | T | T |
| F | F | F |

Negation

| p | ~p |
| -- | -- |
| T | F |
| F | T |

Implication

Conditional statement

Hypothesis (or premise) $$\rightarrow$$ conclusion

$$p \to q$$

Warning: The statement p only if q is often misunderstood as having the same meaning as the statement p if q. Remember, p if q means If q, then p. So be careful. Think of only if as one phrase; do not split it.

Converse

Inverse

Contrapositive

The **converse** of the implication $$p \to q$$ is $$q \to p$$ (switch the premise and the conclusion in $$p \to q$$).
The **inverse** of $$p \to q$$ is $$\sim p \to \sim q$$ (negate the premise and the conclusion).
The **contrapositive** of $$p \to q$$ is $$\sim q \to \sim p$$ (negate the premise and the conclusion, and then switch them).

Boolean operators

Binary operator

Unary operator



## Set Theory

Georg Cantor

Closure

Equivalence relation
Reflexive relation
Symmetric relation
Antisymmetric relation
Inclusion relation
Transitive relation

Power set

Properties:

- Injective, 1 to 1
- Surjective, every element maps to at least one element
- Bijective, injective and surjective

- Set A is a subset of B if every element in A is also an element in B.
  - $$A \subseteq B$$
- Set A is a proper subset of B if every element in A is in B but they are not equal.
  - $$A \subset B$$
- Principle of Extension; 2 sets are the same if and only if they have the same members, so a set is determined by its members
- Principle of Abstraction; a set is determined by its properties
- Order does not change a set.
- Empty set Ø
- Universal set U
- Complement of A, depending on literature is: A’ or A bar (a line above A) or $$A^c$$
- Absolute complement of set A means a member belongs to set U but not A
- Cardinality = size of set
- $$\land$$ and, conjunction
- $$\lor$$ inclusive or, disjunction
- $$\lnot$$ not
- Truth tables
- union means the member is in set A **or** B
- intersection means the member is in set A **and** B
- A\B means A minus B, sometimes other texts uses A-B or A~B instead.

Sets

Set Operations



Boolean logic



Functions



Basics of Counting

**Permutations and Combinations**

- Factorial, 3! = 3 * 2 * 1
- 0! = 1

Pigeonhole Principle

Solving Recurrence Equations:

- Substitution method
- Recursion-tree method
- Master method



Continuum hypothesis



## Order Theory

Partial ordering
Partially ordered set

Lattice

Hasse diagram



## Recurrence Relations

"Recurrence relations are equations that describe the relationship between consecutive terms in a sequence of numbers. They are used to define the terms of a sequence in terms of the previous terms, and to solve problems involving sequences and summations."



## Combinatorics

"Combinatorics is the branch of mathematics that studies ways of combining objects or elements, such as permutations, combinations, and partitions. It is used to count, enumerate, and analyze the possible arrangements or configurations of a given set of objects, and to solve problems involving discrete structures."

## [Probability](https://www.afterlifesong.com/math/2012/02/26/probability.html)



## Group Theory

Group Theory definition:

- Set of elements G
- Operations +, *
- Closure, the group is closed under these operations
- Inverses exists, which gives you identity element
- Elements obey the associative property

For inverses, if you add an inverse, you will get 0. Each transformation has an opposite.
G may not be commutative. If it is commutative, it falls under a commutative group.

Common groups:

- Commutative group
- Abelian group
- Noncommutative group

Modular systems, $$n \mod m$$

Closure:

- Integers are closed under addition.
- Integers are not closed under division.

Symmetry

Abelian group is commutative (or a commutative group)



## [Number Theory](https://www.afterlifesong.com/math/2016/08/17/pure-mathematics.html)



## Function Theory



## Graph Theory

m-ary tree

internal vertices

- G = (V, E)
- V = set of vertices (or nodes)
- E = set of edges
  - e = {v, w} (unordered pairs, undirected)
  - e = (v, w) (ordered pairs, directed)
- There are graphs that have both directed and undirected.
- Weighted, unweighted
- Legal coloring, where no adjacent node shares the same color.
- Represent graph with edge list or adjacency list, that’s the simplest.
- Adjacency matrix is an option for graph representation too.
- Adjacency list good for sparse graphs.
- Adjacency matrix good for dense graphs.
- Scalability is a challenge.

Is there a path between two nodes in an undirected graph? Run DFS or BFS from one node to the other to see if you reach the other one.

What’s the shortest path between two nodes in an unweighted, undirected graph? Run BFS from one node and backtrack once you reach the second. DFS does not always find the shortest path.

Can an undirected graph be colored with two colors? Run BFS, assigning colors as nodes are visited. Abort if we ever try to assign a color different from the one it was assigned earlier.

Does an undirected graph have a cycle? Run BFS, keeping track the number of times we’re visiting each node. If we visit a node twice, we have a cycle.

**Directed Acyclic Graph**
<img src="https://github.com/sif/sif/raw/main/files/post_files/directed-acyclic-graph-computer-science.png" />

Graph Coloring
Matching Problems



### Four color theorem

The four color theorem states that any given map can be colored using no more than four colors, such that no two adjacent regions have the same color.



## Game Theory

Prisoner's dilemma

Nash's equilibrium



### Cooperative / non-cooperative



### Symmetric / asymmetric



### Zero-sum / non-zero-sum



### Simultaneous / sequential



### Perfect information and imperfect information



### Combinatorial games

"Combinatorial games are a type of game in which the players take turns making moves, and the goal is to achieve a certain position or configuration of the game pieces. Examples of combinatorial games include chess, checkers, and tic-tac-toe."



### Infinitely long games



### Discrete and continuous games



### Differential games

"Differential games are a type of game in which the players' choices affect the evolution of a continuously changing environment, such as the movement of a vehicle or the spread of a disease."



### Evolutionary game theory

"Evolutionary game theory is a branch of game theory that studies the dynamics of populations of players who adapt and evolve over time. It is used to model and analyze the evolution of strategies, preferences, and behaviors in situations where individuals or groups interact and compete with each other."



### Stochastic outcomes (and relation to other fields)



### Metagames



### Pooling games



### Mean field game theory



## Discrete Mathematics Problems and Solutions


