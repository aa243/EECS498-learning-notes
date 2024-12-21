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

