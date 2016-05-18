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

