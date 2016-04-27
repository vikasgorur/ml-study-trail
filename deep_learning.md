# Deep Learning

## Introduction

Deep learning became practical due to two reasons:
  - Lots of training data is now available.
  - GPUs are very, very fast (up to 70x performance of CPUs).

Classification can be used as the basis for other tasks like detection (e.g., detecting a face in an image) or ranking (e.g., search results).

## Logistic Classifier

$$\mathbf{WX} + \mathbf{b} = \mathbf{y}$$

The softmax function is used to turn the output vector into a vector of probabilities that sum of 1.

### Input scale
If all inputs to softmax are multiplied by 10, the probabilities get more extreme (closer to 0 or 1).

If all inputs are divided by 10, the probabilities get closer to each other.

We want the classifier to be less sure in the beginning and grow confident as it looks at more data.

**One-hot encoding**: A vector where only the correct class has value 1, all others are 0.

**Cross-entropy**: A function that is used to measure the error.

See [this blog post](http://colah.github.io/posts/2015-09-Visual-Information/) for extensive background on cross-entropy and information theory.

Cross entropy is a smooth function.

**Loss function**: The loss function is the average of the cross-entropy across all training examples. Our goal is to minimize the loss function.

### Numerical stability

Don't add very small numbers to very big numbers.

Try to keep everything with mean 0 and equal variance.

Initialize the weights such that they are normally distributed and have a small standard deviation.

## Measuring Performance

The classifier will try to "memorize" the training set (overfitting).

**subtle**: If you train many models and tweak parameters using the same test data, the model gets information about the test data through you! This will cause overfitting.

To avoid this, set aside a portion of the training data for *validation*, and only use this to make adjustments to the model. Always measure performance using the test data.

**Cross-validation**: A more sophisticated technique for splitting data into multiple training and test datasets.

Don't tweak the knobs too much!

**Validation and test data size**:

*The rule of 30*: If a change affects atleast 30 examples, the change made to the model is statistically significant.

If the validation set size is > 30,000 examples, a 0.1% change in performance is significant.

Getting more data always helps.

### Stochastic Gradient Descent

**Rule of thumb**: If computing the loss function takes n FLOPs, computing the gradient takes 3n FLOPs.

It is time consuming to compute the actual gradient when you have lots of data. Instead, use a *terrible* estimate: compute the gradient using only a tiny sample (1 to 1000) of the training data.

Take small steps and lots of steps.

SGD is a bad optimizer but the only one that is practical.

#### Helping SGD

**Momentum**: Instead of gradient at current step, use a moving average.

**Learning rate decay**: Make the learning rate smaller as training steps increase.

**Parameter hyperspace**: How quickly the model learns has nothing to do with how well it performs.

*Always lower your learning rate*.

**ADAGRAD**: does automatic tweaking of hyperparameters.