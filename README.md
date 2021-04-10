# RBM_learn

A small library for defining and training Restricted Boltzmann Machines. This was originally written as part of a lab assignment for a graduate course on neural networks.

---

## Description of Objects/Methods

* `RBM_network(n_v, n_h)`: instantiates an RBM network object.    
    Arguments:
    - n_v: the number of desired visible neurons
    - n_h: the number of desired hidden neurons

**(The Following are `RBM_network` class methods)** 

* `initialize_weights(seed)`: initializes the weights in the network.    
    Arguments:
    - seed: a random seed to use for initialization

* `generate_layer(W, current_layer)`: generates a layer of neurons (hidden, given visible and vice versa) using conditional probabilities.    
    Arguments:
    - W: the weight matrix for the network
    - current_layer: a binary vector, representing either the hidden layer or the visible layer

* `generate_layer_array(W, layer_array)`: generates an array of layers for an entire array of layers of neurons. A layer is generated for each instance.
    Arguments:
    - W: the weight matrix for the network
    - layer_array: an array where each row corresponds to the layer of an instance. Each row must correspond to a layer of the same type (i.e. all hidden layers or all visible layers).

---

**NOTE:** The "Description of Objects/Methods" section is still being completed.
