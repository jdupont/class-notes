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
  + _Generalization_: A model's ability to adapt properly to new, previously unseen data
  + _Overfitting_: When a model tries to fit the training data so closely that it does not generalize well to new data.
  + _Feature engineering_: Extracting relevant attributes from data by transforming raw data into a feature vector.
  + _One-hot encoding_: Encode vocabulary with a vector of length equal to vocabulary size. For each word in
  the vocabulary, have one digit hot and all others 0.
  + _Feature cross_: Synthetic feature that encodes nonlinearity in the feature space by multiplying two or more input features together.

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
+ TensorFlow Toolkit:

| Toolkit | Description |
| --- | --- |
| Estimator (tf.estimator) | 	High-level, OOP API. |
| tf.layers/tf.losses/tf.metrics |	Libraries for common model components. |
| TensorFlow |	Lower-level APIs |

+ Two pieces of TensorFlow:
  + A graph protocol buffer
  + A runtime that executes the graph
+ Kind of like Java (graph) and JVM (runtime)
+ Often use `tf.estimator`. Typical linear regression with that:
```
import tensorflow as tf

# Set up a linear classifier.
classifier = tf.estimator.LinearClassifier()

# Train the model on some example data.
classifier.train(input_fn=train_input_fn, steps=2000)

# Use it to predict.
predictions = classifier.predict(input_fn=predict_input_fn)
```
+ pandas
  + Primary data structures:
    + **DataFrame**: like a relational data table, with rows and named columns
    + **Series**: A single column.
    + A DataFrame contains one or more Series and a name for each Series.
+ Rules of thumb for model tuning:
  + Training error should steadily decrease, steeply at first, and should eventually plateau as training converges.
  + If the training has not converged, try running it for longer.
  + If the training error decreases too slowly, increasing the learning rate may help it decrease faster. But sometimes the exact opposite may happen if the learning rate is too high.
  + If the training error varies wildly, try decreasing the learning rate.
  + Lower learning rate plus larger number of steps or larger batch size is often a good combination.
  + Very small batch sizes can also cause instability. First try larger values like 100 or 1000, and decrease until you see degradation.
+ Completed Programming Exercises:
  + [Introduction to Pandas](https://drive.google.com/file/d/1-erjOEvNaBL33FIxoMyiPndMklDJmJPO/view?usp=sharing)
  + [First Steps with TensorFlow](https://drive.google.com/file/d/1YY0ougHMzj9ai6k_OekpedAxmFP8Ueq2/view?usp=sharing)
  + [Synthetic Features and Outliers](https://drive.google.com/file/d/1r-cWfxRYy5cVj1AfNo7wIIqxddUKyLcF/view?usp=sharing) 

## Generalization

+ A model's ability to adapt properly to new, previously unseen data
+ Can evaluate a model's generalization using test data
+ To prevent overfitting, generally want to keep the model as simple as possible

## Training and Test Sets

+ Partition data into test and training sets
  + How large to make partitions?
  + Depends on size of data
+ Do not test and train on the same data set -- this can happen by accidents (duplicate data for example)

## Validation

+ Partioning as above can still lead to overfitting to the peculiarities of the test data
+ So, partition into 3 pieces:
  + Train with *training*
  + Tune model with *validation*
  + Confirm with *test*
+ Remember that sets "wear out" with too much use
+ Completed programming exercise [here](https://drive.google.com/file/d/1uuV7sk4ZZ89w6S0Wemh5YhGt52U0_Ve_/view?usp=sharing)

## Representation

+ Important to extract features from data in order to be able to process them in model
+ Properties of a good feature:
  + Should almost always be nonzero (avoid rarely used feature values)
  + Should have a clear and obvious meaning (makes it easier to debug and reason about)
  + Should not have "magic" flag values
  + Feature value should not change over time (semantics must be constant)
  + Feature should not have crazy outliers
+ Strings: one-hot encoding
+ Numeric data: EZ-peasy lemon squeezy
+ Enums (categorical data): Usually represented with one boolean field per category
+ Completed programming exercise [here](https://drive.google.com/file/d/15aS_XO8X5RWSHY51FlOsT2E6x3zbD7LC/view?usp=sharing)

## Feature Crosses

+ Combine two or more features to increase the value of these features beyond what they can provide individually
+ Main value:
  + Allows linear learners to have more expressive models
  + Linear models work well with massive data sets
  + Adding in feature crosses gives these simple models that ability to represent complex situations
+ Crossing One-Hot Vectors:
  + Equivalent to logic conjunction: County AND Language
  + Common in practice
+ Completed programming exercise [here](https://drive.google.com/file/d/1KR7YwWtTziJMtOj6H16apdk3ZCtR3ijK/view?usp=sharing)

## [Regularization: Simplicity](https://developers.google.com/machine-learning/crash-course/regularization-for-simplicity/playground-exercise-overcrossing)

+ Crosses can be overdone
  + Makes model more complex (e.g., adds nonlinearity)
  + But, sometimes data are simple (e.g., completely linear)
  + In this case, overcrossing (as a subset of overfitting)
+ Regularization is a strategy for avoiding overfitting
+ Penalizing Model Complexity
  + The more complex the model, the greater the change of overfitting
  + So, bake this into optimization calculatio for training:
```
minimize(Loss(Data|Model) + lambda * complexity(Model))
```
  + Higher lambda favors simple models (at the risk of underfitting)
  + Lower lambda favors more complex models (at the risk of overfitting)
+ L2 Regularization
  + Prefer smaller weights
  + Small weights with normal distribution
  + Penalize for deviation from this
+ Early stoppage (stop before the overfitting happens)

## Logistic Regression

+ Predicts probability (from 0 to 1)
+ Useful for binary classification (percent chance of one category or another)
+ Good applications:
  + Very fast training and prediction times (works well on large data sets)
  + Can incorporate some nonlinearity with feature crosses

## [Classification](https://developers.google.com/machine-learning/crash-course/classification/video-lecture)

Left off here.

## Regularization: Sparsity

## Introduction to Neural Nets

## Training Neural Nets

## Multi-Class Neural Nets

## Embeddings

## Static vs Dynamic Training

## Static vs Dynamic Inference

## Data Dependencies
