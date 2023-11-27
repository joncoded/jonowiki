---
description: getting to know the git lingo
---

# Git terms and commands

### Common Git terms

| Term                                   | Laymen's term                                                           |
| -------------------------------------- | ----------------------------------------------------------------------- |
| **repository** (aka **repo**)          | project folder                                                          |
| **local repository** (aka **local**)   | project folder on a personal computer                                   |
| **remote repository** (aka **remote**) | project folder on the Internet (a server, perhaps?)                     |
| **staging**                            | a selection of files from the project folder                            |
| **committing**                         | confirming the selection of files as a change to the project            |
| **pushing**                            | uploading the confirmations to the project folder on the Internet       |
| **cloning**                            | copying a project folder from the Internet to one's computer            |
| **forking**                            | copying someone else's project from the Internet onto one's own account |
| **branching**                          | creating a parallel version of a project (which can later merge back)   |
| **checkout**                           | setting a branch as the current working branch                          |
| **merging**                            | combining a version with another version of a project                   |

### Common Git commands

Type `git` plus any of the following:

| Command                       | What it does                                                                                                                                                                                           |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `init`                        | \*\*creates \*\*or **initializes** a new local repository                                                                                                                                              |
| `add -A`                      | **adds** all the changes to the Git repository to "staging"                                                                                                                                            |
| `commit -m "message"`         | **updates** the local repository with all the changes previously added to "staging" (tagged with a message summarizing the changes made)                                                               |
| `remote add origin [repourl]` | **connects** the local repository with a remote repository (usually on GitHub.com)                                                                                                                     |
| `push [origin] [branch]`      | <p><strong>uploads</strong> the most recently committed changes</p><p>(from the local repository to the remote repository)</p>                                                                         |
| `clone [repourl]`             | **downloads** a remote repository to one's own computer                                                                                                                                                |
| `checkout [branchname]`       | **switches** to a branch in the local repository (assuming it exists)                                                                                                                                  |
| `checkout -b [newbranchname]` | **creates** a new branch in the local repository                                                                                                                                                       |
| `branch -a`                   | **displays** a list of all branches                                                                                                                                                                    |
| `status`                      | <p><strong>displays</strong> the current status of the local repository, i.e.:</p><ul><li>current branch name</li><li>any files on staging</li><li>any files with changes but not on staging</li></ul> |
| `pull [branch]`               | **retrieves** the latest changes of a working version from the remote to the local                                                                                                                     |
| `diff`                        | **displays** a list of code changes since the last `add`                                                                                                                                               |

### Typical workflow

```bash
# making a commit and pushing it online
$ git add -A
$ git commit -m "adding all files"
$ git push origin development

# getting code other people did (if any)
$ git pull support/newbranch

# doing an experiment (branching)
$ git checkout -b support/newbranch devlopment
$ git branch -a

# finding out the status of a project
$ git status
$ git diff
```

###
