---
title: "Oxford MSc Application: Passing the Take Home Assignment & Interview"
categories:
  - Oxford
tags:
  - code
  - application
  - algorithms
---

You've submitted your application to the Oxford CompSci MSc Program! What happens next?

* auto-gen TOC:
{:toc}

# Take-Home Assignment

When applying for the computer science MSc at Oxford, the next stage after submitting the personal statement and reference letters is a take-home assignment. I was given 48 hours to complete the assignment - the questions were not difficult, and I believe can be done without much effort by anyone who
has completed a computer science bachelor degree.

The questions you receive depend on your academic background. Some of my colleagues, who came from a non-CS fields, were tasked with solving basic questions about code and linear algebra concepts.

While I no longer have my original questions, I can roughly guess what they were from my answers. For the computer science applicants, I hope this helps you narrow down which subjects to review.

## 1st Question

<i>Tell us about a mathematical course you enjoyed studying during your undergraduate degree and how it is applied in computer science. Write around 250 words. </i>

### Answer

Although I love mathematics in general, one field that I have found especially interesting is linear algebra. I first became interested in this field when I discovered that one could determine whether a system of equations has none, one, or infinitely many solutions using an abstract object called a determinant. Although I later learned that a determinant is not used in practice due to its computational complexity, I was still captivated by the idea of approaching a practical problem with a more higher-level perspective.

In the same spirit, the use of eigenvectors and eigenvalues to characterize sets of linear transformations also fascinated me. I was initially exposed to their use in phsyics, my other undergraduate major, in order to help decouple dependent differential equations and find the natural frequencies and energy levels of quantum systems. But I must confess that I was more impressed when I found out about their uses in computer science:

- To reduce a dataset’s dimensionality, thus saving an enormous amount of storage memory.
- In Google’s PageRank algorithm

Linear Algebra is ubiquitous in computer science. For instance, it's useful in computer graphics because many common geometrical transformations, such as rotation and shearing, are linear operations. Linear algebra is also used to gain insights into graph theory. For example, by taking powers of the adjacency matrix of a graph, one can find the length of a walk between two vertices. Linear algebra can be used to find approximate solutions when none exists, which can happen when there are more equations than variables: a classic example is provided by the analytic
solution of the Least Squares problem.

## 2nd Question

**_A. Given an ($$n$$,$$n$$) grid, how many paths are there from $$(0,0)$$ to $$(n,n)$$?_**

### Answer

While you can solve this question for a specific value of $$n$$ using dynamic programming (or recursion, if your computer has the memory capacity), combinatorics
allows you to obtain a general solution:

One must take $$n-1$$ moves down (D) and $$n-1$$ moves right (R), for a total of $$2(n-1)$$ steps. If we order the steps and give them labels from $$1$$ to $$2(n-1)$$, then we simply need to count the number of ways to select $$n-1$$ of these
labels (without caring about order), and assign them to D (for instance). In short, there are $${2n-1}\choose{n-1}$$ paths.

**_B. Given $$k$$ different baskets and $$n$$ identical apples, such that $$k>n$$, how many ways can we allocate the apples such that no basket is empty?_**

### Answer

This is a “Combinations with Repetitions”[^1] problem. However, since $$n>k$$ and we require that no basket be empty, $$k$$ apples are already accounted for: each of the first $$k$$ apples must go into the $$k$$ different baskets, and there is only one
way to do this since they are indistinguishable.

The remaining $$n-k$$ apples can go into any of the baskets, and there are $${(n-k)+k-1}\choose{n-k}$$, which gives us the final answer (multiplied by the factor of 1 from earlier).

## 3rd Question

<i>Given a connected graph with $$k$$ vertices ($$k>4$$), where each vertex starts with a color of red or blue, at each time step a vertex becomes the color that is
the majority of its neighbors' colors, and does not switch if there is a tie.

Prove or disprove the following claim: If the graph reaches a static situation, then all vertices are of the same color.</i>

### Answer

I spent a while trying to prove this claim, but it is actually false. A counter example is seen below. Half the vertices are red and the other half are blue, but none of the vertices can change colors.

R \ / B
| R ---- B
R / \ B

## 4th Question

I do not recall the last question precisely, yet it was a simple coding question (psuedocode was fine), in which you needed to be able to explain your algorithm, as well as its time and space complexity. Stirling's approximation came in handy at some point...

# Online Interview

the last step of the application is an online interview. The interview lasts about 40 minutes, and is comparable to the take-home assignment. Prior to the interview, I had prepared personal answers in expectation of getting questions about my CV, but the questions were in fact standard, non-personal ones:

1.  Question about <b>combinatorics</b>
2.  Question about providing an algorithm for <b>graphs</b>, with a follow-up about the time and space complexity of the solution and tweaking the BFS algorithm.
3.  Simple <b>recursion</b> problem, with follow-ups about dynamic programming and memoization.

# Conclusion

If you review your basic courses from your bachelor's, you should be fine. In my year, combinatorics, algorithms, and general
math knowledge were enough, but I would also recommend reviewing probability and computation theory.
