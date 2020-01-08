---
date: 2020-01-08 09:46:00
layout: post
title: Neural Networks in Machine Learning
subtitle: Understand a Neural Network as a learning algorithm.
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
h<sub>Θ</sub>(x)

## Table of Contents
- 1.[Definition](#definition)
- 2.[Representation](#representation)
  - 2.1 [Simplistic View](#simplistic-view)
  - 2.2 [General View](#general-view)
    - 2.2.1 [General Example](#general-exampe)
    - 2.2.2 [Notation](#notation)
    - 2.2.3 [Formula](#formula)
    - 2.2.4 [Dimension](#dimension)
  - 2.2 [Vectorized Version](#vectorized-version)
    - 2.2.1 [Conversion Step](#conversion-step)
- 3. [Reference](#reference)
- 4. [Related](#related)
***

## Definition
* **Neuro** (a computational unit): [dendrites](https://www.wisegeek.com/what-are-dendrites.htm#didyouknowout)(features) →_axons_(h<sub>Θ</sub>(x))
* **x<sub>0</sub>**: called _"bias unit"_. Equal to 1.
* **Θ**: called _"weights"_ (a matrix instead of a column vector &theta;)
* **h<sub>Θ</sub>(x)**: called _"sigmoid / logistic activation function"_. The formula is the same as the logistic function.

***

## Representation

### Simplistic view
* **Simplistic Example**:
> [x<sub>0</sub>, x<sub>1</sub>, x<sub>2</sub>] <sup>T</sup> → [ ]  → h<sub>Θ</sub>(x)<br/>

* **Text View**:
>_input layer →  hidden layers → output layer_,

 where _hidden layers_ are layers that intermediate the input and the output.

***

### General View
#### General Example
> [x<sub>0</sub>, x<sub>1</sub>, x<sub>2</sub>] <sup>T</sup> → [a<sub>1</sub><sup>(2)</sup>, a<sub>2</sub><sup>(2)</sup>]<sup>T</sup>  → h<sub>Θ</sub>(x)<br/>

#### Notation
  * **a<sub>i</sub><sup>(j)</sup>**: an activation unit
    * **i**: the index of the unit
    * **(j)**: the index of the layer
  * **Θ<sup>(j)</sup>**: weight matrix of the layer _(j)_

#### Formula
  The value of nodes in each layer is derived by, taking the sum of **nodes** and **Θ** of the **previous** layer as inputs, and applying the function **_g(Θx)_**.

  > eg. In the previous example,  we have **[x<sub>0</sub>, x<sub>1</sub>, x<sub>2</sub>] <sup>T</sup> → [a<sub>1</sub><sup>(2)</sup>, a<sub>2</sub><sup>(2)</sup>]<sup>T</sup>  → h<sub>Θ</sub>(x)**<br/>
  and therefore, we will have **a<sub>1</sub><sup>(2)</sup> = g(Θ<sub>10</sub><sup>(1)</sup>x<sub>0</sub> + Θ<sub>11</sub><sup>(1)</sup>x<sub>1</sub> + Θ<sub>12</sub><sup>(1)</sup>x<sub>2</sub>)**, ...<br/>
  This will also work for h<sub>Θ</sub>(x) (which is actually a<sub>1</sub><sup>(3)</sup>): **a<sub>1</sub><sup>(3)</sup> = g(<big>*Θ<sub>10</sub><sup>(2)</sup>a<sub>0</sub><sup>(2)</sup>*</big> + Θ<sub>11</sub><sup>(2)</sup>a<sub>1</sub><sup>(2)</sup> + Θ<sub>12</sub><sup>(2)</sup>a<sub>2</sub><sup>(2)</sup>)**.

  <small>(**Note**: In the 3<sup>rd</sup> line, we include a **bias node** in the summation.)</small>

#### Dimension
  Suppose we have **N<sub>j</sub>** nodes in layer _j_, and **N<sub>j+1</sub>** nodes in layer _j+1_.

  The dimension of the **Θ<sup>(j)</sup>** is **N<sub>j</sub>** x (**N<sub>j+1</sub> + 1**), except for **Θ<sup>(1)</sup>**.

   <small>(**Note**: The "+1" actually indicates that the **"bias node"**, which is equal to 1, should be involved in the calculation.)</small>

***

### Vectorized View

#### Conversion Step

* **z**: Recall that we have __z = &theta;<sup>T</sup>x__, and therefore, in this case, **_z<sub>k</sub><sup>(j+1)</sup> = Θ<sub>k</sub><sup>(j)</sup>a<sup>(j)</sup>_**, where _k_ is the index of the unit in _j_, _j_ is the index of the layer, and _x_ is a column vector.

  > eg. **z<sub>k</sub><sup>(j+1)</sup> = Θ<sub>k0</sub><sup>(j)</sup>a<sub>0</sub><sup>(j)</sup> + ... + Θ<sub>kn</sub><sup>(j)</sup>a<sub>n</sub><sup>(j)</sup>**

* **a<sup>(j)</sup>**: **a<sup>(j)</sup> = g(z<sup>(j)</sup>)**, where *z<sup>(j)</sup>* is a column vector **[z<sub>1</sub><sup>(j)</sup>, z<sub>2</sub><sup>(j)</sup>, z<sub>3</sub><sup>(j)</sup>, ..., z<sub>n</sub><sup>(j)</sup>]<sup>T<sup>**.

  The function _g_ will be applied to _z_ row-wise. It's just the same with the logistic function.

* **h<sub>Θ</sub>(x)**: Remember that **h<sub>Θ</sub>(x)** is actually a layer with one activation unit, so we just apply the same rule.

  > eg. **h<sub>Θ</sub>(x) = a<sup>(j + 1) </sup> = g(z<sup>(j+1)</sup>)**

## Reference
1. [Coursera](https://www.coursera.org/learn/machine-learning/home/week/4)

***

## Related:

1. Logistic Regression

***

<small>Last update: 12:37pm 08/01/2020</small>
