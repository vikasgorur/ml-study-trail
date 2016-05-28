# Statistical Inference

## Fundamental Concepts in Inference

**Point estimation**: Provide a single "best guess" of some quantity of interest. By convention, the point estimate of $$\theta$$ is denoted by $$\hat\theta$$. While $$\theta$$ is a fixed, unknown quantity, $$\hat\theta$$ is a random variable since it depends on the data.

The **bias** of an estimator derived from $$n$$ data points is defined as

bias($$\hat\theta_n$$) = $$E(\hat\theta_n) - \theta$$

The distribution of $$\hat\theta_n$$ is called the **sampling distribution**, and its standard deviation is called the **standard error**.

**Confidence interval**: An $$\alpha$$ confidence interval for a parameter $$\theta$$ is the interval $$C_n = (a, b)$$ such that it contains $$\theta$$ with probability $$1 - \alpha$$.

For example, $$\alpha = .05$$  means that if you construct such confidence intervals over and over throughout your life, 95% of them will contain the true parameter value.

Relevant [XKCD](https://xkcd.com/882/).

**Hypothesis testing**: We try to determine if the available data rejects the **null hypothesis**.

## Parametric Inference

In parametric inference we are trying to estimate parameters of the distribution that generated the given data: $$f(x; \theta)$$, where $$\theta$$ are the parameters.

### The Method of Moments
If the parameter $$\theta$$ has $$k$$ components, the successive moments and sample moments are defined as:

$$\alpha_j = E(X^j) = \int x^j \, f(x)\, dx$$

$$\hat\alpha_j = \dfrac{1}{n}\sum_{i=1}^{n}X^j_i$$

The parameters are estimated by solving the system of equations that sets each moment equal to its sample moment.

$$\alpha_1 = \hat\alpha_1$$
$$\alpha_2 = \hat\alpha_2$$
$$...$$

### Maximum Likelihood

The **likelihood function** is the joint density defined by

$$\mathcal{L_n}(\theta) = \prod_{i=1}^{n}f(X_i; \theta)$$

The log-likelihood is $$\mathcal{l}_n(\theta) = log \, \mathcal{L}_n(\theta)$$. The **maximum likelihood estimator** $$\hat\theta_n$$ is the value of $$\theta$$ that maximizes the likelihood function (or equivalently the log-likelihood).