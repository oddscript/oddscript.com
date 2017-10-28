---
title: "Binary the machine language"
categories:
  - How computers work
date: 2017-10-25 19:53:16
tags:
---

***
This is the second article in the series: How computers work.
1. ['What is a computer?'](/how-computers-work/what-is-a-computer)
2. ['Binary the machine language'](/how-computers-work/binary-the-machine-language) (This article)
3. ['How computers compute'](/how-computers-work/how-computers-compute)
***

In the last article I simply described what a computer is. Now it’s time to show how the computer actually stores and process information. We are going to learn some machine language!

So, as you no doubt have heard the computer uses something called binary to store and process information. This is just a different way of counting than the decimal system (you know the way most humans count). Binary only contains ones and zeroes. So how in the butterscotch is the computer able to do anything with this? Well, as it turns out you can do quite a lot if you have enough sets of ones and zeroes.

## The lightswitch metaphor
Imagine that i have one lamp standing on my desk. Now, I need to signal you a number for some very contrived reason. How many numbers could I convey with only one lamp if we decided beforehand how we should interpret the lamp? Well, turns out we can convey two numbers. Let’s assume we start from the beginning and decide that *off* means **0** and *on* means **1**.


| Number | 1's (Lamp 1) |
|--------|--------------|
| 0      | off          |
| 1      | on           |


Now imagine that I have two lamps, how many numbers could we communicate with only two lamps? If we decide that the new lamp represents the number 2 when it’s on then we can represent 4 numbers, namely 0, 1, 2, 3.


| Number | 2's (Lamp 2) | 1's (Lamp 1) |
|--------|--------------|--------------|
| 0      | off          | off          |
| 1      | off          | on           |
| 2      | on           | off          |
| 3      | on           | on           |


Now it’s very simple math to calculate each scenario. Take scenario one, where both lamps are off. It means we take zero 2’s , which is 0, and zero 1’s which is 0 and then add them together like so, 0+0=0. Therefore if both lamps are off it means the number is 0. Scenario two is more interesting. First we take zero 2’s (0) and then one 1’s (1) which is 1. Scenario three we have one 2’s (2) and then one 1’s (0) which is 2. The last scenario is one 2’s (2) and zero 1’s (1) so it’s 3.

What happens if we increase the lamps to three lamps? As with the second lamp, we assign it a number it can represent and we pick 4 in this instance. Why 4? Well, we are counting in binary now so each lamp represents a number double the size of the previous lamp. Now the table looks like this:

| Number | 4's (Lamp 3) | 2's (Lamp 2) | 1's (Lamp 1) |
|--------|--------------|--------------|--------------|
| 0      | off          | off          | off          |
| 1      | off          | off          | on           |
| 2      | off          | on           | off          |
| 3      | off          | on           | on           |
| 4      | on           | off          | off          |
| 5      | on           | off          | on           |
| 6      | on           | on           | off          |
| 7      | on           | on           | on           |



## Decimal system vs. Binary system
That is actually what counting in binary is like. Not terribly different from the decimal system if you think about it in tables. The decimal system is probably what you count in every day. You learned it as a kid. Let’s count to 14 in the decimal system. (yay! *clap*)

| Number | 1000's | 100's | 10's | 1's |
|--------|--------|-------|------|-----|
| 14     | 0      | 0     | 1    | 4   |

Instead of putting on/off (or 1 and 0) in each column we are allowed to put 0-9 in each column. Here the columns are just the previous column * 10. So what we are saying is take zero 1000's, zero 100’s, one 10’s, and four 1’s, which is 0 + 0 + 10 + 4 = 14.


Let’s count to 14 in binary. As we saw earlier each column is twice as big as the previous (look right to left):

| Number | 8's | 4's | 2's | 1's |
|--------|-----|-----|-----|-----|
| 14     | 1   | 1   | 1   | 0   |

Here we are taking one 8’s, one 4’s, one 2’s and zero 1’s, which is 8 + 4 + 2 + 0 = 14.


## Bits, bytes and transistors
So how is the lamps related to the computer? It’s actually quite simple. Instead of lamps, switch to transistors. A transistor is basically just a mini switch, that can either be on or off or as we have learned 1 or 0. Take a bunch of these transistors and connect them and now you have a way for the computer to handle and manipulate information.

A single transistor could be viewed as a bit. A bit can hold 2 values, 1 or 0. Chain 8 bits together and you have the more familiar Byte. A byte can represent 256 different values (for example numbers between 0-255.)

## How to store other things than numbers in binary?
Maybe it seems impossible to understand how the computer now could store and handle other types of information than numbers using binary. But most things can actually be represented by numbers and if they can be represented by numbers they can be represented by binary.

### Colors
Maybe you have heard of RGB? It stands for Red, Green, Blue. Not to go into specifics of how color works but with these three colors you can represent all other colors if you just combine them right. So if we wanted to store these colors we could give them a Byte each. Now each color can have a value between 0 - 255. 

### Letters
If you assign each character a unique number you can now represent any language using binary. You could do this completely arbitrary, but a better approach would be to use some sort of standard so other people and computers could also understand what character each number represented. UNICODE is an example of a standard for connecting a character with a numbers.


## Lastly
This was just a brief overview of how binary works in computers. But hopefully you found it interesting. Next article will go through how the computer does calculations and very low level programming.
