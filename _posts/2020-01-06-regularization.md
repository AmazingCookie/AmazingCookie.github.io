---
date: 2020-01-07 15:03:00
layout: post
title: Overfitting and Underfitting in Machine Learning
subtitle: The way of minimizing the error of the hypothesis function, and producing the best-fitted curve.
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
TBC.

***

## Overfitting and Underfitting
### Definition
Problems my happen during the prediction:
1. **Underfitting**: High bias. Poor performance in fitting existing data. Usually caused models that are too simple.
2. **Overfitting**: High variance. Poor performance in predicting new data. Usually caused by unrelated curves and angles of models.

![Regularization](/src/img/regularization-post/regularization.jpg)

<small>Refer to [Deep Learning: Regularization](http://www.imooc.com/article/69484) to view _"what is bias and what is variance"_.</small>

### Solution
1. Reduce Features (Technique applied: **_Model Selection Algorithm_**)
2.  Reduce the magnitude of θ<sub>j</sub> (Technique applied: **_Regularization_**)

***

## Regularization
A way of handling **Overfitting**.

### Regularized Cost Function
Reduce influences of some features by adding them into the cost function with **regularization parameters** and **squares**.

 It is denoted as *&lambda;&sum;<sup>n</sup><sub>j=1</sub> &theta;<sub>j</sub><sup>2</sup>*, where &lambda; is the **regularization parameters**.

  > eg. For the function _h<sub>&theta;</sub>(x) = &theta;<sub>0</sub> + &theta;<sub>1</sub>x + &theta;<sub>2</sub>x<sup>2</sup>_, if  we wanna minimize the influence of the square, we can replace the **Cost Function** with *J(&theta;) =
    J(&theta;) + 100 &theta;<sub>2</sub><sup>2</sup>*.<br/><br/>
    Since we want to minimize the **Cost Function** as well, the value of _&theta;<sub>2</sub>_ must be small enough to satisfy this requirement.

***

### Regularized Linear Regression

## Reference
1. [Coursera](https://www.coursera.org/learn/machine-learning/resources/Zi29t)
2. [Regularization](https://www.cnblogs.com/nowornever-L/p/6862320.html)
3.

***

## Related:

1. [Course: Regularization](https://blog.csdn.net/u011324454/article/details/78648568)
2. [Deep Learning: Regularization](http://www.imooc.com/article/69484)

***

<small>Last update: 14:57pm 07/01/2020</small>
