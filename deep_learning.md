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

**Cross-entropy**: A function that is used to measure the error (loss function).

See [this blog post](http://colah.github.io/posts/2015-09-Visual-Information/) for extensive background on cross-entropy and information theory.

Cross entropy is a smooth function.

