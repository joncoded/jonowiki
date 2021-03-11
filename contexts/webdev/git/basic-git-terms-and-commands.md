# Git terms and commands

### Common Git terms

| Term | Laymen's term |
| :--- | :--- |
| **repository**  \(aka **repo**\) | project folder |
| **local repository**  \(aka **local**\) | project folder on a personal computer |
| **remote repository**  \(aka **remote**\) | project folder on the Internet \(a server, perhaps?\) |
| **staging** | a selection of files from the project folder |
| **committing** | confirming the selection of files as a change to the project |
| **pushing** | uploading the confirmations to the project folder on the Internet |
| **cloning** | copying a project folder from the Internet to one's computer |
| **forking** | copying someone else's project from the Internet onto one's own account |
| **branching** | creating a parallel version of a project \(which can later merge back\) |
| **checkout** | setting a branch as the current working branch |
| **merging** | combining a version with another version of a project |

### Common Git commands

Type `git` plus any of the following:

<table>
  <thead>
    <tr>
      <th style="text-align:left">Command</th>
      <th style="text-align:left">What it does</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>init</code>
      </td>
      <td style="text-align:left"><b>creates </b>or <b>initializes</b> a new local repository</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>add -A</code>
      </td>
      <td style="text-align:left"><b>adds</b> all the changes to the Git repository to &quot;staging&quot;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>commit -m &quot;message&quot;</code>
      </td>
      <td style="text-align:left"><b>updates</b> the local repository with all the changes previously added
        to &quot;staging&quot; (tagged with a message summarizing the changes made)</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>remote add origin [repourl]</code>
      </td>
      <td style="text-align:left"><b>connects</b> the local repository with a remote repository (usually
        on GitHub.com)</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>push [origin] [branch]</code>
      </td>
      <td style="text-align:left">
        <p><b>uploads</b> the most recently committed changes</p>
        <p>(from the local repository to the remote repository)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>clone [repourl]</code>
      </td>
      <td style="text-align:left"><b>downloads</b> a remote repository to one&apos;s own computer</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>checkout [branchname]</code>
      </td>
      <td style="text-align:left"><b>switches</b> to a branch in the local repository (assuming it exists)</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>checkout -b [newbranchname]</code>
      </td>
      <td style="text-align:left"><b>creates</b> a new branch in the local repository</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>branch -a</code>
      </td>
      <td style="text-align:left"><b>displays</b> a list of all branches</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>status</code>
      </td>
      <td style="text-align:left">
        <p><b>displays</b> the current status of the local repository, i.e.:</p>
        <ul>
          <li>current branch name</li>
          <li>any files on staging</li>
          <li>any files with changes but not on staging</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>pull [branch]</code>
      </td>
      <td style="text-align:left"><b>retrieves</b> the latest changes of a working version from the remote
        to the local</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>diff</code>
      </td>
      <td style="text-align:left"><b>displays</b> a list of code changes since the last <code>add</code>
      </td>
    </tr>
  </tbody>
</table>

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

