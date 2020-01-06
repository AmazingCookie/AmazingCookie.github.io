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
paginate: 12
---

## Table of Contents
- 1.[Definition](#formal-definition)
- 2.[Type](#type)
- 3.[Model](#model)
  - 3.1 [Linear Regression](#linear-regression)
    - 3.1.1 [Notation](#notation)
    - 3.1.2 [Hypothesis Function](#hypothesis-function)
    - 3.1.3 [Cost Function](#cost-function)
    - 3.1.4 [Gradient Descent](#gradient-descent)
  - 3.2. [Multivariate Linear Regression](#multivariate-linear-regression)
    - 3.2.1 [Multivariate Notation](#multivariate-notation)
    - 3.2.1 [Hypothesis Function](#multivariate-hypothesis-function)
    - 3.2.2 [Cost Function](#multivariate-cost-function)
    - 3.2.3 [Gradient Descent](#multivariate-gradient-descent)
    - 3.2.4 [Tip](#tip)
    - 3.2.5 [Normal Equation](#normal-equation)
  - 3.3 [Polynomial Regression and Features](#polynomial-regression-and-features)
- 4.[Reference](#reference)
- 5.[Related](#related)

***

## Formal Definition

> A computer program is said to learn from experience E with respect to some class of tasks T and performance measure P, if its performance at tasks in T, as measured by P, improves with experience E. —— Tom Mitchell

In other words:
* _E_ is the repeated experiences
* _P_ is the measured data
* _T_ is the task

As a result of machine learning, the computer program can perform better in _T_ based on _P_, with iterations _E_.

***

## Type

### Supervised Learning

In **Supervised Learning**, there must be a relationship between inputs and outputs. According to this, problems can be divided into two categories:

* **Regression**: continuous function. Outputs can be _predicted_ based on inputs
  > eg. Predict the age of a person based on pictures.

* **Classification**: also called 'discrete'. Outputs will be separated into distinct categories instead of predicting the their specific values
  > eg. Predict will a person be bald based on pictures.

### Unsupervised Learning
In Unsupervised learning, we will process data sets with no label or with same labels. No results are required to be predicted.

* **Clustering Algorithm**: Decide data into different clusters.
  > eg. News about the same topic from different newspapers.

* **Cocktail Party Algorithm**: Non-Clustering. Separate overlapping voices/audios.

### Important:

* **The difference between _Clustering_ and _Classification_**:

  In _Classification_, before processing any data, the definition of each class will be decided first.

  > eg: Group fruits into apples, bananas, and oranges based on given pictures.

  Instead, in _Clustering_, classes will not be pre-defined. Data will be divided into different groups by detecting similar features.

  > eg: Group fruits of similar types based on given pictures.

  Also, once you've **labelled** the data, it will be treated as _Supervised Learning Problem_.

***

## Model

### Notations
* _x_: input
* _y_: output
* _x<sup>(i)</sup>_, _y<sup>(i)</sup>_: the i-th input/output
* _(x,y)_: the training set / a signle training example
* _X_: the space of input values
* _Y_: the space of output values
* _h_: hypothesis. The function that takes the input and gives the prediction, denoted as _h: X→Y_.

### Linear Regression

#### Hypothesis Function

* By given a real-valued input, we will predict a real-valued output, denoted as _h<sub>θ</sub>(x) = θ₀ + +θ₁x_.

  >eg. predict housing prices of based on their sizes.

#### Cost Function
* Measure the accuracy of _h_ by taking an average difference of _h<sub>θ</sub>(x)_ and _y_. The use of the algorithm is to find parameters which minimize the cost function.

  * **Squared error cost function**: Calculated by:  _J(θ₀,θ₁) = &sum;(hθ(x<sup>(i)</sup>) - y<sup>(i)</sup>)<sup>2</sup>_ * _1/2m_, where _m_ is the number of training examples.

#### Gradient Descent
* _Gradient_ is the direction which increase the most at a certain point. It can be represented by a vector of partial derivatives, denoted by _(&#8753;x,&#8753;y)<sup>T</sup>_. By graphing the cost function, we want to find a point which minimizes the square error _J_.

  > eg. for the point _(x<sub>0</sub>, y<sub>0</sub>)_, the direction _(&#8753;x<sub>0</sub>,&#8753;y<sub>0</sub>)<sup>T</sup>_ **increases** _f_ the most, while the direction _-(&#8753;x<sub>0</sub>,&#8753;y<sub>0</sub>)<sup>T</sup>_ **decreases** _f_ the most.

* **Gradient Descent Algorithm**: _θ<sub>j</sub> := θ<sub>j</sub> − α&#8753;θ<sub>j</sub>_, where _α_ is the learning rate and _j_ is the index. Repeat until convergence.

  * **Linear Regression**: instead, we can convert the differential equation into its real form (differentiate the original function _J(θ)_).

  <small>Read [Coursera](https://www.coursera.org/learn/machine-learning/resources/JXWWS) to view more details.</small>

  * **Note**: It's important to decide an appropriate learning rate. If _a_ is too big, it's likely to skip significant values. If _a_ is too small, it will pull down the efficiency.

  During the practice, if _J(θ)_ increases, it's better to decrease _a_.

  <small>Read [What is learning rate?](https://www.cnblogs.com/lliuye/p/9471231.html) to view more details. </small>

***

### Multivariate Linear Regression

#### Multivariate Notation

* _x<sub>j</sub><sup>(i)</sup>_: variable(feature) _j_ of _i-th_ training example.
* _x<sup>(i)</sup>_: a column vector of all variables(features) of _i-th_ example
* _m_: number of examples
* _n_: number of features

#### Multivariate Hypothesis Function

* **Multivariable formula (a single training example)**: _h<sub>θ</sub>(x) = θ<sub>0</sub> + θ<sub>1</sub>x<sub>1</sub> + .. + θ<sub>n</sub>x<sub>n</sub>._

* **Vectorized Version (a single training example)**: _h<sub>θ</sub>(x) = [θ<sub>0</sub> θ<sub>1</sub> ... θ<sub>n</sub>] [x<sub>0</sub> x<sub>1</sub> ... x<sub>n</sub>]<sup>T</sup> = θ<sup>T</sup>x_ **(Note: Here is a Transpose. θ is actually a column vector )**.

* **With _m-th_ training examples**, we will replace the vector _x_ with vector _X_, where _X_ represents training examples row-wise. Therefore, we will have _h<sub>θ</sub>(X) = Xθ_ **(Note: do not switch the order of X and θ)** instead.

<small>Read [Coursera](https://www.coursera.org/learn/machine-learning/resources/QQx8l) to view more details.<small>

#### Multivariate Cost Function

* **Remind**: _J(θ) = 1/2m * &sum; (h<sub>θ</sub>​(x<sup>(i)</sup>)−y<sup>(i)</sup>)<sup>2</sup>_, where _θ_ is a parameter vector.

* **Vectorized Version**: _J(θ) = 1/2m(Xθ-y)<sup>T</sup>(Xθ-y)_, where _y_ is a vector of real output values **(Note: (Xθ-y) is actually the difference between hypothesis and the real value of each training example)**.

#### Multivariate Gradient Descent

* **Formula**:
```
repeat until covergence: {
  _θ<sub>j</sub>:=θ<sub>j</sub>−α&#8753;θ<sub>j</sub>_
  //_α_ is the learning rate and _j (0..n)_  is the index
}
```

* **Matrix Notation**: _θ := θ - a&nabla;J(θ) = θ−m/α​X<sup>T</sup>(Xθ−y​)_ , where _a&nabla;J(θ)_ is the column vector of partial derivatives. The second formula is derived from the substitution of _(h<sub>0</sub>(x<sup>(i)</sup>)-y<sup>(i)</sup>)_.\

* **Running Time**: _O(kn<sup>2</sup>)_ (I would suggest _nm_ instead).

#### Tip
**Improve the efficiency of gradient descent by restricting the range of input values (_-1..1_ or _-0.5..0.5_).**
1. Feature Scaling: divide inputs by range(maximum-minimum), resulting in _1_ as its new range.
2. Mean Normalization: subtract the average value(mean value) and divide inputs by range/standard.

**When to Declare Convergence**
* Once _J(θ)_ decreases by some small value _E_, declare convergence. The threshold _E_ will be decided based on the situation.

#### Normal Equation
* **Formula**: _θ=(X<sup>T</sup>X)<sup>−1</sup>X<sup>T</sup>y_

* **Proof**: Substitute _h<sub>θ</sub>(x)_ with _θ<sup>T</sup>x_, and expand it by applying the multiplication. More details can be found [here](https://eli.thegreenplace.net/2014/derivation-of-the-normal-equation-for-linear-regression).

* **Running time**: _O(n<sup>3</sup>)_, since calculating _(X<sup>T</sup>X)<sup>-1</sup>_ takes _O(n<sup>3</sup>)_.

* **Non-invertibility**: _X<sup>T</sup>X_ may not be invertible, since:
  1. Parallel(delta equals 0). Linear dependences of features. In this case, decrease the number of features by finding their relations.
  2. The number of features is huge. In this case, delete some features or use "regularization".

***

### Polynomial Regression and Features

* **Idea**: Improve the hypothesis function by combining multiple features into a new feature, such as taking _x<sub>1</sub>x<sub>2</sub>_ as _x<sub>3</sub>_.

  * **Example**: Create a new feature by square an existing feature _x<sub>1</sub>_, then we turn _h<sub>θ</sub>(x) = θ₀ + +θ₁x₁_ into _h<sub>θ</sub>(x) = θ₀ + +θ₁x₁ + θ<sub>2</sub>x<sub>1</sub><sup>2</sup>_. In addition, we can apply the square root as well.

* **Note**: _Feature Scaling_ becomes relatively important as the square and the cubic can be extremely large.

***

## Reference:

1. [Coursera](https://www.coursera.org/learn/machine-learning/resources/JXWWS)
2. [Difference Between Clustering and Classification](https://www.differencebetween.com/difference-between-clustering-and-vs-classification/)
3. [Gradient Descent](https://zhuanlan.zhihu.com/p/64402931)
4. [What is learning rate?](https://www.cnblogs.com/lliuye/p/9471231.html)
5. [Derivation of the Normal Equation for linear regression](https://eli.thegreenplace.net/2014/derivation-of-the-normal-equation-for-linear-regression)
6. [The Normal Equation and matrix calculus](https://eli.thegreenplace.net/2015/the-normal-equation-and-matrix-calculus/)
7. [inv and pinv](https://blog.csdn.net/yinyu19950811/article/details/61420131)

***

## Related:

1. Linear Algebra
2. Matrix
3. Partial Derivative

***

<small>Last update: 3:09pm 03/01/2020</small>
