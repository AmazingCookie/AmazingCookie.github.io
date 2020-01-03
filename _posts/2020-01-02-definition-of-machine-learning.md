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
paginate: true
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

### Important:

The difference between _Clustering_ and _Classification_:

In _Classification_, before processing any data, the definition of each class will be decided first. eg: Group fruits into apples, bananas, and oranges based on given pictures.

Instead, in _Clustering_, classes will not be pre-defined. Data will be divided into different groups by detecting similar features. eg: Group fruits of similar types based on given pictures.

Also, once you've **labelled** the data, it will be treated as _Supervised Learning Problem_.

## Model
**Notations**:
* _x_: input
* _y_: output
* _x<sup>(i)</sup>_, _y<sup>(i)</sup>_: the i-th input/output
* _(x,y)_: the training set / a signle training example
* _X_: the space of input values
* _Y_: the space of output values
* _h_: hypothesis. The function that takes the input and gives the prediction, denoted as _h: X→Y_.

### Linear Regression
**Hypothesis Function**: By given a real-valued input, we will predict a real-valued output, denoted as _h<sub>θ</sub>(x) = θ₀ + +θ₁x_. eg. predict housing prices of based on their sizes.

**Cost Function**: Measure the accuracy of _h_ by taking an average difference of _h<sub>θ</sub>(x)_ and _y_. The purpose of the algorithm is to find parameters which minimize the cost function.

* **Squared error cost function**: Calculated by:  _J(θ₀,θ₁) = &sum;(hθ(x<sup>(i)</sup>) - y<sup>(i)</sup>)<sup>2</sup>_ * _1/2m_, where _m_ is the number of training examples.

### Gradient Descent
**Definition**: _Gradient_ is the direction which increase the most at a certain point. It can be represented by a vector of partial derivatives,
 denoted by _(&#8753;x,&#8753;y)<sup>T</sup>_. eg. for the point _(x<sub>0</sub>, y<sub>0</sub>)_, the direction _(&#8753;x<sub>0</sub>,&#8753;y<sub>0</sub>)<sup>T</sup>_ increases _f_ the most, while the direction _-(&#8753;x<sub>0</sub>,&#8753;y<sub>0</sub>)<sup>T</sup>_ decreases _f_ the most.

**Purpose**: By graphing the cost function, we want to find a point which minimizes the square error _J_.

**Gradient Descent Algorithm**: _θ<sub>j</sub>:=θ<sub>j</sub>−α&#8753;θ<sub>j</sub>_, where _α_ is the learning rate and _j_ is the index. Repeat until convergence.
* **Linear Regression**: instead, we can convert the differential equation into its real. Read [Coursera](https://www.coursera.org/learn/machine-learning/resources/JXWWS) to view more details.
* **Note**: It's important to decide an appropriate learning rate. If _a_ is too big, it's likely to skip significant values. If _a_ is too small, it will pull down the efficiency. Read [What is learning rate?](https://www.cnblogs.com/lliuye/p/9471231.html) to view more details.

### Multivariate Linear Regression
**Notations**:
* _x<sub>j</sub><sup>(i)</sup>_: variable(feature) _j_ of _i-th_ training example.
* _x<sup>(i)</sup>_: a column vector of all variables(features) of _i-th_ example
* _m_: number of examples
* _n_: number of features

**Hypothesis Function**:
* Multivariable Form  (a single training example): _h<sub>θ</sub>(x) = θ<sub>0</sub> + θ<sub>1</sub>x<sub>1</sub> + .. + θ<sub>n</sub>x<sub>n</sub>._
* Vectorized Version (a single training example): _h<sub>θ</sub>(x) = [θ<sub>0</sub> θ<sub>1</sub> ... θ<sub>n</sub>] <[x<sub>0</sub> x<sub>1</sub> ... x<sub>n</sub>]| = θ<sup>T</sup>x_ **(Note: Here is a Transpose. θ is actually a column vector )**.
* With _m-th_ training examples, we will replace the vector _x_ with vector _X_, where _X_ represents training examples row-wise. Therefore, we will have _h<sub>θ</sub>(X) = Xθ_ **(Note: can not switch the order of X and θ)** instead. Read [Coursera](https://www.coursera.org/learn/machine-learning/resources/QQx8l) to view more details.

**Cost Function**:
* Remind: _J(θ) = 1/2m * &sum; (h<sub>θ</sub>​(x<sup>(i)</sup>)−yx<sup>(i)</sup>)<sup>2</sup>_, where _θ_ is a parameter vector.
* Vectorize Version: _J(θ) _ = 1/2m(Xθ-y)<sup>T</sup>(Xθ-y)_, where _y_ is a vector of real output values **(Note: (Xθ-y) is actually the error of each training example)**.







## Reference:
1. [Coursera](https://www.coursera.org/learn/machine-learning/resources/JXWWS)
2. [Difference Between Clustering and Classification](https://www.differencebetween.com/difference-between-clustering-and-vs-classification/)
3. [Gradient Descent](https://zhuanlan.zhihu.com/p/64402931)
4. [What is learning rate?](https://www.cnblogs.com/lliuye/p/9471231.html)

## Related:
1. Linear Algebra
2. Matrix
3. Partial Derivative
