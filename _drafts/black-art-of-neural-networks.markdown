---
title: "Black art of neural networks (#4)"
layout: post
theme: default
category: building
---
I have been interested in neural network learning for quite some time now. The history of these networks are vast and span many decades of (mainly) academic research. With the sharp increase in ll past research

# Network architecture
  1. **Feedforward neworks:** Problem with small gradients in too deep networks
  2. Error function - squared error vs. cross-entropy (logistic function
          plateuing at -1 & 1 or softmax unit making it difficult to train due
          to too small gradient using squared error)
  3. **Convolutional networks:** 
  4. **Echo state networks:**
  5. **Boltzmann machines and restricted Boltzmann machines:**
  6. **-**

# Optimization technique
  1. **Gradient decent optimizers:**
  2. **Hessian free optimizers:**
  3. **-**

# Error functions
  1. **Cross-entropy**
  2. **Maximum likelihood:** The derivative of the probability function is
     zero.
  3. **Square root of squared error:**

# Initializing the weights
  1. Start with random weights - otherwise they will all change together
  2. Pre-training: initializing with RBM (unuspervised learning)
  3. Too big weights may make hidden logistic units to be firmly on or off (the
          regions where they plateu and gradient is small - this is not even a
          local minima).

# Learning rate
Avoiding oscillation and escaping from local minima
  1. Scale the learning rates - turn down learning rate close to the end of
  learning but not too soon.
  2. Use momentum to smoothout the gradient descent learning: use velocity to
  change gradient.
  3. Adaptive adjustment: increase rate if gradient sign stays the same, or
  decrease rate if gradient sign keeps oscilating. You can apply this on a
  per-weight basis (in full batch learnign or with large mini batches) and have
  changes be bound to [.1, 10] or [0.01, 100] to avoid big changes from
  distroying the weights.
  4. rprop: make weight changes proportional to the step size for each weight
  which increases multiplicatively if gradient sign doesn't change and
  decreases multiplicatively if gradient sign changes. Also place limits for
  step changes. Not too good, since it doesn't consider gradient size.
  5. rmsprop: divide learning rate by square root of running average of the
     square size of recent gradients (for each weight).

# Input transformation
Transforming your inputs can help the gradient to point towards the minimum -
making the error surface a circular bowl.
  1. Shifting the input by adding a constant to the inputs while maintain a zero
  mean: this solves the problem of elongated ellipses in the weight space. For
  example inputs of (101, 99) and (101, 101) could be shifted to mean of 0,
  hence transformed to (1, -1) and (1, 1). For hidden units, `2 1. logistic - 1`
  produces similar zero-mean.
  2. Scaled input to make it have variance of 2 (around 1 and -1).
  3. Decorrelate input components using Principal Component Analysis and
  down-scaling them (i.e., divide) by square root of their eigenvalues.

# Overfitting
  1. **Restrict number of parameters and hidden layers:** weight sharing:
  2. **Dropout:**
  3. Using validation dataset to monitor changes in error rate - if error
     increases, we are starting to overfit. Also, initial training of networks
     may push the network to produce output proportional to the population in
     the input data. It takes longer for network to improve beyond this
     guessing and actually learn things.
  4. Averaging different models 
  5. **More training data:** Increasing the amount of training data while
     keeping the network size, helps avoid the network from fitting the data
     perfectly. Of course, if data volume is vastly high, a bigger network is
     needed to properly generalize the larger data set.
  6. **Baysian models:** - average prediction by many models
     model parameters have a probability distribution which gets updated by
     seeind data.

  7. **Early stopping:** Start with small weights and stop learning before
     overfitting, i.e., use training data, validation data and test data.
     Rotation of validation sets is also a good technique on random inputs.when
     error rate on validation set grows.
  8. **Weight decay:** Penalize the network by a function (normally square) of
     the weights - this penalty is added to the error function and pulls the
     weights towards zero unless big error derivaties counter act this decay.
  9. **Weight constraints:** Restrict the squared length of incoming weight
     vector to any given node to a maximum.
  10. **Adding noise to weights, inputs or hidden activities:** we can treat
      activities of neural as stochastic (i.e., a neuron is activated by the
              probably equal to its logistic output). In the backward pass, we
      use the real value of the activation values to compute the derivatives.
  11. **Model averaging:** Averaging different models helps lower bias and
      variance of error. 

# Learning data size
  1. Mini batch learning: make sure data is random and each batch has
  representative set of data.

-- shkreza

{% include disclaimer.html %}
{% if jekyll.environment == "production" %}
  {% include google-analytics.html %}
{% endif %}
