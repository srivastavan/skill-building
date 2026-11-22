# Lecture 1: Building micrograd

My hand-written notes from Andrej Karpathy's [Neural Networks: Zero to Hero](https://karpathy.ai/zero-to-hero.html) course, lecture 1: "The spelled-out intro to neural networks and backpropagation: building micrograd."

I have divided the content into sub-parts:

- 1a [Creating the Value class](lecture-1a-creating-class-Value.ipynb): a scalar object that stores data, its gradient, and how it was computed
- 1b [Running backpropagation](lecture-1b-running-backpropogation.ipynb): computing gradients through the expression graph with the chain rule
- 1c [Manual backpropagation through a neuron](lecture-1c-manual-backpropogation-neurons.ipynb): working out each gradient of a single neuron by hand
- 1d [Doing the same in PyTorch](lecture-1d-doing-same-in-pytorch.ipynb): checking micrograd's results against PyTorch tensors and autograd
- 1e [Building an MLP in micrograd](lecture-1e-building-MLP-in-micrograd.ipynb): the Neuron, Layer and MLP classes, and counting parameters
- 1f [Loss function and training](lecture-1f-loss-function-in-micrograd.ipynb): squared-error loss, zeroing gradients, and gradient descent

## Summary

Neural networks are mathematical expressions that take two kinds of input: the data, and the network's parameters (its weights and biases). The forward pass runs the data through this expression to produce predictions. A loss function then measures how far those predictions are from the correct targets: the lower the loss, the better the network is doing. Backpropagation calculates the gradient of the loss with respect to every parameter, which tells us how each parameter affects the loss. Gradient descent then nudges each parameter a small step in the opposite direction of its gradient, which lowers the loss. Repeating this loop many times (forward pass, zero the gradients, backward pass, update) is how the network learns.

Diagrams and screenshots used in the notebooks are in the [images](images/) folder.

---

*This README was written with AI assistance (Claude). The notebooks are my own hand-written notes.*