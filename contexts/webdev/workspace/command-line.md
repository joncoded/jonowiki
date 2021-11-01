---
description: using this "hacker-looking" interface to access files
---

# Command line

On the Mac, we would usually access the **command line** via an application called Terminal:

![](../../../.gitbook/assets/2021-01-20-at-22.02.57.png)

This interface allows us to:

* _**Access files and folders**_ on the computer and on the internet
  * Create, retrieve, update, delete!

### The prompt

For `jon@Jons-Mac-mini Desktop %`:

* `jon@Jons-Mac-mini` refers to the _**current machine**_
* `Desktop` refers to the _**current folder**_
* `%` is the _**prompt**_ (this symbol may also be `$` or `#` depending on the system)
  * just a way of stating our "cue" to type a command

### The command

A **command** consists of a

* **keyword**
* **arguments** (the values that follow the keyword)

For example:

```
$ cd myfolder
```

From that:

* the keyword `cd` (change directory) leads the single argument `myfolder`
* together, the command changes directory to the folder called `myfolder`

### The commands

These commands come in handy on an everyday basis:

| Command | Arguments         | What it does                                                                          |
| ------- | ----------------- | ------------------------------------------------------------------------------------- |
| `cat`   | `filename`        | prints the contents of a file (may not appear readable depending on the type of file) |
| `cd`    | `foldername`      | accesses a folder (if it exists)                                                      |
| `cd`    | `..`              | accesses the parent folder of the current folder                                      |
| `clear` | (none)            | clears the command-line screen of its history                                         |
| `ls`    | (none)            | lists the files and sub-folders of the current folder                                 |
| `mkdir` | `foldername`      | creates a directory/folder                                                            |
| `mv`    | `oldname newname` | renames a file to a new name                                                          |
| `pwd`   | (none)            | prints the path of the current folder                                                 |
| `rmdir` | `foldername`      | removes the directory/folder (if it exists)                                           |
| `rm`    | `filename`        | removes the file (if it exists)                                                       |
| `touch` | `filename`        | creates a new blank file                                                              |
