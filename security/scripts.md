---
layout: page
title: Pentesting with Scripts
---

## Introduction
Before we begin anything let's tecap Pentesting's 5-core steps:

1. Scan a system for vulnerabilities
2. Exploit those vulnerabilities
3. Create a connection (Backdoor)
4. Maintain that connection
5. Secure the system and delete the backdoor

Understanding those 5 steps you'll start to realise that you _might_ be able to automate some of those and spare you some time. That is why I made this page, to tell you that you can do that using a scripting language.

## Python
If you are looking for a toolbox and you don't know much about coding Python is a great start. That is because Python is a high level language which means that it is easy to read.

### Tools
When looking to Python for pentesting you got to look on GitHub,to be more precise there is a Git that covers every resource that you might need when it comes to it and that is [dloss's Repo](https://github.com/dloss/python-pentest-tools) which gives you access to a great number of Python sources.

### Example
You can find an example code for a simple packet sniffer [here](/security/python_example.md) which you can execute directly from your Python IDE. 

The version that you will see in this example is 2.7 and the example can be found from Justin Seitz' book _"Black Hat Python: Python Programming for Hackers and Pentesters"_ which I highly recommend for a deep dive to Pentesting.

## Perl
Like Python, Perl is an easy to read language but because it is older than Python it has been used more by the Pentest community and so most of the tools that you will find for Pentesting they are written, or at least they were written, in Perl.

If you really want to write with Pearl I will provide a source for that.

### Tools
Perl's pentesting tools are so many that there is a single repository called CPAN (Comprehensive Perl Archive Network) that hosts all of them. If you want to find out about them go to the official [CPAN website](https://www.cpan.org/) to take a look at the list.

### Example
You can find an example code for a simple BruteForce cracking using SHA1 hashes [here](/security/perl_example.md)

## Shellscript
If you ever wandered how to execute code without an IDE on Linux, then look no further, Shellscript is just for you, simply create a file in .sh format, open it with an editor and at the begining of the file write _#!/bin/env python_ to execute a python script or _#!/bin/env perl_ to execute a Perl script or _#!/bin/env python3_ to execute a Python 3 script. The idea is to give the directory of the said enviroment and below that line execute the code that you have written.

## Reading Material
+ [Introduction to Perl](https://www.perl.com/pub/2000/10/begperl1.html/)
+ [Introduction to Python](https://wiki.python.org/moin/BeginnersGuide/Programmers)
+ [Intorduction to Shellscript](https://www.shellscript.sh/)
+ [Courses on Pentesting](http://www.pentesteracademy.com/topics)
