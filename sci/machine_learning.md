---
layout: page
title: Machine Learning
---
## Introduction 
In 1959 researchers from diffrent fields were conducting AI expirements where the machine (a computer) was learning through partitions (parts) of dataset, that way they were able to test statistical models and their accuracy against real problems. Back then they named those methods _Neural Networks_ and after a while, a guy named Arthur Samuel named that branch more appropriately _Machine Learning_. Furthermore Machine Learning is closely related to Statistics whereas Machine Learning has algorithmic models, Statistics has data models.

## Practical Machine Learning
Now that I mention where the name _Machine Learning_ came from let's get this out of the way; Machine Learning is a field which has a set of tools, with those tools you can divide a dataset into "training" data and "testing/validation" data. Usually we use a big portion, about 80% of the main dataset to let our machine learn and then we validate what it learned against the remaining data, usually the rest 20%. 

When we are using Machine Learning methods we need to remember that we are letting the machine to learn, so if we use 90% for the training data and 10% for the testing data sometimes it's fine, but 99% training and 1% testing it's borderline useless because we need to distinguish the mistakes that the machine would make so if our results don't differ much, using statistical errors and whatnot, between 90% testing and 80% testing we go with 80% testing.

### Examples using R and Python

#### Using Python
[Python Example](machine_learning_python)

#### Using R
[R Example](machine_learning_r)

## Epilogue
Machine Learning has a lot of applications and depending on what you want from it you'll have to modify the codes above. But it's an amazing concept and if done correctly can give fast and efficient predictions.
