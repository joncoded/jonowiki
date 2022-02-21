---
description: how to begin web development
---

# 🧰 Workspace

### Setting up essential software

* **Code editor** (that's all we'll need to install!)
  * any of [Atom](https://atom.io), [Sublime](https://wwwsublimetext.com) or [Visual Studio Code](https://code.visualstudio.com) (which we will outline here)

### Starting a new project

* Open [Visual Studio Code](https://code.visualstudio.com) and in the Welcome screen:
  * Click on "Add workspace folder..." to add a folder in a desired location
  * Click open the top-most icon to view the Explorer
  * Right-click on the folder name to add new files or folders
* Have a **Terminal** window appear at the bottom of Visual Studio Code while coding:
  * Click on "View" > "Terminal" on the top bar
  * Terminal panel will appear on the bottom
    * this panel will also allow you to add new tabs
* Start a new project via the Terminal with the following command:

```
$ npm init -y
```

(This will create a new `package.json` file that lists metadata and, more importantly, what **dependencies,** i.e. third-party code, this project will need!)

* Save your **Workspace** in another folder (not in your _project folder_)
  * Click on "File" then "Save Workspace as..."
  * This will tell VSC what files are opened the next time you open the Workspace
* Have fun coding!
