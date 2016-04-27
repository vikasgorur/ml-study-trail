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
