---
title: Understanding the command-line (bash)
categories:
  - Computer basics
date: 2017-10-22 15:19:52
tags:
  - bash
  - cli
---

If you want to be a developer you really should have some familiarity with the terminal. So in this article I will try to explain what the terminal (shell or command line) is and how to use it in a very basic way. Bear in mind that the terminal is slightly different depending on what OS you are using. This article is written from the perspective of macOS, but all information should be applicable on other UNIX systems as well. As long as they use bash as their shell.
<!-- more -->
## What are shells?
On macOS and many other UNIX based system the default shell is called bash (Bourne-again shell). A shell is just a command line interpreter that let’s the user access the operating system’s functionality from a text based interface instead of the graphical user interface.
On mac you open the app called Terminal and it will launch the shell called bash as default. There are other shells than bash that you could use, but we will stick with the default for this article.

To check that you are using bash as your shell: open up the app Terminal and type the following command into the window:

``` bash
echo $SHELL
```

If you get /bin/bash as the output it means you are using bash.

## Why use the command line?
So now you might be asking why someone would prefer to type text into a shell instead of using a mouse and click on icons. Well there is some use cases where using a text based interface is superior to having to move a cursor around:

- Searching for files and in files
- Batch-operations on files are easier with the terminal. 
- Running development tools
- Troubleshooting

As a developer you will also find that a lot of the tools you encounter are only available through the command line.
How to use it
Just like earlier you open the terminal app so you can see the blinking cursor. This is the place to enter your commands.

## Commands
Commands are quite simple to understand. It’s just the program’s name followed by some arguments/parameters (data) for the program to work on. So the generic structure of a command would look like this:

<program> <arguments>


Here is an actual command you can type in:

``` bash
echo Hello
```
here is a simple program echo. It takes in a string of text, in this case “Hello” and just prints it back to you. Play around with it and fill the screen with your messages. Now you can have your own little echo chamber, who needs the internet am I right?

When you have stopped being a writing-weirdo, you can always clear the terminal with:

``` bash
clear
```

or just use the keyboard shortcut cmd-K (or ctrl+K on a non-macOS)

Let’s revisit the command you typed in to see if you were in bash:

``` bash
echo $SHELL
```

Now this is the same program echo but with another parameter, in this case you are feeding the echo program a thing called a variable (with is just like variables in math, they hold a value). This $SHELL variable contains the value for the path to your current shell which should end in /bash if your are using bash.

## Paths
Typing a command executes it in your path (a.k.a current folder, location or directory). 
So now you need to learn how to determine where you are, how you move around to different paths.

To see your current path run:

``` bash
pwd
```

pwd, or the print working directory command just spits out your current location.

### What locations exists?
You can think of your hard drive (HDD) as your root (/) location, on the HDD there are a lot of folders in a tree like structure.

![](/images/path-structure-bash.jpg)

There are many more subfolders than displayed on this illustration. But it’s not practical to fit all of them. Hopefully you get the general idea anyway.

### Change the path
to get to the root location of your computer just type the following command:

``` bash
cd /
```

here we are using the command/program change directory (cd) with the argument “/”. The single slash is the root directory. 

``` bash
cd /Users
```

this command takes you to the Users folder, inside here are all the users’ folders.

``` bash
cd /Users/<username>
```

this command takes you to the user folder of whatever user you type in instead of <username>. If you type in your username, you will end up in your user folder.

``` bash
cd ~
```

Now this is a weird one right? This is just a short hand to take you to the current user’s folder. So whatever user you are logged in as. Tilda (~) just means the current user’s home folder.

``` bash
cd
```

What? cd without arguments, what is going to happen? Well, it just defaults to the current user’s home directory so it ends up being the same as cd ~
Now when you can hop around to different locations, maybe you want to see what’s inside the folder you are in?

``` bash
ls
```

ls, or the list command, lists files and folders in the current location.

If you think all those files messed with the zen of your terminal you can clear the terminal screen with:

``` bash
clear
```

or with the keyboard shortcut cmd+K. 

now back to ls, it can take arguments just like cd, and also flags:

``` bash
ls / -a
```

Breakdown:
ls - program/command to list files and folders
/ - root location as argument/parameter to the program
-a - include all files (even hidden ones)

So the command just shows you all files and folders (including hidden ones) in the root location. It does NOT change the current location, it only shows what is in the root location without switching to it. Perfect for when you just want a peek.

If you are tired of the terminal and just want to use Finder on the current path just run:

``` bash
open .
```

the dot indicates the current location and opens the folder in finder. Let’s open the root path in Finder as well:

``` bash
open /
```

## Essential commands in bash
All <arguments> should be replaced with whatever you want.

Clear the terminal (or cmd+K)
``` bash
clear
```
Print something to the terminal
``` bash
echo <text-to-print>
```
Open a location in Finder
``` bash
open <path>
```
Change current location
``` bash
cd <path>
```
List files and folders in a location
``` bash
ls <path>
```
Move a file or a folder from one location to another
``` bash
mv <path-to-be-moved> <new-path>
```
Copy a file or a folder from one location to another
``` bash
cp <path-to-be-copied> <new-path>
```
