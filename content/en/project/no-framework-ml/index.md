---
title: Machine Learning with No Frameworks - Logistic Regression
subtitle: ""
date: 2022-05-10T08:00:00.024Z
summary: Implementation of Machine Learning model without using libraries or frameworks for machine learning or advanced statistics. 
draft: false
featured: false
tags:
  - 1
  - 6
  - Python
  - Neural Network
external_link: ""
# 
image:
  filename: featured.png
  focal_point: Smart
  preview_only: false
---

## Overview
Machine Learning model of Logistic Regression, made from scratch without using frameworks nor libraries for machine learning or advanced statistics.

Only libraries used are **pandas** for the data reading and manipulation, and **numpy** for math and np arrays.

## Tools
For the creation of this project, the tools that were mainly used were:
+ Python: To write the Logistic Regression
+ Pandas: For data reading and manipulation
+ Numpy: For math and np arrays

## Final Product:
You can find the .py file in the following repository with the code manual implementation.
[Github Link](https://github.com/lcanoi/MachineLearning_NoFrameworks)

<br/>

## The Solution
I selected to solve a simple multiclassification problem, the [iris dataset](https://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data). Here we have 4 attributes/variables and 3 different classes/flower species.
This problem is solved with Logistic Regression and sigmoid activation function. For this to work in multiclassification, I make a rows * classes onehot matrix for the output, where each line has a 1 and two 0s, their possition representing the species the flower belongs to.
Likewise, we use a variables * classes matrix for the weights and a 1 * classes array for the bias/error.

#### Logistic Regression Model
We train the model in the following loop for "range(epochs)" epochs:
```
'''
for epoch in range(epochs):
    for i, x in enumerate(x_train):
        # Forward Propagation
        # Calculate activation
        z = np.dot(x, weights) + bias
        a = sigmoid(z)

        # Backward Propagation
        # Calculate gradient derivatives
        error = a - onehot[i]
        d_grad_w = np.dot(x.reshape(-1,1), error.reshape(1,-1))
        d_grad_b = error

        # Update weigths and bias
        weights -= lr * d_grad_w
        bias -= lr * d_grad_b
'''
```
#### Predictions
We can make predictions like this:
```
y_pred = []
for i in range(len(x_test)):
    z = np.dot(x_test[i], weights) + bias
    a = sigmoid(z)
    y_pred.append(np.argmax(a))
```

#### Accuracy
And we can see the accuracy by calculating correct predictions / total predictions, as well as by analizing the confusion matrix
```
# Accuracy
print("\n\n Final Test Accuracy: ", np.sum(y_pred == y_test)/len(y_test), "\n\n")

# Confusion Matrix
print("Confusion Matrix\n________________\n")
print(pd.crosstab(y_test_rf, y_pred_rf, rownames=['Real'], colnames=['Predictions']))
```
