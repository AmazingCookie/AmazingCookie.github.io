---
date: 2020-01-07 15:03:00
layout: post
title: Overfitting and Underfitting in Machine Learning
subtitle: Introduce the way of making better predictions.
description: >-
  Regularization.
image: >-
  https://res.cloudinary.com/dm7h7e8xj/image/upload/v1559821647/theme6_qeeojf.jpg
optimized_image: >-
  https://res.cloudinary.com/dm7h7e8xj/image/upload/c_scale,w_380/v1559821647/theme6_qeeojf.jpg
category: Reading
tags:
  - machine learning
  - regularization
author: Alex
---

## Table of Contents
- 1.[Overfitting and Underfitting](#Overfitting-and-Underfitting)
  - 1.1 [Definition](#definition)
  - 1.2 [Solution](#solution)
- 2.[Regularization](#regularization)
  - 2.1 [Regularized Cost Function](#regularized-cost-function)
  - 2.2 [Regularized Linear Regression](#regularized-linear-regression)
    - 2.2.1 [Gradient Descent](#regularized-descent)
    - 2.2.2 [Normal Equation](#normal-equation)
  - 2.3 [Regularized Logistic Regression](#regularized-logistic-regression)
- 3. [Reference](#reference)
- 4. [Related](#related)
***

## Overfitting and Underfitting
### Definition
Problems my happen during the prediction:
1. **Underfitting**: High bias. Poor performance in fitting existing data. Usually caused models that are too simple.
2. **Overfitting**: High variance. Poor performance in predicting new data. Usually caused by unrelated curves and angles of models.

![Regularization](/src/img/regularization-post/regularization.jpg)

<small>Refer to [Deep Learning: Regularization](http://www.imooc.com/article/69484) for _"what is bias and what is variance?"_</small>

### Solution
1. Reduce Features (_Technique applied:_ **_Model Selection Algorithm_**)
2.  Reduce the magnitude of θ<sub>j</sub> (_Technique applied:_ **_Regularization_**)

***

## Regularization
<small>One way of handling **Overfitting**.</small>

### Regularized Cost Function
Reduce influences of some features by minimizing their parameters.

This can be done by penalizing (**L2 regularization**).

> eg. For the function _h<sub>&theta;</sub>(x) = &theta;<sub>0</sub> + &theta;<sub>1</sub>x + &theta;<sub>2</sub>x<sup>2</sup>_, if  we wanna minimize the influence of the square, we can replace the original cost function with *J<sub>new</sub>(&theta;) =
  J<sub>old</sub>(&theta;) +* ***100 &theta;<sub>2</sub><sup>2</sup>***.<br/><br/>
  Since we want to have the cost function approaching to 0, the value of _&theta;<sub>2</sub>_ must be small enough to satisfy this requirement.

In general, instead of adding some certain &theta;, **all parameters will be penalized** in order to produce a simpler curve, which takes over overfitting.

 It can be denoted as:
 > J<sub>new</sub>(&theta;) = J<sub>old</sub>(&theta;) + ***&lambda;/2m &sum;<sup>n</sup><sub>j=1</sub> &theta;<sub>j</sub><sup>2</sup>***, where &lambda; is the _regularization parameters_ <small>(Refer to [How to calculate the regularization parameter?](https://stackoverflow.com/questions/12182063/how-to-calculate-the-regularization-parameter-in-linear-regression) for more details)</small>.<br/>

 If &lambda; is too huge, it may lead to _underfitting_, in which case, the shape of the function may just be a horizontal line.  

 Also, note that **_j_ starts from _1_**, since &theta;<sub>0</sub> doesn't have to be penalized.

***

### Regularized Linear Regression

#### Gradient Descent
To regularize the gradient descent, for each &theta; except &theta;<sub>0</sub>, we substract the original formula by a&lambda;/m &theta;<sub>j</sub>.

> θ<sub>j</sub> := θ<sub>j</sub> − α(... +  **λ/m θ<sub>j</sub>**), where j = [1..n], or <br/>
θ<sub>j</sub> := θ<sub>j</sub>(1 - **aλ/m**) - ..., where ... stands for the original formula.

#### Normal Equation
> _θ = (X<sup>T</sup>X + **&lambda;L**)<sup>−1</sup>X<sup>T</sup>y_, where L is a _(n+1)x(n+1)_ matrix similar to I (identity matrix), except the first row is all 0.

Also, by applying the regularization, _X<sup>T</sup>X + **&lambda;L**_ becomes invertible regardless of numbers of _m_ and _n_ (recall [links to be added]()).

***

### Regularized Logistic Regression
> *J<sub>new</sub>(&theta;) = J<sub>old</sub>(&theta;) +* ***λ/2m ​∑<sup>n</sup><sub>j=1</sub>​θ<sub>j</sub><sup>2</sup>***

which is almost the same as the regression model.

## Reference
1. [Coursera](https://www.coursera.org/learn/machine-learning/resources/Zi29t)
2. [Regularization](https://www.cnblogs.com/nowornever-L/p/6862320.html)

***

## Related:

1. [Course: Regularization](https://www.coursera.org/learn/machine-learning/resources/Zi29t)
2. [Deep Learning: Regularization](http://www.imooc.com/article/69484)
3. [How to calculate the regularization parameter?](https://stackoverflow.com/questions/12182063/how-to-calculate-the-regularization-parameter-in-linear-regression)
4. Identity Matrix
***

<small>Last update: 15:04pm 07/01/2020</small>
