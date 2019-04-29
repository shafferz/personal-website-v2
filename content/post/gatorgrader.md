+++
date = 2019-04-29
title = "Working on the GatorGrader Software System"
summary = "A reflection on my work with the GatorGrader system."

[header]
image = "gatorgraderlogo.png"
caption = "The GatorGrader Logo"
+++

In the early half of my final semester at Allegheny College, I had the
opportunity to work on a project called GatorGrader. GatorGrader, a tool
designed to help students know when they have satisfied the requirements of a
given lab assignment on GitHub, is an open-source software developed by students
at Allegheny College. You can check out the project
[here](https://github.com/GatorEducator/gatorgrader), and you can read on to
hear my personal reflection of my work on the system as part of the Software
Innovations course.

At the start of the semester, I was more or less shoe-horned into a Team Leader
position for a team of 5 other developers and myself. At the outset, we had
little direction as our task was, in essence, "expand upon this existing code
base." To begin this, we dove headlong into the Issue Tracker and started
selecting issues to solve. The other Team Leaders and I took up some of the
basic issues tagged "Good First Issue," and made a plan of action for the first
major issues we would all tackle. My team had worked with another team on
completing a task wherein we had to implement an Abstract Syntax Tree (AST) to
determine paragraphs in Markdown documents for the purpose of checking a minimum
paragraph length.

While this task sounded daunting, my team did not directly implement the AST.
Rather, we performed the viability research, created sample documents for
testing the tools we had found during our research, and, when the other team
actually implemented the AST, we wrote the automated test cases for them using
the `pytest` Python library for automated unit testing.

Our viability research pointed us to several tools. The first of such tools that
we found was [CommonMark](https://commonmark.org/), which we ultimately ended up
using for the implementation. We then had to consider how we would parse the
data gathered by CommonMark, which lead us into a discussion revolving around
tools such as [glom](https://github.com/mahmoud/glom), a tool for parsing data
sets of any size, or a tool like [JQ](https://stedolan.github.io/jq/) which
does similar things with JSON files. In the end, we ended up using what came
the AST interfact through the
[CommonMark-py library](https://pypi.org/project/CommonMark/).

Once we figured out what we were doing, and the other team we worked with
actually implemented the AST into the GatorGrader system, my team worked to
create a comprehensive set of test cases for making the sure the implementation
of the AST was behaving as expected. We considered many facets, such as
whether or not a multi-line code block would break a paragraph into two
different paragraph nodes, if any fragment would do the same, how different
fragments counted towards word counts, and so on. Once we established the
possible scenarios, we divided the test cases over our six team members, and
implemented the test cases as such.

After that, we as a team needed to find new issues to work on. Rather than
working with other teams to divvy up the work, though, the teams all took a more
free-for-all approach to tackling issues in the Issue Tracker. Our team ended up
working on making sample repositories for the purpose of testing the GatorGrader
system on repositories with code in different programming languages, as well as
provide starter repositories for instructors who are teaching using those
languages. I personally developed the sample repository for using GatorGrader on
a C++ programming language assignment, which you can find
[here](https://github.com/GatorEducator/cpp-assignment-starter).

All in all, working on GatorGrader was a fun way to get experience leading a
team and working on tackling issues for an existing software project on GitHub.
In the future, I am excited to learn more about creating software from scratch,
which was the premise of the second long-term software project that I worked on
for my Software Innovations course in my last semester here at Allegheny.
