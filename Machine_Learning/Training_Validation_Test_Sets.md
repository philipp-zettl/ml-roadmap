# Training, validation, and test sets[^1]
In ML we build sometimes models/algorithms that learn from data and make predictions on data.  
Such algorithms form our mathematical models based on the input data we forward to it. It is common
to split/divide this input data in multiple data sets. In particular it's common to split it into
three sets for the three different stages of model creation. The _training, validation and test_ sets.
- Training
  - used to initially fit the model
  - a set of examples
  - model is trained on training data set using supervised learning
  - usually contains the expected result, not just input values
  - the predicted output and expected output get compared and based on that the optimization algorithm adjusts the parameter of the model
- Validation
  - used for unbiased evaluation of a model fit on the training data
  - tunes hyperparameters
  - can be used for early exits during training
- Test
  - provides unbiased evaluation of final model fit on training data set
  - sometimes same set as Validation  


Sometimes we can skip the step of Validation and use two data sets in total, the Training and Test sets.  
A usual split might be `33%` for the test data and `67%` for training data.

But same as with using different cost functions we're covered thanks to `sklearn` using
```python
from sklearn.model_selection import train_test_split
```
does the heavy lifting of selection for us. We can just provide a ratio like
```python
train_test_split(X, y, test_size=0.33, random_state=1)
```
this even provides a `random_state` parameter to allow replication of datasets.

### Cross-validation
In order to get more stable results and use all valuable data for training, a set can be split into several training
and validation sets over and over again, which is called cross-validation.  
To validate the models performance an additional test set independent from the cross-validation set is used.

[^1]: [https://en.wikipedia.org/wiki/Training,_validation,_and_test_sets](https://en.wikipedia.org/wiki/Training,_validation,_and_test_sets)
