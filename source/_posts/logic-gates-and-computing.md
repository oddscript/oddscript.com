---
title: Logic gates and computing
description: "Learn how computers compute with logic gates."
categories:
  - How computers work
date: 2017-10-26 22:08:44
tags:
---

***
This is the third article in the series: How computers work.
1. ['What is a computer?'](/how-computers-work/what-is-a-computer)
2. ['Binary: the machine language'](/how-computers-work/binary-the-machine-language)
3. ['Logic gates and computing'](/how-computers-work/logic-gates-and-computing) (This article)
***

<!-- block -->
Computers use boolean algebra to calculate and store data. It’s basically another version of algebra that only uses two values, true or false, or as we are familiar with 1 or 0. But boolean logic contains a range of operators to calculate these two values. You can build these logical operators using transistors. They are called logic gates and there is quite a few of them: AND, OR, NOT, NAND, XOR, NOR. But we are only going to look at the three basic ones.
<!-- block -->

## Logic gates

![alt text](/images/AND.png "AND gate")
First up is the AND gate. It has two (or more) inputs and one output. The output is true (1) only if both inputs are true (1) as well. If either of the inputs are false (0), the output will also be false (0). 
“I’m only letting through electricity if the first input and the second input gives me electricity”

![alt text](/images/OR.png "OR gate")
Second we have the OR gate. Like the AND gate the OR gate has two (or more) inputs and one output. The output is true (1) if either of the inputs are true (1). So if one of the inputs are false (0) and the other one is true (1) the output is still true (1). The only time an OR gate outputs false (0) is if both inputs are false (0)
“I’m letting through electricity if the first input or the second input gives me electricity”

![alt text](/images/NOT.png "NOT gate")
Third is the NOT gate. It only has one input and one output. This logic gate simply inverts (negates) the input. If the input is true (1) then the output is false (0), and if the input is false (0) the output is true (1)
“I’m not going to do what I’m told. I will do the opposite!”


Now with only these logic gates you can do some pretty amazing things if you combine them in clever ways. First off we will create another common logic gate NAND. 

![alt text](/images/NAND-diagram.png "NAND gate diagram")
This is our NAND gate, or more descriptively NOT AND. We take a AND gate and connect a NOT gate after it, so it inverts the AND gate’s output. There is a symbol for NAND gate as well, just to simplify things:

![alt text](/images/NAND.png "NAND gate")

So why do we need this NAND gate? Well, with enough NAND gates we can create any logic circuit we want.

## Adding two binary digits together with logic gates
Normally in the decimal system (you know, the way we usually count, numbers 0-9 and all that) when we add two numbers together we go from right to left and carry over any value that is necessary. E.g. adding 13 and 19:
- Step 1: (3 + 9 = 12) (we carry the one into the next column).
- Step 2: (1+1+1 = 3)
- The answer: 32

So we want to build a circuit that is capable of adding two binary digits and handle the carry over in binary land. Below you will find a circuit that does that. It’s called a 1-bit Full Adder:

![alt text](/images/full-adder-diagram.png "Full adder diagram")

Don’t even worry if you find this very confusing, it’s okay. The point is just that we can combine transistors into logic gates and then combine these logic gates into something useful like a simple adder circuit. Think of it as a black box, put in two digits, get the output sum and the carry over, if there is any. 

![alt text](/images/full-adder-simple.png "Full adder")

Now, in modern computers we are dealing with larger numbers than 1-bit. Since the adder circuit is built to handle carry overs, we can chain multiple 1-bit adders into something that can handle much bigger numbers.

![alt text](/images/ripple-adder.png "Ripple adder")

This is what's called a ripple adder. A ripple adder is just a bunch of full adders chained together to handle bigger numbers. In this illustration the circuit can handle 4-bit numbers. A ripple adder is not the most effective adder, because the chaining causes a delay. You would find a similar adding circuit inside a Arithmetic Logic Unit (ALU). But hopefully more efficient. An ALU is the part of a processor that is responsible arithmetic and bitwise operations. You will for example find one in your Central Processing Unit (CPU) and your Graphics Processing Unit (GPU). 

## Lastly

The purpose of this article was to give you an overview of how computers *compute* using logic gates. You don't absolutely need to understand this to be able to program later on, but I find it helpful to have some general idea of what my computer code eventually is going to turn into and what is physically happening inside the computer. The next article will introduce programming at a very low level.