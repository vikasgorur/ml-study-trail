# Probability & Statistics

**Reference book**: [All of Statistics](http://www.stat.cmu.edu/~larry/all-of-statistics/), Larry Wasserman.


## Probability

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

$$f_{X,Y}(x) = \sum_{x}f(x, y)$$

We are summing over all values of the other variable ($$Y$$). This can be used to define conditional mass functions as well.

### Transformations of Random Variables

Let $$Y = r(X)$$. We wish to find the density of $$Y$$.

1. For each y, find the set $$A_y = {x : r(x) \le y}$$
2. Find the CDF:

    $$F_Y(y) = P(r(X) \le y) = \int_{A_y} f_X(x) dx$$
3. The PDF is:

    $$f_Y(y) = F'_Y(y)$$
  
**Generating samples**: Let $$X$$ be a random variable with the CDF $$Y = F_X(x)$$. We know that $$Y$$, being a probability takes on values between 0 and 1. Thus if we wanted to generate samples of $$X$$ we can derive them from samples of $$Y$$ via:

$$x = F^{-1}(y)$$

## Expectation

**Definition**: The **expected value**, **mean**, or **first moment** of a random variable $$X$$ is defined as:

$$E(X) = \sum_{x}x \, f(x)$$ (discrete)

$$E(X) = \int x \, f(x) dx$$ (continuous)

The expected value (mean) can sometimes not exist!

For the Cauchy distribution defined by $$f(x) = \frac{1}{\pi (1 + x^2)}$$, the mean diverges to $$\infty$$. This means that if you take a number of observations, the mean never settles down.

**Theorem (The Rule of the Lazy Statistician)**: Let $$Y = r(X)$$. Then,

$$E(Y) = E(r(X)) = \int r(x) \, dF_{X}(x)$$

**Explanation:** This is better written as

$$E(r(X)) = \int r(x) \, f_X(x) dx$$

See [Law of the unconscious statistician](https://en.wikipedia.org/wiki/Law_of_the_unconscious_statistician) for more details.

### Properties of Expectations

If $$X_1, X_2, ..., X_n$$ are random variables and $$a_1, a_2, ..., a_n$$ are constants,

$$E(\sum_i a_iX_i) = \sum_i a_i E(X_i)$$

Let $$X_1, X_2, ..., X_n$$ be **independent** random variables. Then,

$$E(\prod_{i=1}^{n} X_i) = \prod_i E(X_i)$$

### Variance and Covariance

**Definition**: Let $$X$$ be a random variable with mean $$\mu$$. The **variance** of $$X$$ is defined by

$$V(X) = \sigma^2 = E[(X - \mu)^2] = \int(x - \mu)^2 dF(x)$$

$$\sigma = \sqrt{V(X)}$$ is the standard deviation.

**Properties of variance**:

  1. $$V(X) = E(X^2) - \mu^2$$
  2. If a and b are constants then $$V(aX + b) = a^2V(X)$$

**Definition**: Let $$X$$ and $$Y$$ be random variables with means $$\mu_X$$ and $$\mu_Y$$ and standard deviations $$\sigma_X$$ and $$\sigma_Y$$. Define the **covariance** by:

$$Cov(X, Y) = E((X - \mu_X)(Y - \mu_Y))$$

and the **correlation** by:

$$\rho(X, Y) = \dfrac{Cov(X, Y)}{\sigma_X\sigma_Y}$$

The covariance satisfies

$$Cov(X, Y) = E(XY) - E(X)E(Y)$$

The correlation is a scaled version of the covariance and satisfies

$$-1 \le \rho(X, Y) \le 1$$

**Definition**: If $$X$$ is a random vector, the **covariance matrix** $$\Sigma$$ is defined by

$$\Sigma_{i, j} = Cov(X_i, X_j)$$ when $$i \ne j$$
$$\Sigma_{i, j} = V(X_i)$$ when $$i = j$$

### Conditional Expectation

If $$X$$ and $$Y$$ are random variables, the mean of $$X$$ among those times when $$Y = y$$ is given by

$$E(X|Y = y) = \int x \, f_{X|Y}(x|y) \, dx$$

**Iterated Expectations**: For random variables $$X$$ and $$Y$$,

$$E[E(Y|X)] = E(Y)$$

$$E[E(X|Y)] = E(X)$$

**Definition**: The **conditional variance** is defined by

$$V(Y|X = x) = \int (y - \mu(x))^2 \, f(y|x) \, dy$$

where $$\mu(x) = E(Y | X = x)$$

### Moment Generating Functions

**Definition**: The **moment generating function** (also called Laplace transform) of $$X$$ is defined by

$$E(e^{tX}) = \int e^{tx} \, dF(x) $$

$$e^{tX}$$ can be written as an infinite series (Taylor expansion) whose successive coefficients are the moments of $$X$$. See [here](https://en.wikipedia.org/wiki/Moment-generating_function) for more details.

## Convergence

**The Law of Large Numbers**: The sample mean of a variable $$X$$ approaches $$E(X) = \mu$$ as the sample size gets larger.

### The Central Limit Theorem

For any random variable $$X$$, the sample mean $$\bar{X}$$ has a distribution that is approximately normal with mean $$\mu$$ and variance $$\sigma^2/n$$. In other words,

$$\dfrac{\sqrt{n} \, (\bar{X_n} - \mu)}{\sigma} \to Z$$

where $$Z \sim N(0, 1)$$

