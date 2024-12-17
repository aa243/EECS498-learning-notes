# Regularization and Optimization

## Optimization

In previous section, we have linear function as our score function, and loss function to measure the quality of the parameters we choose.

Now we will learn how to optimize the parameters to minimize the loss.

The SVM loss function is formulated as:

$$L = \frac 1 N \sum\limits_i\sum\limits_{j\ne y_i}[max(0,f(x_i;W)_j-f(x_i;W)_{y_i} + 1)] + \alpha R(W)$$

Each item of the loss function can also be viewed as:

$$ L_i = \sum\limits_{j\ne y_i} [max(0,w_j^Tx_i - w_{y_i}^Tx_i+1)]$$

One way to minimize the loss is to follow the gradient.

### Computing the gradient

There're two ways to compute the gradient:

- numerical gradient: slow approximate but easy

Centered difference formula: $[f(x+h)-f(x-h)]/2h$

In practice, centered difference formula often works better.

**Step size** is a very very important hyperparameter in training a neural network.

It has complexity linear in the number of parameters, and is not scalable.

- analytic gradient: fast exact but more error-prone

We can also calculate the gradient by calculas. Since it's more error-prone, sometimes we need to compare it to the numerical gradient to have a double check.

### Gradient descent

- **mini batch gradient descent**: use a fraction of the whole dataset to perform gradient descent. When the dataset is huge, this method is useful.
- **stochastic gradient descent**: It's the extreme case of mini batch where it only contains a single example.

The size of the mini batch is usually based on memory constraints, or set to some value, e.g. 32, 64 or 128.