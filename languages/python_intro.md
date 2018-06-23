---
layout: page
title: Intro to Python
---

## Prologue
Because python comes in two flavors _Python_ and _Python 3_ here you are going to see what you can do with _Python 3_ which is more or less what you can do with other one but the syntax changes, a little. The reason why these two are diffrent is because, well, I don't know exactly. Pythoners are great developers, don't get me wrong, but for some reason there are still two diffrent versions of the same language. I try not to think about it before sleep.

Also keep in mind that here I will mention some of the basics like "how to assign a value to a variable" or "how to write loops" so how to write functions and the rest of it will be on the Reading Material which will be at the end of the page.

## Introduction
You can find programming languages for diffrent projects but Python does pretty much everything. An Object-Oriented programming language that you can use to build web applications, data analysis and even penetration testing. It's like the cool kid that everyone wants in their sports team and can play in every position. 

So, Python is a great programming language (according to me) and what now? Well, let's talk about... the syntax.

NOTE: Before we continue you will need to remember two things, packages/modules/libraries are pretty much the same thing when you are coding Python and that python need tabulates (tabs) when you are using conditionals and loops.


### Coding Syntax
Following there are some generel commands for you to start a scripted program. Something really simple.
```
# Import a module/library
import module

# Print variable
print(variable)

# Use a specific function from a module
module.function(parameters)

# Assign a value to a variable
variable=1

# Ask user for an input (as text/string)
variable=input('Input variable value here: ')

# Ask user for an input (as integer)
variable=int(input('Input variable value here: '))

# Conditionals
variable=int(input('Input variable value here: '))
if variable ==1:
    print ("variable=",variable)
elif variable==2:
    print ("variable=",variable)
else:
    print ("variable=","...somethin other than 1 or 2")

# Loops

# While loop
i=1
while i < 10:
    print(i)
    i=i+1

# For loop
for i in range(10):
    print(i)

# Create a dictionary
thisdict =	{
  "apple": "green",
  "banana": "yellow",
  "cherry": "red"
}

# Change a value to another value in a dictionary
thisdict =	{
  "apple": "green",
  "banana": "yellow",
  "cherry": "red"
}
thisdict["apple"] = "red"
```

### Operators
| Logical Operators       | Meaning        |
|:-------------:|:-------------:|
| ==     | exactly equal to |
| >      | greater than     |
| >= | greater than or equal to|
| <     | less than |
| <=     | less than or equal to|
| != | not equal to|
| not    | Not x |
| or | x OR y|
| and | x AND y|


| Arithmetic Operators       | Meaning        |
|:-------------:|:-------------:|
| +    | addition |
| -      | subtraction     |
| * | multiplication|
| /     | division |
| **   | exponentiation|
| //    | modulus (x mod y) 5%%2 is 1 |
| % | integer division 5%/%2 is 2|

| Assignment Operators       | Example        | Meaning
|:-------------:|:-------------:||:-------------:|
| =   | x = 5 | x = 5|
| +=     | x += 5| x = x + 5 |
| -= | x -= 5| x = x - 5 |
| *=     | x *= 5 | x = x * 5 |
| /=   | x /= 5| x = x / 5 |
| %=    | x %= 5 |x = x % 5 |
| //= | x //= 5|x = x // 5 |
| **=   | x **= 5 |x = x ** 5 |
| &=     | x &= 5|x = x & 5 |
| │= | x |= 5| x = x | 5|
| ^=     | x ^= 5 |x = x ^ 5 |

So now that we got all the basics out of the way let's go to some reading material.

## Reading material
+ [Introduction to Python (Codeacademy)](https://www.codecademy.com/learn/learn-python)
+ [Introduction to Python(W3schools)](https://www.w3schools.com/python/python_intro.asp)
+ [Python Applications](https://www.python.org/about/apps/)
