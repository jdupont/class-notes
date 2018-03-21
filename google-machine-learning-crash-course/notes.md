# [Machine Learning Crash Course](https://developers.google.com/machine-learning/crash-course/)

## Overview

+ Definitions:
  + _Label_: the thing we're predicting (`y`)
  + _Feature_: the input variables describing our data (`x_i`)
  + _Model_: maps examples to predicted labels
  + _Training_: feeding the model examples so it can "learn" how to predict
  + _Inference_: use the model to predict results for unlabeled examples
  + _Hyperparameters_: The knobs the programmers tweak in machine learning algorithms
  + _Learning rate_: A measure of how quickly the model can be trained.

## Descending into Machine Learning

+ Regression vs Classification:
  + Regression predicts continuous values
  + Classifications predicts discrete values
+ Linear regression:
  + `y = wx + b`
  + Learned this in school
+ Training is also *empirical risk/loss minimization*
+ Loss:
  + Zero: perfect model
  + > 0: Imperfect model
  + Defined and calculated by some function (one popular example is squared loss)

## Reducing Loss

+ Gradient descent
  + One technique for minimizing loss
  + Compute derivative of L2
  + Repeatedly take small steps in the direction that minimizes loss (i.e., gradient descent)
  + Learning rate (how big each step is)
+ Will this always get us where we need to be?
  + Convex problems:
    + Just one minimum
    + Starting anywhere is fine
  + Non-convex problems:
    + Uh-oh
    + Multiple minima
    + One example is neural nets
  + Goldilocks rate: learning rate that ensures the fastest possible convergence

## First Steps with TensorFlow

+ Left off [here](https://developers.google.com/machine-learning/crash-course/first-steps-with-tensorflow/video-lecture)

## Generalization

## Training and Test Sets

## Validation

## Representation

## Feature Crosses

## Regularization: Simplicity

## Logistic Regression

## Classification

## Regularization: Sparsity

## Introduction to Neural Nets

## Training Neural Nets

## Multi-Class Neural Nets

## Embeddings

## Static vs Dynamic Training

## Static vs Dynamic Inference

## Data Dependencies
