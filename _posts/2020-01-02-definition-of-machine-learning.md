---
date: 2020-01-02 14:01:00
layout: post
title: Definition of Machine Learning.
subtitle: Basic introduction and definition
description: >-
  Basic concepts of machine learning.
image: >-
  https://res.cloudinary.com/dm7h7e8xj/image/upload/v1559821647/theme6_qeeojf.jpg
optimized_image: >-
  https://res.cloudinary.com/dm7h7e8xj/image/upload/c_scale,w_380/v1559821647/theme6_qeeojf.jpg
category: Reading
tags:
  - machine learning
author: Alex
---

## Formal Definition

> A computer program is said to learn from experience E with respect to some class of tasks T and performance measure P, if its performance at tasks in T, as measured by P, improves with experience E. —— Tom Mitchell

In other words:
* _E_ is the repeated experiences
* _P_ is the measured data
* _T_ is the task

As a result of machine learning, the computer program can perform better in _T_ based on _P_, with iterations _E_.

## Type

### Supervised Learning
A relationship between the input and the output exists in _Supervised Learning_. Problems can be divided into two categories:
* **Regression**: continuous function. Outputs can be _predicted_ based on inputs - eg. Predict the age of a person based on pictures.
* **Classification**: also called 'discrete'. Outputs will be separated into distinct categories instead of predicting the their specific values - eg. Predict will a person be bald based on pictures.


### Unsupervised Learning
In Unsupervised learning, we will process data sets with no label/same labels rather than predict results.

* **Clustering Algorithm**: Decide data into different clusters. eg. News about the same topic from different newspapers.
* **Cocktail Party Algorithm**: Non-Clustering. Separate overlapping voices/audios.

## Important:

The difference between _Clustering_ and _Classification_:

In _Classification_, before processing any data, the definition of each class will be decided first. eg: Group fruits into apples, bananas, and oranges based on given pictures.

Instead, in _Clustering_, classes will not be pre-defined. Data will be divided into different groups by detecting similar features. eg: Group fruits of similar types based on given pictures.

Also, once you've **labelled** the data, it will be treated as _Supervised Learning Problem_.

## Model
Notations:
* _x_: input
* _y_: output
* _x<sup>(i)</sup>_, _y<sup>(i)</sup>_: the i-th input/output
* _(x,y)_: the training set / a signle training example
* _X_: the space of input values
* _Y_: the space of output values
* _h_: hypothesis. The function that takes the input and gives the prediction, denoted as _h: X→Y_.

### Supervised Learning - Linear Regression
**Definition**: By given a real-valued input, we will predict a real-valued output, denoted as _hθ(x) = θ₀ + +θ₁x_. eg. predict housing prices of based on their sizes.

**Cost Function**: Measure the accuracy of _h_ by taking an average difference of _hθ(x)_ and _y_. The purpose of the _cost function_ is to find parameters which minimize the cost function.

* **Squared error cost function**: Calculated by: the sum of _(hθ(x<sup>(i)</sup>) - y<sup>(i)</sup>)<sup>2</sup>_ times _1/2m_, where _m_ is the number of training examples, denoted by _J(θ₀,θ₁)_.


## Reference:
1. [Coursera](https://www.coursera.org/learn/machine-learning/supplement/d5Pt1/lecture-slides)
2. [Difference Between Clustering and Classification](https://www.differencebetween.com/difference-between-clustering-and-vs-classification/)
