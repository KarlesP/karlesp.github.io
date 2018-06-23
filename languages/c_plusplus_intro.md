---
layout: page
title: Intro to C++
---
## Introduction
So C++ is a language that covers the applications of C for thank gods I have to do only one tutorial on it and not both C AND C++. Also you will need to remeber that both C and C++ are Object-Oriented, that means both C and C++ work like Python.

If you ever wondered about the applications of C and C++ look at your Operating System (OS). One of the most famous OS, Windows, is written in C and C++. Also MySQL, Mozilla Firefox, Adobe Systems and Gaming engines like Unity are written in that language.

## Coding Syntax
So, because C++ is a lower level language it differs from other languages like R or Python and because of that I won't try to create examples that parallel the ones from R and Python. Instead I am going to present a "Hello World" program, which is basically a "print" program, and then present some examples.

Note: In C++ every line of code ends with a semi-column ";"

```
// Load "iostream" library
#include <iostream>

/* Start main function, where you basically execution 
begins and int means that "main" function returns as it closes.
*/

int main()
{
/*The "<<" characters indicate that you want to send output to
the display, "std::cout" means "from library std take the function cout"*/
std::cout << "Hello World!";

//Return 0 to close the function main()
return 0;
}
```

### Examples

#### Simple User input-output
```
#include <string>
#include <iostream>
int main()
{
/* Display (print-out) the "Enter your full name: " and wait
for a string */
// Note: "cout" means "C output something"
std::cout << "Enter your full name: ";
std::string fullname;

// User input (as a text/string)
// Note: "cin" means "input in C"
std::getline(std::cin, fullname);

// Print-out (display) user's input
std::cout << "Your name is " << fullname ;
return 0;
}
```
#### Simple Calculation
```
/* Keep in mind that we are declaring the data-type 
of the variable */
int num1 = 5;
int num2 = 6;
int num3 = num1 * num2;
```

#### Conditionals

```
int num1 = 5;
int num2 = 6;
int result = num1 + num2;
if (result > 4 )
{
cout << “Result is greater than 4.”;
}e
lse if (result == 4)
{
cout << “Result is equal to 4.”;
}e
lse
{
cout << “Result is less than 4.”;
}
```

#### Loops

```
// While Loop
int count = 0;
while(count < 4)
{
cout << count << “\n”;
count++;
}

// For Loop
for (int count=0; count < 4; count++)
{
cout << count << " ";
}

// Do-While Loop
int count = 4;
do
{
// A simple print function
cout << count << “\n”;
// Add 1 every to our variable
count++;
}
while(count < 4);
```

#### Arrays

```
/* Name of our array is "numbers", "2" means
that we can store two things in
our array and int means that every thing
has to be an integer */
int numbers[2];

// Now let's fill these 2 places with "1" and "3"
numbers[0] = 1;
numbers[1] = 3;

// Populate array using a loop
int numbers[2];
for (int count = 0; count < 2; count++)
{
numbers [count] = count;
}

/* Create a structure named "Employee" with
different variables */
struct Employee
{
// Create objects
int id;
std::string firstname;
std::string lastname;
int birthyear;
};

// Make in a two variable array (meaning we have 2 employees)
Employee employees[2]
// Change employees to emp1
Employee emp1;
// Assign values to each object
emp1.id = 1;
emp1.firstname = “John”;
emp1.lastname = “Smith”;
emp1.birthyear = 2000;
employees[0] = emp1;
// Assign "emp1" as the first object of our array
employees[0] = emp1;
/* Print out the object "firstname" from the
first object from the array "employees" */
cout << employees[0].firstname;
``` 

#### Pointers
Pointers are values that can be found in our RAM...and yes, at first it makes _Zero sense_ but, bear with me, as I said before, here I will present to you examples because for now it will be the only thing that you will need (also I will have a whole page on Pointers in the reading material because you will have to see examples from an IDE to understand completely what they are and how they work)

```
int mynumber = 5;

/* What comes out the following line is the value of the pointer (yes the one with the numbers and the letters) and the other is the value of the variable "mynumber" */
int *ptr = &mynumber;

// To be more specific
int mynumber = 5;
int *ptr = &mynumber;
cout << mynumber; //prints 5
cout <<*ptr; //prints 5
cout << ptr; //prints 0012FFF7C
cout << &mynumber; //prints 0012FFF7C
```
#### Functions
So we mentioned before how we can understand a function but below you will find a quick recap

```
#include <iostream> // library
void calculate() // function calculate returns nothing (void)
{
int int1 = 5; // variable 1
int int2 = 5; // variable 2 
if (int1 == 5) // simple conditional
{
return; // return nothing if someting went wrong
}
cout << int1 + int2; // calculation and then print the result
}
```

## Reading material
+ [Basic Tutorials from the officiacl C++](http://www.cplusplus.com/doc/tutorial/)
+ [Pointers](http://www.cplusplus.com/doc/tutorial/pointers/)
+ [C++ examples](https://www.programiz.com/cpp-programming/examples)
+ [Snake game with C++](http://cplusplus.happycodings.com/computer-graphics/code24.html)
+ [Online C++ Compiler](http://cpp.sh/)
