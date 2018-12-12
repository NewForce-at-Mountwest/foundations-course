# Setting Up Your Environment

## Installs
#### Hardware

Up until now, you didn't have the power to destroy your machine, but within the first two weeks of attending NewForce you will have that power. Go buy a backup drive RIGHT NOW and start backing up your entire hard drive.

**Seriously, right now!**

---

### Online Services

#### Github

Github is the primary site that software developers throughout the world use to store their code, and share it with other developers. Visit the [sign up page](https://github.com/join) and create your own, free account.

---


## Software

### Google Chrome

[Google Chrome](https://www.google.com/chrome/browser/desktop/index.html) is the most popular browser for web developers because of the powerful tools it provides to test code, manipulate documents, and measure performance.


### Git Bash

Visit the [Git powershell](http://www.git-scm.com/downloads) download page click the "Download for Windows" button, and once complete, install the software. Powershell is a command line utility that allows you to run most Unix command inside a Windows environment.

### Node

Visit the [Node.js](https://www.nodejs.org) site and install the LTS release.

### Node Packages

Now that you have Node installed, you can install some open source software that you will need in the course.

Run the following command in Git Bash.

```sh
npm i -g http-server
```

### Slack Desktop Client

Do not use the browser-based interface for Slack. Download and [install the client](https://slack.com/downloads). Let us know if you did not get an invitation to the NewForce Slack organization, and we'll send you one immediately.

### Visual Studio Code

Visual Studio Code is the editor we will all be working on to start the course.

Windows users must visit the [Visual Studio Code](https://code.visualstudio.com/) website to download and install the code editor.

Suggested extensions to install

1. [ESlint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
1. [FontSize Shortcuts](https://marketplace.visualstudio.com/items?itemName=fosshaas.fontsize-shortcuts)
1. [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
1. [Quokka.js](https://marketplace.visualstudio.com/items?itemName=WallabyJs.quokka-vscode)
1. [REST Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client)


## Welcome to the Terminal

Even though it looks like something out of the Matrix, the terminal will become your best friend over the next six months. It's a way to move around your computer, set up projects, and modify files quickly without taking your hands off your keyboard. From here on out, you should use your terminal instead of your file explorer.

Open up Git Bash! Let's run some commands to get you started:

*Note: from here on out, we'll use the word "directory" instead of "folder" in reference to file structure.*

1. Make a new directory called `workspace`. 
```
mkdir workspace
```

1. Change directories- let's move into the one you just created
```
cd workspace
```

1. Get in the habit of checking to make sure you're in the right place. `pwd` stands for "print working directory" and will show you the filepath to your current location.
```
pwd
```
*This command should output something like `/Users/jordancastelloe/workspace/`*

1. Create a new file called `index.html`
```
touch index.html
```

1. To see if it worked, list all the files in the current directory:
```
ls
```
*This command should output `index.html`, since right now it's the only file in `workspace`.*

1. Open your new file in VS Code:
```
code index.html
```

1. Whoops, we changed our mind. We don't want `index.html` after all. Let's remove it.
```
rm index.html
```
*Be careful with `rm`. This command deletes it permanently and immediately- it doesn't go to your recycling bin. Use it wisely.*




## Supplemental Material

- [Visual Studio Code Tutorial](https://www.youtube.com/watch?v=VqCgcpAypFQ)
- [A Gentle Introduction to the Terminal](https://computers.tutsplus.com/tutorials/navigating-the-terminal-a-gentle-introduction--mac-3855)
