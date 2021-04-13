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

* `update_weights(W, v_0, learning_rate)`: implement a single step of weight updates using contrastive convergence
    Arguments:
    - W: the weight matrix for the network
    - v_0: a matrix of rows consisting each of which contains the initial visible layer for an instance (the design matrix)
    - learning_rate: the learning rate to be used for weight updates

* `MAE(v_0)`: computes the generated visible layers for each instance using the current weight matrix (W) and returns the mean absolute error over the entire dataset
    Arguments:
    - v_0: a matrix of rows consisting each of which contains the initial visible layer for an instance (the design matrix)

* `RBM_learn(self, v_0, learning_rate, num_epochs, verbose = 1)`: trains the RBM network object using contrastive divergence
    Arguments:
    - v_0: a matrix of rows consisting each of which contains the initial visible layer for an instance (the design matrix)
    - learning_rate: the learning rate to be used for weight updates
    - num_epochs: the desired number of epochs to train for
    - verbose: a binary indicator. '1' provides MAE updates after each epoch. '0' runs silently, without real-time updates. (Default is '1')

* `RBM_learn_adaptive(self, v_0, learning_rate, num_epochs, tau, verbose = 1)`: trains the RBM network object using search-then-converge, adaptive learning rate approach. Namely the learning rate for epoch <img src="https://render.githubusercontent.com/render/math?math=n"> is given by 

<img align = "center" src="http://www.sciweavers.org/tex2img.php?eq=%5Ceta%28n%29%20%3D%20%5Cfrac%7B%5Ceta_0%7D%7B1%20%2B%20n%2F%5Ctau%7D&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=0" align="center" border="0" alt="\eta(n) = \frac{\eta_0}{1 + n/\tau}" width="124" height="42" />

---

**NOTE:** The "Description of Objects/Methods" section is still being completed.
