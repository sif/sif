---
layout: post
title: "Data Science"
categories: data
tags: data applied_statistics
---

* TOC
{:toc}

- Create or train ML models



Clustering
Decision Trees
Random Forest
Naïve Bayes
Q-Learning
Time Series



- Split train test
- Put data into ML to create a model
- So, to decide if a photo is of a dog or a cat, need a training phase and testing phase to see learn how to do it
- Collect many dog and cat photos
- That data must then be split into training set and testing set

<img src="https://github.com/sif/sif/raw/main/files/post_files/training.png" />

- Two data set in this case, X will be the independent features, Y will be the dependent variables
- The formula to split it is x Train - x Test / y Train - y Test
- x Train and y Train are used to create the model

- Once the model is created, input x Test and the output should be equal to the y Test
- The more closely the model output is to y Test, the more accurate the model is

- Supervised learning methods
- Tree based learning algorithms

- Gradient descent is the most used learning algorithm, there are many variants of gradient descents
- Gradient descent requires a cost function, there are many types of cost functions
- We need the cost function because we want to minimize it
- Minimizing any function means finding the deepest valley in that function
- Cost function is used to monitor error in prediction of a ML model
- So, minimizing this means reducing the error or increasing the accuracy of the model

Decision tree algorithms are referred to as CART (Classification and Regression Trees), the possible solutions to a given problem emerge as the leaves of a tree, each node representing a point of deliberation and decision

Decision tree model is a flowchart like structure in which each internal node represents a test on attribute (example: whether a coin comes up head or tail), each branch represents the outcome of the test and each leaf node represents a class label (decision taken after computing all attributes), the paths from root to leaf represents classification rules

Use cases:

- When user is trying to achieve maximum profit, optimize cost
- When there are several courses of action
- Calculate measure of benefit of the various alternatives
- When there are events beyond the control of decision makers (such as environmental factors)
- Uncertainty concerning which outcome will actually happen

- Overfitting is more common than underfitting
- Overfitting means that the model is too well trained and fit too closely to the training dataset
- Overfitting means that the model is too complex, underfitting means the model is too simple

- To avoid overfitting, the data can’t have too many features/variables compared to the number of observations
- To avoid underfitting, the data need enough predicators/independent variables

accuracy_score() takes two arguments, first is the test data labels (actual labels) and then the model’s prediction

Example:

```
accuracy = accuracy_score(y_test, predictions)
```

brew install graphviz (not pip)



## TensorFlow

Graphs

Neural Network

Regression

Classification


