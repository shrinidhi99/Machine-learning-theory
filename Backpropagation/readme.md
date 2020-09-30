## Backpropagation

The Backpropagation algorithm is a supervised learning method for multilayer feed-forward networks from the field of Artificial Neural Networks.

Feed-forward neural networks are inspired by the information processing of one or more neural cells, called a neuron. A neuron accepts input signals via its dendrites, which pass the electrical signal down to the cell body. The axon carries the signal out to synapses, which are the connections of a cell’s axon to other cell’s dendrites.

The principle of the backpropagation approach is to model a given function by modifying internal weightings of input signals to produce an expected output signal. The system is trained using a supervised learning method, where the error between the system’s output and a known expected output is presented to the system and used to modify its internal state.

Technically, the backpropagation algorithm is a method for training the weights in a multilayer feed-forward neural network. As such, it requires a network structure to be defined of one or more layers where one layer is fully connected to the next layer. A standard network structure is one input layer, one hidden layer, and one output layer.

The backpropagation algorithm is named for the way in which weights are trained.

Error is calculated between the expected outputs and the outputs forward propagated from the network. These errors are then propagated backward through the network from the output layer to the hidden layer, assigning blame for the error and updating weights as they go.

The math for backpropagating error is rooted in calculus, but we will remain high level in this section and focus on what is calculated and how rather than why the calculations take this particular form.

This part is broken down into two sections.

* Transfer Derivative
    
    Given an output value from a neuron, we need to calculate it’s slope.

    We are using the sigmoid transfer function, the derivative of which can be calculated as follows:
    ```C++
    derivative = output * (1.0 - output)
    ```
* Error Backpropagation
    
    The first step is to calculate the error for each output neuron, this will give us our error signal (input) to propagate backwards through the network.

    The error for a given neuron can be calculated as follows:
    ```C++
    error = (expected - output) * transfer_derivative(output)
    ```
The back-propagated error signal is accumulated and then used to determine the error for the neuron in the hidden layer, as follows:
```C++
error = (weight_k * error_j) * transfer_derivative(output)
```

