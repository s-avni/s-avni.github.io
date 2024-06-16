---
title: "Getting into Google: Part 2"
categories:
  - google
tags:
  - algorithms
  - data structures
  - applications
toc: true
---

<!-- TODO: add this in default layout -->
<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>

Without further ado, here are some of my suggestions on topics to review. I've also included details about some of my pitfalls, in the hope that they will save you time when preparing for interviews. I didn't include any sections on _heaps_, _tries_, _backtracking_, or _amoritized analysis_, but you should be well-acquainted with all these concepts.

## Bits!

Even if you're coding in a high level language like Python, there are still a few "low-level" bit details interviewers would expect you
to know. I encountered questions on several of these bit "rules"-- notice that they're basic: once you understand the logic, you'll be able to easily re-derive them rather than rely on memorization. A good overview is provided in the book "Cracking the Coding
Interview":

- Multiply by $$2^i$$: `x = x << i`.
- Get the ith bit: `temp = x & (1 << i)` and then `ith_bit = temp != 0`
- Set the ith bit: `x = x | (1 << i)`
- Clear the ith bit: `mask = ~ (1 << i)` and then `x = x & mask`
- Clear bits from MSB to ith bit: `mask = (1 << i)`, then `mask = mask -1 `, then `x = x & mask`
- Clear bits from 0 to i: `mask = -1`, then `mask = mask << (i+1)`, then `x = x & mask`

You should also note that:

- $$2^{10} \approx 1\:thousand$$ // ~1KB
- $$2^{20} \approx 1\:million$$ // ~1MB
- $$2^{30} \approx 1\:billion$$ // ~1GB
- $$2^{40} \approx 1\:trillion$$ // ~1TB

## Binary Search

While the idea behind binary search is simple, it's easy to get the implementation details incorrect. Make sure you can code this short
algorithm in your sleep! I also highly recommend understanding how to [adapt the algorithm](https://leetcode.com/problems/find-first-and
-last-position-of-element-in-sorted-array/) to cases when there are duplicates and you want to search for the _first occurrence_ index
or the _last occurrence_ index. Although these slight changes sound simple, there are several pitfalls, and it takes
time to internalize the
details.

Also, Google tends to give questions which have a non-obvious use of binary search (some of which are very elegant), so I'd recommend
going through some of Leetcode's [binary search problems](https://leetcode.com/tag/binary-search/). Feel like you've got these type of
problems under your belt? Try [the Cargo problem](https://www.youtube.com/watch?v=EWhSL4excWI); this problem also imparts the important
lesson that evaluating your complexity in terms of non-intuitive variables can be helpful not only in dynamic programming!

## Sorting

Make sure you understand and can implement both _mergesort_ and _quicksort_, as well as explain the pros and cons of each (bonus points
if you can explain how to parallelize them). I ended up implementing these two algorithms 4 times before my first interview, taking a gap
of a few days between each attempt. Each time that I coded the solutions, I noticed something else that I had missed or overlooked
; they require care and detail-orientation.

I'd also recommend reading the CLRS section on why O(nlogn) is the lower limit complexity for comparison-based sorting - simple theory that goes a long way. Knowing about insertion sort is also good, as it can be useful for nearly-sorted arrays.

## Dynamic Programming & NP

First off, familiariaze yourself with the classic DP problems: LIS, LCS, Knapsack, Edit Distance, Coin Change, Set Cover. It would
also be great if you could explain which of these problems are time/space polynomial and which are pseudo-polynomial.

A general approach for tackling DP problems is to first think of a recursive solution, and then convert the solution to a bottom-up or
town-down DP. Review the pros and cons of top-down and bottom-up. For instance, a top-down solution only calculates the
subproblems actually needed for the specific question, but the recursive calls may cause a stack overflow. In contrast, the
bottom-up approach calculates all sub-problems and may take more time. On the other hand, it's often easier to make bottom-up
approaches very space-efficient by throwing away sub-solutions that are no longer needed.

Some backtracking problems can be optimized with DP, but not all (for instance, the [n-Queen's problem](https://en.wikipedia.org/wiki/Eight_queens_puzzle)). On this note, make sure you can also implement backtracking problems correctly - for instance, if you need to present all solutions for the n-Queen's problem, take care to make sure (in Python) that you're appending deep copies to your solution list (shallow copies will be overwritten as you explore further problems).

## Linked Lists

The idea of linked lists is simple, but there are numerous implementation details to keep an eye out for, and clarification questions to ask:

- Does the linked list have a cycle? (If so, implement a cycle checker)
- Does the linked list have duplicate values?
- How will you handle an empty linked list?

I recommend being comfortable implementing at least the following: (1) finding the middle of a linked list, (2) reversing a linked list
, (3) implementing a circular linked list in which elements can be removed or added. Note that using a `dummyHead` and/or a `dummyTail` can save you a lot of headache.

## Trees

When solving tree problems, make sure to ask the interviewer clarifying questions. As a rule, you should always ask clarifying questions, but
it's particularly important that you don't make invalid assumptions on tree problems. Common questions could include: Is the tree a BST
? Is the tree balanced? \[For search], should I assume the sought value is in the tree? Does the tree have duplicates?

You should be able to implement a successor/predecessor function (for trees in which there nodes know their parents, and for trees in
which nodes do not); implement BST node insertion (easy) and node deletion (more tricky); implement a preorder, postorder, and
inorder traversal (at least recursively, and preorder iteratively as well, with a stack).

## Graphs

Make sure you understand and can implement:

- DFS - for both directed and undirected graphs (there is an edge case to notice in the latter!). Know how to keep track of discovery and finished time, and make sure you understand how to track the time (e.g. with a global `time` variable). Understanding of the [Parenthesis Theorem](https://web.stanford.edu/class/archive/cs/cs161/cs161.1168/lecture11.pdf) and the application of DFS to topological sort is important.
- BFS - make sure to remember to use a `visited` set so that your algorithm doesn't run forever. Can you implement a bi-directional search, which can save a lot of time? BFS and DFS are some of the most common graph questions, so take the time to familiarize yourself with them on platforms like [Leetcode](www.leetcode.com).
- Dijsktra (like BFS, but for weighted-edge graphs)
- A* (shortest path to a single destination in weighted-edge graphs). Can you explain why A* reduces to Dijkstra, for instance? [Stanford](http://theory.stanford.edu/~amitp/GameProgramming/) has a great resource for this with fantastic visuals.

## Greedy Algorithms

A greedy algorithm solution can be hard to spot, and sometimes quite difficult to prove the correctness of as well. I think asking a
challenging
greedy
algorithm question during an interview would be thus be almost unfair, but I do recommend being familiar with the
classic
greedy algorithms
detailed in CLRS: the Activity-Selection problem and the Lecture-Hall problem, and greedy graph problems such as Kruskal's and Prim's
algorithms for minimum spanning trees. Can you explain why these solutions are correct and their invariants?

## Operating Systems (for other companies)

While I personally didn't get asked anything about Operating Systems (OS) at Google, the other big companies I interviewed at did. I would recommend understanding what the role of an OS is, its abstraction mechanisms (processes, threads, sockets, pipes, memory), some of its mechanisms (create process, schedule process, read pipe, etc), and the common policies (e.g. least-recently used). Make sure you can explain virtual addresses, the process control block, and how processes and threads communicate with one another (including mutexes, condition variables, semaphores). Know the difference between a deadlock and livelock, and be familiar with the classic producer-consumer problem and the reader-writer problems. Can you implement a simple circular queue to implement this?

## Nice to Have

These are the things I would review if I had time, but wouldn't stress skipping:

- Union-Find data structure (detailed in CLRS)
- Counting and Radix sort (CLRS)
- Strongly Connected Components (CLRS)
