# Welcome to the Terminal

Even though it looks like something out of the Matrix, the terminal will become your best friend over the next six months. It's a way to move around your computer, set up projects, and modify files quickly without taking your hands off your keyboard. From here on out, you should use your terminal instead of your file explorer.

Open up your terminal! If you're running Windows, use Git Bash. If you're on a Mac, use your built-in terminal. Let's run some commands to get you started:

*Note: from here on out, we'll use the word "directory" instead of "folder" in reference to file structure.*

1. Make a new directory called `workspace`.
```
mkdir workspace
```

2. Change directories- let's move into the one you just created. This is like double clicking on a file in your file explorer to see what's inside of it.
```
cd workspace
```

3. Get in the habit of checking to make sure you're in the right place. `pwd` stands for "print working directory" and will show you the filepath to your current location.
```
pwd
```
*This command should output something like `/Users/jordancastelloe/workspace/`*

4. Create a new file called `index.html`
```
touch index.html
```

5. To see if it worked, list all the files in the current directory:
```
ls
```
*This command should output `index.html`, since right now it's the only file in `workspace`.*

6. Open your new file in VS Code:
```
code index.html
```

7. Whoops, we changed our mind. We don't want `index.html` after all. Let's remove it.
```
rm index.html
```
*Be careful with `rm`. This command deletes it permanently and immediately- it doesn't go to your recycling bin. Use it wisely.*

PRO TIP: Software Developers use the terminal and Command Line Interface (CLI) instead of a Graphic User Interface (GUI) like File Explorer.

***
## Lightning Exercise
1. Use the `cd` command to navigate to your workspace directory that we just made
1. Use the `mkdir` command to make a new directory inside your Workspace directory called `foundations`
1. Use the `cd` command to change directories into your `foundations` directory
1. Use the `mkdir` command to make a new directory inside `foundations`. Call it `HTML`.
1. Use the `cd` command to change directories into the `HTML` directory.
1. Use the `touch` command to create a new file in the `HTML` directory called `index.html`
1. Run the `pwd` command. You should see something like the following:
```
/c/Users/newforce/workspace/foundations/HTML/
```
***


## Supplemental Material

- [Visual Studio Code Tutorial](https://www.youtube.com/watch?v=VqCgcpAypFQ)
- [A Gentle Introduction to the Terminal - Mac OS](https://computers.tutsplus.com/tutorials/navigating-the-terminal-a-gentle-introduction--mac-3855)
- [10 Bash file system commands](https://medium.com/the-code-review/top-10-bash-file-system-commands-you-cant-live-without-4cd937bd7df1)
