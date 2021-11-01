# Git setup

After installation, we may wish to customize your Git with the following: 

### User setup

#### Username

When you make a commit, what would you want to show as your name?

* Open your **Terminal**
* Configure your GitHub account globally on your machine \(remove `--global` if you wish to configure your account just for the current repository\):

```text
$ git config --global user.name "joncoded"
```

* Let's confirm we have set this up correctly:

```text
$ git config --global user.name
> joncoded
```

#### E-mail

When you make a commit, what would you want to show as your e-mail address?

* Open Terminal
* As in the above with a username:

```text
$ git config --global user.email "example@email.com"
```

* Confirm:

```text
$ git config --global user.email
> example@email.com
```

### Repository \(repo\) setup

To create a **repository \(repo\)** for the current working folder:

```text
$ git init
```

### Remote repository setup

To connect the \(already-created\) **remote** version of our local repo: 

```text
$ git remote add [remotename] [repoURL]
```

Replace:

* `[remotename]` with any name \(most often, this is `origin`\)
* `[repoURL]` with the GitHub repository URL in the form: 
  * https://github.com/username/\[repo\].git

#### Removing the remote repository

For whatever reason, we can also delete the remote with this command from the local working folder: 

```text
$ git remote rm [remotename]
```

