---
layout: page
title: Introduction to R
---
## Prologue
So R is a programming language that gets a bad wrap because some people support that it is not a programming language.
That isn't exactly the case. Now, R is a scripting language and it does support Object-Orinented Programming and is compatible with
languages like Python and C++. Now that we got this out of the way, let's begin.

## Introduction
A quick and dirty introduction with R would be the following:

+ It is used *MOSTLY* for its statistical functions.
+ Using its libraries correctly you can make R a multi tool, from basic analysis to web application development (using Shiny).
+ R is also a great choice for ELT and ETL techniques with both NoSQL and SQL databases.

That being said there are a few things that I haven't mentioned here because R's official page, [CRAN](https://cran.r-project.org/doc/FAQ/R-FAQ.html) talks about them in a more extensive matter.

### Coding syntax
R is a pretty simple language. Functions have parenthesis "()", columns can be selected with the dollar sign "$", object are selected using the at sign "@" and loops and conditionals don't need tabulate.

So wihtout further ado, here are some of it's commands:

```
# Remove variable from enviroment
rm(variable)

# Create variable (1)
variable=1

# Create variable (2)
variable<-1

# Print the value of that variable
print(variable)

# Ask user for an input (as text/string)
variable=readline("Input variable here: ")

# Ask user for an input (as numeric)
variable=as.numeric(readline("Input variable here: "))

# Conditionals

# Create a conditional with 3 scenarios
if (variable==1){
    print("hello")
} else if (variable==2){
    print("not hello")
} else{
    print("something other than 'not hello'")
}

# Loops
# Note: all three do the exact same thing

# Create a 'for' loop
for(i in 1:10) {
  print(i)
}
# Create a 'repeat' loop
i=1
repeat{
  if (i<=10){
    print(i)
    i=i+1
  } else {
    break
  }
}
# Create a 'while' loop
i=1
while(i <= 10){
  print(i)
  i=i+1
}
```
### Operators
Now if you are wandering about R's operators you should read the following table:


| Logical Operators       | Meaning        |
|:-------------:|:-------------:|
| ==     | exactly equal to |
| >      | greater than     |
| >= | greater than or equal to|
| <     | less than |
| <=     | less than or equal to|
| != | not equal to|
| !x    | Not x |
| x │ y | x OR y|
| x & y | x AND y|
| isTRUE(x)    | test if X is TRUE |


| Arithmetic Operators       | Meaning        |
|:-------------:|:-------------:|
| +    | addition |
| -      | subtraction     |
| * | multiplication|
| /     | division |
| **   | exponentiation|
| ^ | exponentiation (2)|
| x %% y    | modulus (x mod y) 5%%2 is 1 |
| x %/% y | integer division 5%/%2 is 2|


Below you will find some code examples for you to test R.
## Examples

### Statistical Analysis
To use methods of statistical Analysis it would take **SO MUCH TIME** and frankly you don't have that much time. So let's start with some examples and hope that you will learn quickly your way around [this page](https://cran.r-project.org/web/packages/available_packages_by_name.html).


Fist we load Edgar Anderson's Iris Data, one of the most famous datasets for analysis. If you don't want to load the iris dataset there are a lot out there but this is one of the most common and it comes prepacked with multiple languages.
```
#Load dataset
dataset=iris
```
And now we will start a simple analysis. That being said, we will print out every column name of our data, do a simple summary, use a matrix-plot for our data and create a boxplot.
```
colnames(dataset)
summary(dataset)
plot(dataset)
boxplot(dataset)
```
If you have executed the above code you will see that the summary outputs diffrent statistics for our data, now you can see for example that the minimum value for *Petal.Length* is "1". As for our plots you can pretty much understand how the values correlate between columns (variables) by carefully studying the matrix-plot and how the values 'spread-out' from the boxplot.

Now we will showcase some multivariate analysis using clusters and regressions.

### Multivirate Analysis
Multivirate analysis is a really big branch of Statistics and if you are new to it it's 80% studying and 20% coding examples. But for now I will show you an example as if you knew about it and you just want to do a linear regression and a simple cluster analysis
#### Linear Regression
Following I am showing you an example of linear regression using the iris dataset.
```
# Load dataset
dataset=iris
# Assign values to x and y
x=dataset$Sepal.Length
y=dataset$Sepal.Width
# Create a linear model using x and y
lm(x~y)
# Plot the result
plot(y,x,col = "blue", abline(lm(x~y)),cex = 1.3,pch = 16)
```
#### Cluster analysis
Now that we closed Linear regression just copy-paste the Cluster analysis example and see what happens.
```
# Load the data
dataset=iris
# Assign a kmeans result to the "irisCluster" using iris' third to fourth columns as data, 3 centers and 20 random sets.
irisCluster <- kmeans(iris[, 3:4], 3, nstart = 20)
irisCluster
table(irisCluster$cluster, iris$Species)
irisCluster$cluster <- as.factor(irisCluster$cluster)
```
### Big Data
Using the same hardware and excluding big data technologies, like Hadoop, there are 3 ways to handle Big Data; Sampling, Aggregation, Multiprocess. Here I will show you all 3 of those using a few lines in R.

#### Sampling
Sampling is pretty simple, there is the range of the data and then there is the amount of samples.
```
# Load mtxars dataset
attach(mtcars)
# Sample 10 values from our dataset
sample(mtcars,10)
```
#### Aggregation
The general idea of aggregation is to lower the dimensions of a dataset so the process takes less time. Now if you were to lower the dimensions of a table (matrix, data.frame, etc) you would have to use a function to calculate the new values based on the old ones. Here I use as an example the "mtcars" dataset and the mean function. 
```
# Load mtxars dataset
attach(mtcars)
# Aggregate dataset using 2 columns and the mean function
aggdata <-aggregate(mtcars, by=list(cyl,vs), FUN=mean, na.rm=TRUE)
# Print results
print(aggdata)
```