# Bias and Variance
## Bias
as we know from previous chapter [Over-/Underfitting](Over_Underfitting.ipynb) bias occures when an algorithm has limited flexibility to learn a signal from the dataset.
High bias can cause an algorithm to miss the relevant relations between features and target outputs, underfitting the train data.  
We can visualize this as our model is biased thowards our training data, like we could be biased thowards other people. If you're highly biased you're more likely to make false assumptions about them,
you literally label them thowards your bias.

Thus learning models that summarize data with a set of parameters of fixed size, so called parametric models, are prone to high bias.
A LinReg model as seen in several previous chapters is an example of a parametric algorithm
```
y ~ b_0 + b_1 * X
```
the simplest model always has 2 variable parameters `b_0` and `b_1`, this will **never** change.
Thus, those parametric models are inaccurate for complex datasets and are high-bias algorithms. This includes not only
Linear Regression models, but also Linear Discriminant Analysis and Logistic Regression.

## Variance
Variance refers to how sensitive the algorithm to specific sets of the training set occurs when an algorithm has limited flexibility to learn the true signal from that dataset.
High variance can cause an algorithm to model the random noise in the training data, rather than the intended outputs, overfitting the train data.

Varaince is the difference between many predictions by one model.
A high variance tends to occur when we use complicated models that can overfit our training sets. Think of it as different stereotypes based on different demographics.

## Is there a trade-off?
> Unfortunately there's no way to minimize bias and variance.

We need to find the balance. One good thing is, using cross-validation we can give a better average representation of the whole and average predictions.
But this is what we can do:

High variance:
- get more training examples
- try smaller feature sets
- reduce your training rate

High bias:
- add features, you're generalizing the dataset
- try adding polynomial features, make your model more complicated
- try decreasing your learn rate


## Conclusion
If a learning algorithm suffers from high variance, get more training data. High variance and low bias means overfitting. This is caused by understanding the data too well. More data will allow finding a signal instead of noise.
