# 5 Neural Networks

## Neuron

Each neuron performs a dot product with the input and its weights, adds the bias and applies the non-linearity (or activation function).

## Common activation function

- Sigmoid function: it's rarely used in practice for two reasons:
  - saturation: when the input value is very large or very small, it's gradient will be almost zero, which will stop the network from learning.
  - It's not zero-centered. Hence, the gradient on the weights will become either all positive or all negative, and will introduce undesirable zia-zagging.
- tanh: zero-centered version of sigmoid. It's always better than sigmoid.
- ReLU: max(0,x)
  - greatly accelerate the convergence of stochastic gradient descent
  - can be simply implemented
  - may "die" when a large gradient flow through and cause the weight to update in such a way that the neuron will never be activated.
- Leaky ReLU：$f(x) = 1(x<0)(\alpha x) + 1(x\le 0) (x)$, where $\alpha$ is a small constant. It's an effort to solve the "dying" ReLU neuron.

**In short, use the ReLU, be careful with your learning rates and possibly monitor the fraction of "dead" units in a network. If "dying" does become a problem, try Leaky ReLU or Maxout. Never use sigmoid. Try tanh, but expect it to work worse than ReLU/Maxout.**

## Neural Network Architectures

Neural Network is usually organized by layers. It makes it easy to compute the gradient. The most common layer type is the fully-connected layer.

**Naming conventions**: when we way N-layer network, we don't count the input layer.

In practice, 3 layer neural networks is usually deep enough, while in Convolutional Networks, depth is more important.

A bigger size of the neural network means it is easier to overfit. It's always a trade-off of **variance** and **bias**.

However, instead of using smaller network to lower the variance, we should always consider using **L2 regularization, dropout, input noise, etc. to control the variance, and use as big of a neural network as our computational budget allows.**
