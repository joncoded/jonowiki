---
description: summarizing everyone's (least) favourite software version control system
---

# 🐙 Git

**Git** allows software developers (and even anyone who works with any kind of data) to share bundles of files in **repositories**:

* Each person can have a **local repository** (aka version)
  * they can then push that to a **remote repository** (typically on [GitHub.com](https://www.github.com))
* Many people can work on the same **remote repository**
* Everything magically gets merged based on changes called **diffs**...
  * ...unless a **conflict** happens in which case developers typically resolve the conflict (or pull their hair and/or skin out)

When things run smoothly enough, Git can feel like the most useful thing in the world as it:

* tracks changes
* allows us to rollback changes
* shows who did something, line-by-line
* simplifies code review by a lot
* promotes open source development

#### Git basics

To "get by with Git", one just needs to know "**the flow**" in addition to these actions:

* **Cloning**
  * copying a repository to one's own "local" computer
* **Initializing**
  * starting a local repository
* **Staging**
  * preparing changes to a local repository for a commit
* **Committing**
  * confirming changes to a local repository
* **Pushing**
  * sending committed changes from a local repository to a remote repository
* **Pulling**
  * "**fetching**" changes from a remote repository to a local repository
* **Branching**
  * creating a separate sub-version ("**checking out a new branch**") of a repository
* **Merging**
  * requesting an integration of a sub-branch into the main branch
  * confirmation of this merge usually via a "**pull request approval**"

Many more idiosyncratic terms in the Git universe exists so we will try to cover them in this series!
