---
date: 2020-01-06 16:06:00
layout: post
title: Classification Model of Machine Learning
subtitle: Introduce four types of classification models.
description: >-
  All about classification models.
image: >-
  https://res.cloudinary.com/dm7h7e8xj/image/upload/v1559821647/theme6_qeeojf.jpg
optimized_image: >-
  https://res.cloudinary.com/dm7h7e8xj/image/upload/c_scale,w_380/v1559821647/theme6_qeeojf.jpg
category: Reading
tags:
  - machine learning
  - model
  - classification
author: Alex
---

## Table of Contents
- 1.[Logistic Regression Model](#logistic-regression-model)
  - 1.1 [Binary Classification](#binary-classification)
    - 1.1.1 [Definition](#definition)
    - 1.1.2 [Notation](#notation)
    - 1.1.3 [Hypothesis Function](#hypothesis-function)
    - 1.1.4 [Decision Boundary](#decision-boundary)
    - 1.1.5 [Cost Function](#cost-function)
    - 1.1.6 [Gradient Descent](#gradient-descent)
  - 1.2 [Multiclass Classification](#Multiclass-classification)
- 2.[Reference](#reference)
- 3.[Related](#related)

***

## Logistic Regression Model
<small>Note: Don't confuse by the name. They are actually classification models.</small>


### Binary Classification

#### Definition

In binary classification problems, only two possible results (classes) are considered. And therefore, the output can only be a binary number (0 or 1).

> eg. Consider that we have a group of people. 0 may represent the group of males, and 1 may represent the group of females.

The following steps will convert functions (may not be linear) into **Sigmoid Functions**, which maps the range into [0..1].

***

#### Notation

1. _0_: negative class, sometimes denoted as "-"
2. _1_: positive class, sometimes denoted as "+"
3. _y<sup>(i)</sup>_: can be also called the "label"

***

#### Hypothesis Function

* **Purpose**: As for the **Hypothesis Function** for Classification, instead of real-value predictions, we'll have the **probability** of our outputs.

  > eg. If h<sub>θ</sub>(x) = 0.1, then the probability that the result is 1 is 10%, which is denoted as _h<sub>θ</sub>(x) = P(y=1\|x;θ) = 1 - P(y=0\|x;θ)_.

* **Formula**: <br/>
> _h<sub>θ</sub>(x) = g(θ<sup>T</sup>x)  = 1/(1+e<sup>-θ<sup>T</sup>x</sup>)_

  To make it more clear: </br>
  > _Let z = θ<sup>T</sup>x_ (the original function),</br>
  _g(z) = 1/(1+e<sup>-z</sup>)_
<small>

(apply the "[Sigmoid Function](https://baike.baidu.com/item/Sigmoid%E5%87%BD%E6%95%B0/7981407?fr=aladdin)" or the "[Logistic Function](https://baike.baidu.com/item/Sigmoid%E5%87%BD%E6%95%B0/7981407?fr=aladdin)") </small>

* **Relationship**: <small>(Recall the graph of [Fractional Function](https://image.baidu.com/search/detail?ct=503316480&z=0&ipn=d&word=%E5%88%86%E5%BC%8F%E5%87%BD%E6%95%B0&step_word=&hs=0&pn=7&spn=0&di=2750&pi=0&rn=1&tn=baiduimagedetail&is=0%2C0&istype=2&ie=utf-8&oe=utf-8&in=&cl=2&lm=-1&st=-1&cs=4130024059%2C2682151601&os=3611948051%2C2676546098&simid=3197995867%2C3751113396&adpicid=0&lpn=0&ln=845&fr=&fmq=1578364236859_R&fm=result&ic=&s=undefined&hd=&latest=&copyright=&se=&sme=&tab=0&width=&height=&face=undefined&ist=&jit=&cg=&bdtype=0&oriquery=&objurl=http%3A%2F%2Fwww.mianfeiwendang.com%2Fpic%2F6438f2e47608b1eab3dbd630%2F6-338-png_6_0_0_135_367_526_183_892.979_1262.879-974-0-1289-974.jpg&fromurl=ippr_z2C%24qAzdH3FAzdH3Fooo_z%26e3B4twgujtojg1wg2_z%26e3Bv54AzdH3F15vAzdH3Fm9nbudj90mabk8jwkn1k1mnaAzdH3Fm&gsm=&rpstart=0&rpnum=0&islist=&querylist=&force=undefined))</small>
  1. When _z = 0, e<sup>0</sup> = 1 => g(z) = 1/2_;
  2. When _z = ∞, e<sup>-∞</sup> → 0 => g(z) = 1_;
  3. When _z = -∞, e<sup>∞</sup> → ∞ => g(z) = 0_;

***

#### Decision Boundary

- **Definition**: a line that separates values into 1 and 0 after deciding the _hypothesis function_.

  > eg. When x<sub>j</sub> <=10, y = 1, and vice versa. Then, x<sub>j</sub>  = 10 becomes the **Decision Boundary**.

- **Translation**: In order to map values into 0 and 1, We have the rule that
  > h<sub>θ</sub>(x) ≥ 0.5 → y = 1 <br/>
  h<sub>θ</sub>(x) < 0.5 → y = 0

  According to the relationship above, the translation indicates that
  > θ<sup>T</SUP>x >= 0 → y = 1<br/>
  θ<sup>T</SUP>x < 0 → y = 0

  ***

#### Cost Function
* **Recall**: **Cost Function** demonstrates the *accuracy* of our hypothesis function.

* **Formula - Two Conditional Cases**:
  > _J(θ) = 1/m \* &Sum;<sup>m</sup><sub>i=1</sub>Cost(h<sub>θ</sub>(x<sup>(i)</sup>), y<sup>(i)</sup>),_ where <br/>
  if y = 1, Cost(h<sub>θ</sub>(x<sup>(i)</sup>), y<sup>(i)</sup>) = -log(h<sub>θ</sub>(x))<br/>
  if y = 0, Cost(h<sub>θ</sub>(x<sup>(i)</sup>), y<sup>(i)</sup>) = -log(1- h<sub>θ</sub>(x))

  To explain the **Cost:**<small>(Recall the graph of [Logarithmic Function](http://image.baidu.com/search/index?tn=baiduimage&ps=1&ct=201326592&lm=-1&cl=2&nc=1&ie=utf-8&word=Logarithmic+Function))</small><br/>
   if y = 1, when h<sub>θ</sub>(x) approaches 1, -log(h<sub>θ</sub>(x)) approaches 0. At the same time, when h<sub>θ</sub>(x) approaches 0, -log(h<sub>θ</sub>(x)) approaches &infin;.

* **Formula - One Case**:
  > Cost(h<sub>θ</sub>(x),y) = −y log⁡(hθ(x)) − (1−y) log⁡(1−h<sub>θ</sub>(x))

  To explain the **Cost:**<br/>
  The tricky thing is, when y = 0, the left half of the formula will be 0. It's similar when y = 1.

* **Formula - Vectorized Version**:
  > h<sub>&theta;</sub>(x) = g(X&theta;)<br/>
  J(&theta;) = 1/m (−y<sup>T</sup>log⁡(h<sub>&theta;</sub>(x)) − (1−y)<sup>T</sup>log⁡(1-h<sub>&theta;</sub>(x)))

***

#### Gradient Descent
The same as the Regression Model [links to be added].

***

### Multiclass Classification
* For Multiclass Classification, we will have _n_ hypothesis functions, where _n_ is the number of classes.

* **Formula**:
  > h<sub>&theta;</sub><sup>(i)</sup>(x) = P(y = i \| x;&theta;), where i = (1,2,3,...,n)

  For each new _x_, we will find an _i_ which maximizes the **probability**(h<sub>&theta;</sub><sup>(i)</sup>).

   This can be denoted as **max<sub>i</sub>(h<sub>&theta;</sub><sup>(i)</sup>(x))**.  

## Reference
1. [Coursera](https://www.coursera.org/learn/machine-learning/resources/Zi29t)
2. [Sigmoid Function](https://baike.baidu.com/item/Sigmoid%E5%87%BD%E6%95%B0/7981407?fr=aladdin)

## Related:

1. Sigmoid Function
2. Fractional Function
3. Logarithmic Function
4. _Conjugate gradient, BFGS, and L-BFGS_: Existing algorithm which are efficient and convenient for calculating &theta;

***

<small>Last update: 15:03pm 07/01/2020</small>
