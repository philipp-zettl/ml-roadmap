This directory contains content about Superviced Learning

# Supervised Learning
Supervised Learning, or SL, is the task of learning a function that maps an input to an output based on example
input-output tuples. In supervised Learning each example is a tuple consisting of an input object, usually an vector,
and a desired output value, also called supervisory signal or label. A supervised learning algorithm
analyzes the training data and producesa an inferred function, which can be used for mapping new examples.
In the optimal scenario this allows to correctly classify unseen instances. This requires the learning
algorithm to generalize from the training data to unseen situations in a "reasonable" way.
Statistically the quality of an algorithm is measured through the so called generalization error.

## Using supervised learning
There are different kind of algorithms to solve different kind of problems.
Yet to use a supervised algorithm a few steps of preparation and decisions need to be done:
1. determine type of training examples
2. gather training set
3. determine input feature representation of the learned function
4. determine structure of the learned function and corresponding learning algorithm
5. complete design and run the learning algorithm on the gathered training data
6. evaluate accuracy of the learned function


## Chosing an learning algorithm
None of the algorithms works best for all problems, so there's a list of different algorithms to chose from
There are a few major issues to consider in SL
- Bias-variance tradeoff
- Function complexity and amount of training data
  - if we have enough data for the complexity of our problem this is not a problem 
- Dimensionality of the input space, aka number of features
  - can we reduce the input space?
  - feature selection/engineering
- noise in the output values
  - are we overfitting/underfitting the training data?

### Algorithms
- [Regression](Regression.ipynb)
  - [Linear Regression](Regression.ipynb)
  - [Poisson Regression](Regression.ipynb)
- [Classification](Classification.ipynb)
  - [Logistic Regression](Classification.ipynb)
  - [Naive Bayes](Classification.ipynb)
  - Linear discriminant analysis
  - [Decision trees](Classification.ipynb)
  - [k-nearest neighbor algorithm](Classification.ipynb)
  - [Neural networks (Multilayer perceptron)](Classification.ipynb)
- Support-Vector machines
- Similarity learning

Supervised learning algorithms are working the following way:

Given a set of `N` training examples of the form `{(x_i,y_i),...}` for `i = 1,..., N` such that `x_i` is the feature vector of the `i`-th example and `y_i` its label,
a learning algorithm seeks a function `g: X -> Y`, where `X` is the input space and `Y` the output space. The function `g` is an element of some space of possible functions `G`,
usually called the hypothesis space. Sometimes `g` is represented using a scoring function `F: X x Y -> R` such that `g` is defined as returning the `y` value that gives
the highest score `g(x) = argmax f(x,y)` with variable `y`. Let `F` denote the space of scoring functions.  
Altough `G` and `F` can be any space of functions, many learning algorithms are probabilistic models where `g` takes form of a conditional probability model `g(x) = P(y|x)`, of `f` takes form of a joint probabilty model `f(x,y) = P(x,y)`.
For example, naive Bayes and linear discriminant analysis are joint probability models, whereas logistc regression is a conditional probability model.
Generally speaking there are two approaches of chosing `f` or `g` empirical risk minimization and structural risk minimization. Both require
a risk `R(g)` to be calculated. Empirical risk minimization seeks the function that fits the training data best and structural risk minimization includes a penalty function that controls the bias/variance tradeoff.
Both cases assum having traing data sets that consist of sample data of independent and identically distributed pairs `(x_i, y_i)`.
To measure how well the model fits the training data the loss function `L: Y x Y -> R` is defined. 
This calculates the loss of predicting the value `y_bar` for the example `(x_i, y_i)` as `L(y_i, y_bar)`.
`R(g)` is defined as the expected loss of `g`. This can be estimated from the training data as
```python
R(g) = 1/N * sum([L(y_i, g(x_i) for x_i, y_i in data])
```
