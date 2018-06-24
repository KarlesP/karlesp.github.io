## Introduction
So Java is a "general-purpose computer-programming language that is concurrent, class-based, object-oriented, and specifically designed to have as few implementation dependencies as possible" according to Wikipedia. 
Let's see what that means:

+ **General purpose** means lots of applications, from OS to Web.

+ **Object-Oriented** means it uses objects with attributes, think of it like a table with multiple columns.

+ **Class-based** means that it uses classes instead of attributes for it's objects.

+ **Few implementation dependencies as possible** means less changes between language updates.

So let's do a little recap. Java is a language that was made to be used in multiple systems, is Object-Oriented and its code will stay pretty much the same no matter how much time has it passed since you left that Java file in your computer.

Now, let's talk about the coding syntax and how to execute it.

## Coding Syntax
To execute code in Java you'll need a Java Virtual Machine (JVM) and a java compiler (javac). In Java, every source file usually contains exactly one class. The file must have the same name as the class; a class named TurtleMaze would be stored in the source file *TurtleMaze.java*. This source file can then be compiled using the javac compiler:
```
% javac TurtleMaze.java
```

If you have to recompile multiple Java files javac has a special option to do just that 
```
% javac -depend TurtleMaze.java
```
that way you can recompile a file and every other file that depends it depends upon

### Simple Declerations
Java uses declerations, like C++, because is a "dumb" language, that means that it doesn't understand the datatype of a value when it is used in an object.

```
int m, n; // Two integer variables
double x, y; // Two real coordinates
boolean b; // Either ‘true’ or ‘false’
char ch; // A character, such as ‘P’ or ‘@’
```
### Numeric Expressions
Below are some numeric expressions
```
y = 1
n = 3 * (5 + 2);
x = y / 3.141592653;
n = m % 8; // Modulo, i.e. n is now (m mod 8)
b = true;
ch = 'x';
```

You can also declare as you assign a value

```
double f = 0.57; 
boolean flag = true;
```
Note: Division (/) can do both integer and real numbers

```
double f;
f = 1 / 3; // f is now 0.0
f = 1.0 / 3.0; // f is now 0.33333333
```

### Type Conversion
Because Java is a "dumb" language we have to do type conversions by hand

```
double radians = 30.6;
int degrees;
degrees = radians * 180 / 3.141592653; // Error
degrees = (int) (radians * 180 / 3.141592653); // OK
``` 

### Conditionals

```
int testscore = 76;
        char grade;

        if (testscore >= 90) {
            grade = 'A';
        } else if (testscore >= 80) {
            grade = 'B';
        } else if (testscore >= 70) {
            grade = 'C';
        } else if (testscore >= 60) {
            grade = 'D';
        } else {
            grade = 'F';
        }
        System.out.println("Grade = " + grade);
    }
```

### Loops

+ While loop

```
// Calculate exp(1). End when the term is less than 0.00001
double sum = 0.0;
double term = 1.0;
int k = 1;
while (term >= 0.00001) {
 sum = sum + term;
 term = term / k;
 k++; // Shortcut for ‘k = k + 1’
}
```

+ For loop

```
// Calculate 1 + (1/2) + (1/3) + ... + (1/100)
int i;
double sum = 0.0;
for (i = 1; i <= 100; i++) {
 sum = sum + 1.0 / i;
}
```
### Objects
The first line creates a class named "Turtle" as "t" and the second lines creates an object Turtle with the "new" operator and assigns coordinates x and y as (100,100)
```
Turtle t; 
t = new Turtle(100, 100);
```

### Classes
A class declaration typically contains a set of attributes (sometimes called instance variables) and functions (called methods in Java).

```
class Turtle {
private boolean penDown;
protected int x, y;
// Declare some more stuff
}
```

### Methods
In Java, functions and procedures are called methods

```
class Turtle {
// Attribute declarations, as above
public void jumpTo(int newX, int newY) {
 x = newX;
 y = newY;
 }
public int getX() {
return x;
 }
}
```
### Inheritance and the "main" method
In order to declare a subclass of another class we use the *extends* keyword in the class declaration

```
class NinjaTurtle extends Turtle {
// Declarations for Ninja turtles
}
```

if we want to create a superclass with parameters:

```
public NinjaTurtle(int initX, int initY, String name) {
super(initX, initY); // Call superclass’ constructor
// ... do some more initialization stuff...
}
```

As for the _main_ method, it usually creates a few objects and does some small work to get things
going. For Turtle a simple main method may look as follows:

```
public static void main(String[] args) {
 Turtle t = new Turtle(100, 200);
 t.right(90);
while (t.getX() < 150) {
 t.forward(2);
 }
}
```

### Arrays 
So Java can use arrays, an example follows

```
class ArrayDemo {
    public static void main(String[] args) {
        // declares an array of integers
        int[] anArray;

        // allocates memory for 10 integers
        anArray = new int[10];
           
        // initialize first element
        anArray[0] = 100;
        // initialize second element
        anArray[1] = 200;
        // and so forth
        anArray[2] = 300;
        anArray[3] = 400;
        anArray[4] = 500;
        anArray[5] = 600;
        anArray[6] = 700;
        anArray[7] = 800;
        anArray[8] = 900;
        anArray[9] = 1000;

        System.out.println("Element at index 0: "
                           + anArray[0]);
        System.out.println("Element at index 1: "
                           + anArray[1]);
        System.out.println("Element at index 2: "
                           + anArray[2]);
        System.out.println("Element at index 3: "
                           + anArray[3]);
        System.out.println("Element at index 4: "
                           + anArray[4]);
        System.out.println("Element at index 5: "
                           + anArray[5]);
        System.out.println("Element at index 6: "
                           + anArray[6]);
        System.out.println("Element at index 7: "
                           + anArray[7]);
        System.out.println("Element at index 8: "
                           + anArray[8]);
        System.out.println("Element at index 9: "
                           + anArray[9]);
    }
} 
```

the output here will be:

```
Element at index 0: 100
Element at index 1: 200
Element at index 2: 300
Element at index 3: 400
Element at index 4: 500
Element at index 5: 600
Element at index 6: 700
Element at index 7: 800
Element at index 8: 900
Element at index 9: 1000
```

### Examples
Minesweeper

```
public class MineSweeper
{	private int[][] myTruth;
	private boolean[][] myShow;
	
	public void cellPicked(int row, int col)
	{	if( inBounds(row, col) && !myShow[row][col] )
		{	myShow[row][col] = true;
		
			if( myTruth[row][col] == 0)
			{	for(int r = -1; r <= 1; r++)
					for(int c = -1; c <= 1; c++)
						cellPicked(row + r, col + c);
			}	
		}
	}
	
	public boolean inBounds(int row, int col)
	{	return 0 <= row && row < myTruth.length && 0 <= col && col < myTruth[0].length;
	}
}
```

Triangle area calculator

```
import java.util.Scanner;
class AreaTriangleDemo {
   public static void main(String args[]) {   
      Scanner scanner = new Scanner(System.in);

      System.out.println("Enter the width of the Triangle:");
      double base = scanner.nextDouble();

      System.out.println("Enter the height of the Triangle:");
      double height = scanner.nextDouble();

      //Area = (width*height)/2
      double area = (base* height)/2;
      System.out.println("Area of Triangle is: " + area);      
   }
}
```
Simple user inputs

```
import java.util.Scanner;

class GetInputData
{
  public static void main(String args[])
  {
     int num;
     float fnum;
     String str;
 
     Scanner in = new Scanner(System.in);
 
     //Get input String
     System.out.println("Enter a string: ");
     str = in.nextLine();
     System.out.println("Input String is: "+str);
 
     //Get input Integer
     System.out.println("Enter an integer: ");
     num = in.nextInt();
     System.out.println("Input Integer is: "+num);
 
     //Get input float number
     System.out.println("Enter a float number: ");
     fnum = in.nextFloat();
     System.out.println("Input Float number is: "+fnum); 
  }
}
```

Because Java is an old language it has so much to read about, so below is some reading material to cover some of the questions that you may have and some examples.

## Reading material
+ [Oracle's Basics of Java](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/index.html)
+ [Java for beginners](https://beginnersbook.com/java-tutorial-for-beginners-with-examples/)
+ [Learn Java by examples](https://www.cs.utexas.edu/~scottm/cs307/codingSamples.htm)
+ [Java in 21 minutes](http://fileadmin.cs.lth.se/cs/Education/EDA040/common/java21.pdf)