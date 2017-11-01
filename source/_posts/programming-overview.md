---
title: Programming overview
description: Basic overview of how to program a computer
categories:
  - How computers work
date: 2017-11-01 16:42:32
tags:
---

***
This is the fourth article in the series: How computers work.
1. ['What is a computer?'](/how-computers-work/what-is-a-computer)
2. ['Binary: the machine language'](/how-computers-work/binary-the-machine-language) 
3. ['Logic gates and computing'](/how-computers-work/logic-gates-and-computing) 
4. ['Programming overview'](/how-computers-work/programming-overview) (This article)
***

We now know that the computer only works with 1’s and 0’s to process and store information. But how do we actually tell it to do stuff? We just enter a list of instructions for it to do. These instructions is a series of numbers that means something to the processor. So each processor might have different numbers corresponding to different instructions.

Let’s say we are a processor manufacturer and we need to make up a language for our new processor. We might come up with something like this:



| Code | Mnemonic   | What is does |
|------|------------|--------------|
| 0    | NOP        | Do nothing   |
| 1    | READ       | Get a number from the keyboard |
| 2    | WRITE      | Display a number on the screen |
| 3    | ADD        | Add two numbers |
| 4    | JUMP       | Go to a different step in the program |


This is a very simplified and restrictive language, but it works as an example. Each number can be represented with binary and stored like we talked about in the earlier articles. We can also string together multiple instructions to make what is called a program. A program is simply a series of instructions. With these imaginary instructions we could make a program that did the following:

1. Get a number from the keyboard
2. Get another number from the keyboard
3. Add the first and the second number together
4. Print the result to the screen
5. Go to step 1


if we write to program using our codes instead, the steps would look like this:

1. 1
2. 1
3. 3
4. 2
5. 4

And that’s a very basic view of how to program the computer. If we convert our codes into 1’s and 0’s using binary we now have a program that our processor understands. But, as a human you would probably go insane if you had to write code using 1’s and 0’s. So you could encode the 1’s and 0’s into the [hexadecimal](https://en.wikipedia.org/wiki/Hexadecimal) system for “better readability”. 

## Higher level programming languages

But the truth is, hexadecimal is not that easy to read either, so some good people have been smart enough to actually abstract away all of this by creating higher level programming languages. These languages are way easier to read and understand as a human and are easy to convert into machine code using what is called a compiler. The first compiler were written in machine language, but once you have a compiler + higher level programming language, like C for example, you can start to write your own compilers using that language. Another great feature is that with a language that is abstracted away from the actual machine language you can build compilers that compile the source code into multiple machine languages, making it easier to create portable code that works on different processors and platforms.

## Runtimes and scripting languages

Another abstraction on top of all of this is so called runtimes. Runtimes gives you the ability to run code without actually compile it into machine code every time. It works as a translation program, taking in your source code and translating it into machine instructions on the fly. This is basically how programming languages like Javascript and Python works. Usually this approach comes with a performance hit, but with the added benefit of being easier and faster to develop in.
