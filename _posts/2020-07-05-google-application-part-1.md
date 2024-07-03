---
title: 'Google: Landing the SWE Job - Part 1'
categories:
  - google
tags:
  - algorithms
  - data structures
  - applications
toc: true
---

The following notes reflect some of my personal thoughts on applying to Google, where I've been working since July 2020. These notes are best suited for junior developers - for instance, the notes don't include any advice for a
_System Design_ interview, because that is only given for applicants with experience (which I wasn't at the time).

**Disclaimer**: these notes in no way reflect Google's position on the matter, and only represent my
personal opinions.

# Applying: General Tips

First, I strongly suggest applying for companies besides Google as well. The reasons I recommend applying for several companies are:

- **Have Alternatives**: Don't put all your eggs in one basket. First, nothing guarantees that you'll be accepted to Google, and I'm
  assuming your ultimate goal is to get an interesting and challenging position. You should apply to your top 4 companies. Be open to
  being offered a more interesting job in your 3rd choice, and don't let Google's brand be the sole deciding factor. Also, be respectful of
  interviewers' time, and only interview at places you would actually be pleased to accept a position in.

- **Negotiations**: Even if you get into Google, you'll want to negotiate your conditions. How much negotiation experience do you have
  compared to Google's recruiters? Basically, none. Even if you think you're a good negotiator (e.g. with your siblings, with your friends), remember that company recruiters do this full-time.

  Thus, your best shot at negotiating is simply stating the offers that you have received from other companies. Having alternative offers
  ensures that you won't fold on
  your demands (because these are real terms that you've already been offered). Google's recruiters will sense that, and put more effort
  into securing you a better offer. Of course, even if you don't have other offers, negotiate and ask for a little more than what you'd
  be happy with.

- **Interview Experience**: Interviewing is a completely different ball game than taking a test. In an exam, you have time to reflect on
  questions, take 10 minutes to breath and overcome your nerves, and sketch out possible answers in any order you fancy. In contrast, during
  interviews you need to think on the spot, out loud, and start offering ideas almost immediately. Combine that with nerves, and you
  get a good recipe for freezing on the spot (this definitely happened to me).

  For this reason, I would recommend interviewing with several companies. You'll habituate yourself to the interview environment and
  gain valuable practice in verbal communication.

# Do Mock Interviews!

The interview nerves discussed in the previous section lead me to strongly suggest you find people to do mock interviews with before
approaching any company. There are 3 avenues I would recommend for mock interviews, each one having its unique benefits:

1. **With friends**: The advantage of having a friend interview you is that you'll probably be slightly more relaxed, since you know your
   friend appreciates you and won't judge you harshly for mistakes! Another benefit of having a friend interview you is that they'll
   probably be frank and honest in their feedback.

   One thing to make sure your friend doesn't do though is be too supportive: smiling, nodding in encouragement, etc. This is especially
   important for Google interviews, since Google interviewers are instructed to keep poker faces - so, make sure your friend interviews you without providing a lot of guidance.

2. **[Pramp](https://www.pramp.com/)**: An online platform for pairing random software developers together to practice interviews. The questions provided on the platform are easier than those in interviews, but I still stumbled a lot on them in the beginning due to nerves. If you meet someone you enjoy practicing with, Pramp also enables you to swap email addresses - this is how I ended up connecting with a friendly French developer, and we practiced together quite rigorously in the days before our interviews (Pramp enables you to provide your own questions when coding with a friend).
3. **With professional colleagues**: If you have a colleague who works at Google or one of the other large companies, it would be of utmost
   benefit
   for you to conduct a mock interview with them. Some of the best advice that I received (on coding style, communication clarity, and
   general thought processes) came from 2 mock interviews that I had with real Google employees, who have professional interview experience.

# Interview Topics: Bird's Eye View

In my experience, the Google technical interviews aim to check 3 qualities in (junior) software developers:

- **Data Structures and Algorithms**: Your standard 101 classes. I'll elaborate on this in the next [post]({% link _posts/2020-07-06-google-application-part-2.md %}), but this includes understanding time and sspace complexities of heaps, hash tables, binary trees, graphs, etc; the data structures' and algorithms' theory and applications.
- **Your ability to ask questions**: In two separate segments of my Google interviews, I was given an open-ended problem whose main aim
  was to check my thought process. I spent most of my time responding by posing questions to clarify and elucidate the goal. In both these
  segments, I wrote only a bit of pseudocode at the wrap-up stage to document my high-level insights to tackling the
  problem . The pseudocode
  consisted
  entirely of my
  made-up API calls, which reflect the emphasis of these segments on achieving high-level clarity followed by the creation of logical
  building blocks
  for the solution.
- **Your coding ability**: Google wants to know that you can (1) code and (2) look _critically_ at your code for checking bugs and
  correctness. It doesn't matter which language you pick to code in (I used Python), but make sure you code nicely in that language. For instance, don't code in Python as if it were C++: in Python, I made sure to use list comprehensions rather than for-loops, and use tuples rather than lists when my variables were immutable. I think this is a reasonable expectation: Google expects you to have done due diligence in familiarizing yourself with the writing style of your preferred language.

# Resources: What You Should Read/Do

The resources that helped me the most, and which all proved invaluable:

## [Introduction to Algorithms by CLRS](https://www.amazon.com/Introduction-Algorithms-3rd-MIT-Press/dp/0262033844)

This wonderful book covers almost all the theory you need in order to understand the standard data structures and algorithms (notably, it's
missing information about Tries; I'll detail resources for that below). However, note that some of the book's data structure implementation details don't correspond to those normally provided in interviews:

- In CLRS, the Breadth First Search (BFS) algorithm alters the vertex attributes directly (e.g. using color attributes), while in
  interviews you won't usually be able to alter the graph nodes (e.g. if they are provided as read-only). It is better, at
  least in Python, to maintain a set of visited nodes instead.
- In the CLRS heap implementation, the developer knows each element's index in the array at all times. This is useful for when a developer
  wants to update a key (e.g. refer to the CLRS function `heapDecreaseKey()`). If you're coding in Python though, there
  is no easy way for you to track an element's index in the array. In fact, the standard Python `heapq` library doesn't even provide a
  public interface for updating an element's value. If you're given a problem in which a heap would have its elements periodically updated, then if you're coding in Python, you should either state how you would implement this functionality on your own, or perhaps opt for another language.
- CLRS assumes that nodes in binary trees have a `parent` attribute, and this simplifies many tree operations, such as CLRS'
  `getSuccessor()` function. In interviews, this attribute often does not exist, so I would strongly recommend understanding how to
  implement all the standard binary tree operations for two separate cases: one when nodes have a parent attribute, and one when they don't.

## [The Algorithm Design Manual](https://www.amazon.com/Algorithm-Design-Manual-Steven-Skiena/dp/1849967202)

This is the book that truly got me excited about using data structures (and reviewing their theory again). It's a long book, and I don't
think you need to read all of it (I didn't). By reading the author's algorithmic "war stories" from real-world businesses, I finally
internalized how crucial the correct choice of data structure is, and how interconnected it is to the choice of algorithm. Among the book's highlights:

- Successfully emphasizing that 'recursive structures occur everywhere in the algorithmic world', thus motivating recursive approaches to problems (which can later be often optimized by dynamic progamming).
- Making logarithms exciting, and emphasizing their utility in problem solving.
- Illustrating that heapsort and select sort are the same algorithm differing only by underlying data structure (take a moment to ponder
  this); the same is true for insertion sort and the creation of a balanced binary search tree.
- Explaining in a clearer manner than CLRS the applications and implementations of DFS in both directed and undirected graphs.

## [Cracking the Coding Interview](https://www.amazon.com/Cracking-Coding-Interview-Programming-Questions/dp/0984782850)

This book is indescribably useful in learning how to approach an interview question. The book details the crucial steps in tackling a problem:

1. Ask clarifying questions, clear up ambiguities, and check assumptions.

   For instance, ask (1) how the input is stored, (2) how to handle edge cases, (3) if the input fits in RAM, (4) if access patterns are
   uniform (e.g. for a database, perhaps read operations occur a lot more frequently than write operations). Ask: are strings made up of
   ASCII or unicode characters? If multiple solutions exist, which one should be returned, if not all? Can I assume the input is valid, or
   should I check it first? Can I
   modify the input, or is it immutable?

2. Walk through an example to get familiarity with the problem and confirm understanding of the problem statement.
3. Propose a naive solution and understanding its complexity (one usually, but not always, exists in interview questions).
4. Clarify if there is a lower bound complexity to the solution. E.g. it is impossible to sum the values of an n-element array in less
   than O(n) with a single CPU (no parallelization).
5. Consider different solutions and their trade-offs in terms of time and space.
6. Write clean, modular code.
7. Use the example from step #2 or propose a better example for walking through and debugging your code.

## [Leetcode](https://leetcode.com/)

Leetcode is an amazing resource for practicing coding interview questions. I personally felt that Leetcode's question style was quite
similar to many of the questions I received at interviews. In addition, I liked the fact that Leetcode's questions are succinct in
comparison to other sites, such as [HackerRank](https://www.hackerrank.com/). (Side note: HackerRank's lengthier problem statements are a
good resource if you need to prepare for a coding
home assignment).

Leetcode offers detailed solutions to many of its problems, and the forums are also a wonderful source of information (for instance, see this [post](https://leetcode.com/discuss/general-discussion/458695/dynamic-programming-patterns) on dynamic programming patterns). I learned how to nicely code [Tries](https://leetcode.com/problems/implement-trie-prefix-tree/) on the platform, and the ability to filter problems by corporation, by difficulty level, and by topic was immensely beneficial. I felt that the Google questions I was asked corresponded to **easy** and **medium** on Leetcode, so those are the ones I would recommend spending the majority of your time on.

# Next Step

For concrete technical advice, please see my next [post]({% link _posts/2020-07-06-google-application-part-2.md %}).
