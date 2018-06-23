---
layout: page
title: Brainf*ck 
---

## Introduction

### History
So, there was this guy in 1993 named Urban Müller who wanted to write a compiler for Amiga OS 2.0 which was an operating system for a computer named Amiga 3000 back in 1990. His main goal was to write the shortest compiler which achieved using only 240-bytes.

### About the language
The language is another esolang, but don't be fooled, Brainf* ck is more applicable than Malbolge and Deadfish. But, again, as an esolang it's a really weird language and it needs an interpeter. Well, Brainf* has Self-Interperters which means that it doesn't actually need other languages.

Brainfuck operates on an array of memory cells, also referred to as the tape, each initially set to zero. There is a pointer, initially pointing to the first memory cell. Now, if you don't know, a pointer is a data type that is used to store a memory address, or a value of such a data type. 

Now let's see how we can write Brain*fck


| Tables        | Are                                         |
| ------------- |:-------------------------------------------:| 
| > |Move the pointer to the right                           |
| < |Move the pointer to the left                            |
| + |Increment the memory cell under the pointer             |
| - |Decrement the memory cell under the pointer             |
| . |Output the character signified by the cell at the pointer|
| , |Input a character and store it in the cell at the pointer|
| [ |Jump past the matching ] if the cell under the pointer is 0|
| ] |Jump back to the matching [ if the cell under the pointer is nonzero|


### Examples (from Wikipedia)
Hello World:
```
++++++++[>++++[>++>+++>+++>+<<<<-]>+>+>->>+[<]<-]>>.>---.+++++++..+++.>>.<-.<.+++.------.--------.>>+.>++.
```

This code piece moves the value of the current cell (cell0) two cells to the right (cell2):
```
>>[-]<<[->>+<<]
```

## Epilogue
So, if you want to learn Brainf* ck by all means do it, it's Turing-complete, meaning that it is in the same computational class as universal Turing machines. I didn't know about Brainf*ck until I read about from it's wiki page and I believe that there is more but honestly I'm writing about this language because I believe that is the most underappreciated esoteric language (not that the others should be appreciated in any way).
