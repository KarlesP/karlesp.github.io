---
layout: page
title: Machine Learning Using (Python Script)
---

Imports:
```
# Load libraries
import pandas
from pandas.plotting import scatter_matrix
import matplotlib.pyplot as plt
from sklearn import model_selection
from sklearn.metrics import classification_report
from sklearn.metrics import confusion_matrix
from sklearn.metrics import accuracy_score
from sklearn.linear_model import LogisticRegression
from sklearn.tree import DecisionTreeClassifier
from sklearn.neighbors import KNeighborsClassifier
from sklearn.discriminant_analysis import LinearDiscriminantAnalysis
from sklearn.naive_bayes import GaussianNB
from sklearn.svm import SVC

# Load dataset
url = "https://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data"
names = ['sepal-length', 'sepal-width', 'petal-length', 'petal-width', 'class']
dataset = pandas.read_csv(url, names=names)
```
Statistical results:
```
# Dimensions of the dataset
print(dataset.shape)

# Printing out the first 20 rows of that dataset
print(dataset.head(20))

# Printing out a statistical summary of those 20 rows
print(dataset.head(20))

# Class distribution of our values
print(dataset.groupby('class').size())

# Scatter plot matrix
scatter_matrix(dataset)
plt.show()
```
Machine Learning:
```
# Split-out validation dataset (80% testing, 20% validation)
array = dataset.values
X = array[:,0:4]
Y = array[:,4]
validation_size = 0.20
seed = 7
X_train, X_validation, Y_train, Y_validation = model_selection.train_test_split(X, Y, test_size=validation_size, random_state=seed)

# Test options(random seed) and evaluation metric(accuracy of classification)
seed = 7
scoring = 'accuracy'

# Load models Linear Reggression, LDA, KNN, Decision Tree Clasifier, GaussianNB and Support vector machine(SVM)
models = []
models.append(('LR', LogisticRegression()))
models.append(('LDA', LinearDiscriminantAnalysis()))
models.append(('KNN', KNeighborsClassifier()))
models.append(('CART', DecisionTreeClassifier()))
models.append(('NB', GaussianNB()))
models.append(('SVM', SVC()))

knn=KNeighborsClassifier()
lr=LogisticRegression()
lda=LinearDiscriminantAnalysis()
cart=DecisionTreeClassifier()
nb=GaussianNB()
svm=SVC()

# Create a dictionary for user input
models_dict=  {knn,lr,lda,cart,nb,svm}

# Evaluate each model in turn
results = []
names = []
for name, model in models:
	kfold = model_selection.KFold(n_splits=10, random_state=seed)
	cv_results = model_selection.cross_val_score(model, X_train, Y_train, cv=kfold, scoring=scoring)
	results.append(cv_results)
	names.append(name)
	msg = "%s: %f (%f)" % (name, cv_results.mean(), cv_results.std())
	print(msg)

# Compare Algorithms
fig = plt.figure()
fig.suptitle('Algorithm Comparison')
ax = fig.add_subplot(111)
plt.boxplot(results)
ax.set_xticklabels(names)
plt.show()

# Chosing the best one using the user input command and using the dictionary
while True:
   quest=eval(input("What is the best classifier? "))
   if quest not in models_dict:
    print("Model not found.")
   else:
    break

# Make predictions on validation dataset
quest.fit(X_train, Y_train)
predictions = quest.predict(X_validation)
print(accuracy_score(Y_validation, predictions))
print(confusion_matrix(Y_validation, predictions))
print(classification_report(Y_validation, predictions))
```
