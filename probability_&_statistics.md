# Probability & Statistics

**Reference book**: [All of Statistics](http://www.stat.cmu.edu/~larry/all-of-statistics/), Larry Wasserman.


## Probability
**(Chapter 1)**

The **sample space** $$\Omega$$ is the set of all possible outcomes of an experiment. Subsets of $$\Omega$$ are called **events**. $$A_1, A_2, ..., A_k$$ is called a **partition** if their union is $$\Omega$$.

**Lemma**: For any events $$A$$ and $$B$$,

$$P(A \cup B) = P(A) + P(B) - P(AB)$$

where $$AB$$ is the event that both $$A$$ and $$B$$ happen.

**Definition**: Two events $$A$$ and $$B$$ are **independent** if

$$P(AB) = P(A)\,P(B)$$

**Definition**: If $$P(B) \geq 0$$ then the **conditional probability** of $$A$$ given $$B$$ is

$$P(A|B) = \dfrac{P(AB)}{P(B)}$$

$$P(A|B)$$ is the fraction of times $$A$$ occurs among those in which $$B$$ occurs.

**Lemma**: For any events $$A$$ and $$B$$,

$$P(AB) = P(A|B)\,P(B)$$

**Bayes' Theorem**: Let $$A_1, A_2, ..., A_k$$ be a partition of $$\Omega$$. Then,

$$P(A_i|B) = \dfrac{P(B|A_i) \, P(A_i)}{\Sigma_j P(B|A_j) \, P(A_j)} $$

## Random Variables
**(Chapter 2)**

**Definition**: A **random variable** is a mapping that assigns a real number $$X(\omega)$$ to each outcome in $$\Omega$$.

**Defintion**: The **cumulative distribution function** is $$F_X : R \to [0, 1]$$:

$$F_X(x) = P(X \le x) $$

**Definition**: The **probability mass function** is defined by $$f_X(x) = P(X = x)$$. Also,

$$F_X(x) = \sum_{x_i \le x} f_X(x)$$

For a continuous random variable X, the corresponding functions are:

$$P(a \lt X \lt b) = \int_{a}^{b}\, f_X(x) \,dx $$

$$F_X(x) = \int_{-\infty}^{x}\,f_X(t)\,dt$$

In the continuous case $$f_X(x)$$ is called the probability **density** function, and probabilities are obtained by integrating.

### Some Important Discrete Random Variables

**Bernoulli Distribution**: $$X$$ is a binary coin flip. $$P(X = 0) = p$$ and $$P(X = 1) = 1-p$$. The mass function is:

$$f(x) = p^x(1-p)^{(1-x)}$$ for $$x \in \{0, 1\}$$

**Binomial Distribution**: We have a coin with probability $$p$$ of falling heads. $$X$$ is the number of heads in $$n$$ trials.

$$f(x) = {n \choose x} p^x (1-p)^{n-x}$$

### Some Important Continuous Random Variables

**Normal (Gaussian) Distribution**: $$X$$ has the normal distribution with parameters $$\mu$$ and $$\sigma$$:

$$f(x) = \dfrac{1}{\sigma\sqrt{2\pi}} \, exp(- \dfrac{1}{2\sigma^2} \, (x -\mu)^2)$$

The **standard normal distribution** has $$\mu = 0, \sigma = 1$$.

### Bivariate Distributions
If $$X$$ and $$Y$$ are random variables, their **joint mass function** is defined as:

$$f_X(x, y) = P(X = x, Y = y)$$

The joint function can be "curried" to obtain **marginal mass functions**. For $$X$$,

$$f_X(x) = \sum_{x}f(x, y)$$

We are summing over all values of the other variable ($$Y$$). This can be used to define conditional mass functions as well.

### Multivariate Distributions
Let $$X = (X_1, X_2, ..., X_n)$$ be a **random vector**.

TODO
**Multinomial Distribution**
**Multivariate Normal**

### Transformations of Random Variables