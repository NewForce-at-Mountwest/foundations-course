# Git

## What is Git?
Git is the most popular version control system. It allows you to track and annotate changes you make in your files so that your project's history is easy to understand. It also allows you to traverse your file's history and revert to previous versions. [Here's a great summary of what git can do in plain English](https://blog.red-badger.com/2016/11/29/gitgithub-in-plain-english). Read until you get to the section on collaborating and then skip down to the glossary. (We'll get to collaborating soon, but don't worry about it for now.)

## Git vs. GitHub
Git and GitHub are two completely seperate systems. Git repositories exist on your computer. You can track your changes locally and never push them up to GitHub. However, if you decide you want to share your project with the world (or with teammates), you can push your Git repo up to GitHub. GitHub hosts your entire commit history so you (and anyone else) can access it from any computer.

[Go ahead and create a GitHub account here](https://github.com/).

[DO WE NEED TO WORRY ABOUT SSH KEYS?]

## A few commands to git you started locally (har har har)

If you're not already in your `workspace` folder, go there now. To figure out where you are and change directories, see the [Environment](ENVIRONMENT.md) chapter.

Make a new directory called `test-project` and `cd` into it.
```
mkdir test-project && cd $_
```

Initialize a new Git repo inside of the `test-project` directory.
```
git init
```
*Once you've done this step, Git will start tracking all the changes you make inside this folder.*

Make some changes! Let's create an `index.html` file.
```
touch index.html
```

Check in with Git to see what changes it's recorded.
```
git status
```

You should see something like this:
```
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	index.html

nothing added to commit but untracked files present (use "git add" to track)
```

Add your changes to the staging area. This tells Git that you want to include updates to a particular file in the next commit.

```
git add index.html
```

Run `git status` again. This time, it should show `index.html` under the "changes to be committed" heading.

Commit your changes. This basically takes a snapshot of every file in the staging area at the time of the commit. Every commit has a message attached to it. Over the course of the project, the commit messages tell a story of what was changed, when, and by whom.

```
git commit -m "created empty index.html file"
```

Run `git status` again- it should say that there's nothing new to commit.

Next, create a new repository on GitHub. Once you create it, you'll see a quick-start page with different commands.

Copy the second set of commands. It should look something like this:
```
git remote add origin git@github.com:[YOUR GIT USERNAME HERE]/test-project.git
git push -u origin master
```

Refresh the page on GitHub. You should see your empty `index.html` file!


## Supplemental Material

[ link to visual studio code tutorial]

[link to git/ github tutorial]

[]

## Practice

1. Go through the steps above on your own, with a brand new directory. (The more you practice, the sooner this process will become muscle memory!)


