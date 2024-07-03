---
title: 'My Favorite Software Engineering Books'
categories:
  - code
tags:
  - engineering
  - design
toc: true
---

Not all books are made equal, but these are my go-to books for software engineering practices.

# Refactoring, by Martin Fowler

_"The heart of a good software design is its modularity—which is my ability to make most
modifications to a program while only having to understand a small part of it."_

This [book](https://dl.ebooksworld.ir/motoman/Refactoring.Improving.the.Design.of.Existing.Code.2nd.edition.www.EBooksWorld.ir.pdf) is one you should have handy whenever designing or refactoring code. There's also an [online cheatsheet catalog](https://refactoring.com/catalog/).

I particularly recommend Chapters 2, 3, 6, 7, 8. Random highlights:

- **Refactor to increase development velocity:** _"When I talk to software developers who have been working on a system for a while, I
  often hear that they were able to make progress rapidly at first, but now it takes much
  longer to add new features. Every new feature requires more and more time to
  understand how to fit it into the existing code base, and once it’s added, bugs often crop
  up that take even longer to fix. The code base starts looking like a series of patches
  covering patches, and it takes an exercise in archaeology to figure out how things work.
  This burden slows down adding new features—to the point that developers wish they
  could start again from a blank slate...."_
- **Functions instead of Comments:** _".. You should be much more aggressive about decomposing
  functions. A heuristic we follow is that whenever we feel the need to comment
  something, we write a function instead. Such a function contains the code that we
  wanted to comment but is named after the intention of the code rather than the way it
  works. We may do this on a group of lines or even on a single line of code. We do this
  even if the method call is longer than the code it replaces—provided the method name
  explains the purpose of the code. The key here is not function length but the semantic
  distance between what the method does and how it does it."_
- **Feature Envy:** _"A classic case of Feature Envy occurs when a function in one module spends more time
  communicating with functions or data inside another module than it does within its
  own module. We’ve lost count of the times we’ve seen a function invoking half­a­dozen
  getter methods on another object to calculate some value. Fortunately, the cure for that
  case is obvious: The function clearly wants to be with the data."_
- **Data Clumps:** _"Data items tend to be like children: They enjoy hanging around together. Often, you’ll
  see the same three or four data items together in lots of places: as fields in a couple of
  classes, as parameters in many method signatures. Bunches of data that hang around
  together really ought to find a home together.... A good test is to consider deleting one of the data values. If you did this, would the
  others make any sense? If they don’t, it’s a sure sign that you have an object that’s dying
  to be born."_
- **Making Classes:** _"Classes are a fundamental construct in most modern programming languages. They are the primary
  construct in object­oriented languages, but are also useful with other approaches too.
  When I see a group of functions that operate closely together on a common body of data
  (usually passed as arguments to the function call), I see an opportunity to form a class.
  Using a class makes the common environment that these functions share more explicit,
  allows me to simplify function calls inside the object by removing many of the
  arguments, and provides a reference to pass such an object to other parts of the system."_ I needed this reminder after my class PTSD from coding in Java.
- **Splitting into Modules:** _"When I run into code that’s dealing with two different things, I look for a way to split it
  into separate modules. I endeavor to make this split because, if I need to make a
  change, I can deal with each topic separately and not have to hold both in my head
  together. If I’m lucky, I may only have to change one module without having to
  remember the details of the other one at all."_

# Complete Code, by Steven McConnall

This [book](https://people.engr.tamu.edu/slupoli/notes/ProgrammingStudio/supplements/Code%20Complete%202nd.pdf) provides some beautiful meta level lessons.

I particularly enjoy Chapter 5, "Design in Construction". The chapter covers:

- Why the design phase should be messy, even though the end result should be clean and organized
- **Key Design Concepts:** including themes like minimal complexity; ease of maintenance; loose coupling; extensibility; high fan-in; low/medium fan-out; portability.
- About why restricting interactions between your `n` subsystems is so important - avoiding entropy and chaos for making future changes and understanding interactions!
- **Design Heuristics:** the chapter provides a strong motivation for not only thinking in OOP terms, but thinking in _hiding secrets_. _"Information hiding has unique heuristic power, a unique ability to inspire effective
  design solutions... Asking “What does this class need to hide?” cuts to the heart of the interface-design
  issue. "_
- **Loose Coupling:** _"Good coupling between modules is loose enough that one module can easily be used by other modules. **Model railroad cars are coupled by opposing hooks that latch
  when pushed together. Connecting two cars is easy—you just push the cars together.** A routine such as `InitVars( var 1, var2, var3, ..., varN )` is more tightly coupled because, with all the variables it must pass, the calling module practically knows what is happening inside InitVars(). Two classes that depend on each other’s use of the same global data are even more tightly coupled."_
