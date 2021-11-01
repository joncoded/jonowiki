# Git command aliasing

### Shortening Git commands

Instead of typing out a command line `git status` entirely, we can configure our command line so that we can just type `git s` (or `git whatever`):

```
$ git config --global alias.s status
$ git s
```

![](https://www.joncoded.com/wp-content/uploads/git-alias.png)

The [Git manual](https://git-scm.com/book/en/v2/Git-Basics-Git-Aliases) recommends other aliases:

```
$ git config --global alias.co checkout
$ git config --global alias.br branch
$ git config --global alias.ci commit
```

### Combining Git commands

This [answer to a Stack Overflow question](https://stackoverflow.com/questions/4298960/git-add-and-commit-in-one-command) combines `git add` and `git commit` into one `git add-commit`:

```
$ git config --global alias.add-commit '!git add -A && git commit'
$ git add-commit -m 'my commit message'
```

Combining the above two, we can do something like:

```
$ git config --global alias.ac add-commit
$ git ac -m 'my commit message'
```

Thus, we can generalize the format as:

```
$ git config -global alias.{alias} {command}
$ git {alias} [flags]
```

#### Other examples

Short for `git push origin master` (push to the cloud!)

```
$ git config --global alias.pom 'push origin master'
$ git pom
```

Short for `git checkout -b {branch-name}` (check into a new branch)

```
$ git config --global alias.cob 'checkout -b'
$ git cob {branch-name}
```

Enjoy!
