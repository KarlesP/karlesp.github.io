---
layout: page
title: Machine Learning Using (R Script)
---

Imports:
```
# Install "caret" whith its dependencies
install.packages("caret", dependencies=c("Depends", "Suggests"))
library(caret)

# Load the iris dataset to a variable named "dataset"
dataset=datasets::iris
```

Statistical Results:
```
# Statistical summary
summary(dataset)
# Dimensions of our data
dim(dataset)
# List types for each attribute 
sapply(dataset, class)	
# Printing out the first 20 rows of the data
head(dataset,20)
# List the levels for the class
levels(dataset$Species)
# summarize the class distribution
percentage <- prop.table(table(dataset$Species)) * 100
cbind(freq=table(dataset$Species), percentage=percentage)
```
Plotting:
```
# Scatterplot matrix
featurePlot(x=x, y=y, plot="ellipse")
# Simple plot
plot(dataset)
```

Machine Learning:
```
# create a list of 80% of the rows in the original dataset we can use for training
validation_index <- createDataPartition(dataset$Species, p=0.80, list=FALSE)
# select 20% of the data for validation
validation <- dataset[-validation_index,]
# use the remaining 80% of data to training and testing the models
dataset <- dataset[validation_index,]

# Run algorithms using 10-fold cross validation
control <- trainControl(method="cv", number=10)
metric <- "Accuracy"

# Algorithmic Models
# a) linear algorithms
set.seed(7)
fit.lda <- train(Species~., data=dataset, method="lda", metric=metric, trControl=control)
# b) nonlinear algorithms
# CART
set.seed(7)
fit.cart <- train(Species~., data=dataset, method="rpart", metric=metric, trControl=control)
# kNN
set.seed(7)
fit.knn <- train(Species~., data=dataset, method="knn", metric=metric, trControl=control)
# c) advanced algorithms
# SVM
set.seed(7)
fit.svm <- train(Species~., data=dataset, method="svmRadial", metric=metric, trControl=control)
# Random Forest
set.seed(7)
fit.rf <- train(Species~., data=dataset, method="rf", metric=metric, trControl=control)

# Compare summary of the models
results <- resamples(list(lda=fit.lda, cart=fit.cart, knn=fit.knn, svm=fit.svm, rf=fit.rf))
summary(results)

# Compare accuracy of models
dotplot(results)

# Let the user choose the best model
repeat{
usr_input=readline("Type in the best model (lda/rpart/cart/knn/svm/rf):")
if (usr_input == "lda" || usr_input == "cart" || usr_input == "knn" || usr_input == "rpart" || usr_input == "svm" || usr_input == "rf"){
  break()
}else{
  print("You gave wrong model, repeat process")
}
}
b_m=get(paste0('fit.', usr_input,sep=""))

# Summarize Best Model
print(b_m)

# Estimate skill of LDA on the validation dataset
predictions <- predict(fit.lda, validation)
confusionMatrix(predictions, validation$Species)
```
