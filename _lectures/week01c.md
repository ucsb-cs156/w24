---
title: "Week 01c - 06.30 Thu"
lecture_date: 2023-10-05
description: "Finish jpa00, Start jpa01 (Java mutation testing)"
ready: true
layout: default
parent: lectures
slides: 
---

[Slides]({{page.slides}})

# Announcements

* I reached out to a few of you on slack/email about your P00 on Gradescope
  - Everyone has the opportunity to get 100 on that if you follow through today.
  - If you didn't hear from me on Slack, you can assume you got 100.
  - After lecture today, the grades are final.
* Grades for P01, P02, P03, and P04 are now final.
* H00 is due Tuesday.   Please complete your work on GitHub (in the markdown file) then submit a link to your work on Canvas here: <https://ucsb.instructure.com/courses/14657/assignments/165157>

# jpa00

* Please finish [jpa00](https://ucsb-cs156.github.io/f23/lab/jpa00.html) today in lecture if you haven't yet.
  - It shouldn't more than about 15-30 minutes at most.
* Once you have, then please start on [jpa01](https://ucsb-cs156.github.io/f23/lab/jpa01.html).

# jpa01

If you haven't worked with Java before, you may find parts of the assignment confusing; if that's the case,
this may help to motivate you to read through the readings suggested in the assignment

But even if you have worked with Java extensively, there should be something new for everyone in this assignment.

Note that you *are permitted* (though not required) to work in pairs; if you do, please choose a pair partner from your same team.

In jpa01 we are looking at three kinds of testing

* Unit testing, for testing the code
* Test Coverage, for *testing the tests* 
* Mutation Testing, also for *testing the tests*

The difference between test coverage and mutation testing:
* Test Coverage is a *quick* way to see what *isn't* tested, but not a *good* way to tell us what *is* tested and how well.
* Mutation testing is a *much better* way to see what *is* tested, and *how well*, but it runs much more *slowly*.

The idea of mutation testing:
* Assume the code is correct for now.
* Make many copies of it, and insert mutations (changes) that should break the code, for example:
  - e.g. change an occurance of ≤ to >
  - replace an expression `return x;` (where x is a reference) with `return null;`
* Each "mutant" is a copy of the code base with a single change (a mutation)
* When you run the tests on the mutated code, each of these mutations should either:
  - Make the code go into an infinite loop, in which case tests might time out
  - Cause at least one test case to fail (we call this "killing the mutant")
 
If the test suite is a good test suite, all mutants will either time out, or be killed.

Your job: improve your test suite to the point where all of the mutants either timeout or are killed.

# How to proceed

1. Write stubs (empty methods that compile, but don't necessariy work) for all methods, so that the student code compiles against the instructor tests on Gradescope
2. Fix all the code so that it passes the student tests (your tests) and the instructor tests (which are not released; they are confidential.)
3. Improve your own test suite so that it gets to 100% code coverage, and kills 100% of mutants.



