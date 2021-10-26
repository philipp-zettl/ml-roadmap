# Cost Function and gradient descent
We'll use a simple linear regression model to explain two machine learning fundamentals
1. cost functions
2. gradient descent

Altough the LinReg model isn't the best ML model we use it here due to its familiarity and interpretability.
LinReg is used to estimate linear relationshipts between continuous or/and categorical data and a continuous output variable.
You can see a simple example [here](https://wiki.godesteem.de/wiki/orthogonal-linear-regression/).  

## So what's actually happing while a model is learning?
The answer will vary from model to model, but in a simplistic way we can claim that the model learns a function `f` such that `f(x)` maps to `y`.
In fancy words the model learns how to take in a number of inputs `X` in order to predict `y`.

In the case of simple linear(/orthogonal) regression
```
y ~ b_0 + b_1 * x
```
where `x` is a single value; the model "learns" two parameters or scalars
- `b_0` the bias (aka intercept)
- `b_1` the slope

Here are some examples how that approximated regression function may look like  
![image](https://user-images.githubusercontent.com/43775635/138492613-fe18ce17-a4f8-47ff-bdc4-355c55faa217.png)

The bias is the `y` value whenever `x = 0` and the slope is the rate of predicted increase or decrease in `y` for each unit increase in `x`.  
Once the model learned the right values for the scalars we can use the model to compute estimated values of `y` given new values of `x`.  
Rephrased to be more obvious, this allows us to predict values of `y` even if we don't know what `y` is supposed to be.

## Learning Parameter values
There are multiple ways how to learn the parameters of a LinReg model, for now we focus on the easiest illustratable approach statistical learning, which minimises a **cost function**.

Remember playing games like [Memory](https://en.wikipedia.org/wiki/Concentration_(card_game)) or [Connect Four](https://en.wikipedia.org/wiki/Connect_Four)? Remember executing one of your turns and having immediate regret because you saw your mistake or created an advantage for your opponent?

This is exactly what cost functions are good for. To give the training algorithm the opportunity to estimate how good or how bad a given prediction was and to act accordingly. Therefore cost functions help the "learner" to correct or change behaviour to minimize mistakes.

Due to this we can generalize that the objective of an ML model is to find parameters, weights or a structure that minimises the cost function.

The ideal convergence of a ML model would look like this  
![image](https://user-images.githubusercontent.com/43775635/138494437-fec5a33f-bcc7-4849-92c5-dcf93245614e.png)

where the y-axis describes the current error/cost and the x-axis a timeframe of training epochs.

## Minimizing the cost
Now that we have the motivation of changing the parameters of our model, we need to discuss how to actually perform these adjustments in a educated way.
Of course we could re-initiate weights and biases randomly and compare previous predictions with the new one, but that wouldn't be practical and doesn't insure convergence.  
This is where methods like **gradient descent** come in place. GDC finds a local or global minima of a function efficiently.  
From math class we remember that gradients are the slope of a function, for example
```
f(x) = 0.5x + 2 => f'(x) = 0.5
```
where `f'` describes the gradient of `f`. Therefor if we teach a model to minimize this gradient, or to move the model into this direction we automatically reduce the error/cost of it. The word "direction" referres in our simple LinReg example to how the parameters `b_0` and `b_1` should be adjusted to further reduce the cost function.  
As the model iterates through the training epochs it gradually converges towards a local, potentially global, minimum where further changes to the parameters have little to no impact on the outcoming cost.  

> This is literally how Newtons-Method is working for roots of functions.

But let's get our hands dirty with some example coding.

You can find an interactive google colab [here](SimpleLogRegSGD.ipynb).
