# Setting Up Your Environment

## Installs

[link to vs code install]

[SET UP THE CODE COMMAND FOR VS CODE]

[link to git bash install]

[link to google chrome install]

## Welcome to the terminal

Even though it looks like something out of the Matrix, the terminal will become your best friend over the next six months. It's a way to move around your computer, set up projects, and modify files quickly without taking your hands off your keyboard. From here on out, you should use your terminal instead of your file explorer.

Here are some terminal commands to get you started:

*Note: from here on out, we'll use the word "diectory" instead of "folder" in reference to file structure.*

1. Make a new directory called `workspace`. 
```
mkdir workspace
```

1. Change directories- let's move into the one you just created
```
cd workspace
```

1. Get in the habit of checking to make sure you're in the right place. `pwd` stands for "print working direcotry" and will show you the filepath to your current location.
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

[ link to visual studio code tutorial]