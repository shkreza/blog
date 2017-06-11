---
title: "Black art of neural networks (#4)"
layout: post
theme: default
category: building
---
# Network architecture
  1. Problem with small gradients in too deep networks
  2. Error function - squared error vs. cross-entropy (logistic function
          plateuing at -1 & 1 or softmax unit making it difficult to train due
          to too small gradient using squared error)

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
  1. Restrict the parameters - weight sharing (such as how )
  2. Dropout
  3. Using validation dataset to monitor changes in error rate - if error
  increases, we are starting to overfit. Also, initial training of networks may
  push the network to produce output proportional to the population in the
  input data. It takes longer for network to improve beyond this guessing and
  actually learn things.

# Learning data size
  1. Mini batch learning: make sure data is random and each batch has
  representative set of data.
