# Linear Algebra

**Reference book**: [Linear Algebra Done Right](http://linear.axler.net/), Sheldon Axler.

## Vector spaces
A **vector** $$x$$ is a list of elements from a **field** $$F$$. We are only interested in the fields $$R$$ (real numbers) and $$C$$ (complex numbers).

$$ x \in F^n, {x_1, x_2, ..., x_n | x_i \in F} $$

### Properties of a vector space

Vectors $$u, v \in V$$.

**Commutative**: $$u + v = v + u$$

**Associative**: $$(u + v) + w = u + (v + w)$$

**Additive identity**: $$u + 0 = 0$$

**Additive inverse**: $$u + u^{-1} = 0$$

**Multiplicative identity**: $$1u = u$$

**Distributive**: $$a(u + v) = au + av$$

### Subspaces

$$U$$ is a subspace of $$V$$ if

**Additive identity exists**: $$0 \in U$$

**Closure under addition**: $$u, v \in U \implies u + v \in U$$

**Closure under scalar multiplication**: $$a \in F, u \in U \implies au \in U$$

Examples of subspaces are:

1. In $$R^2$$, lines through the origin are subspaces.
2. In $$R^3$$, lines and planes through the origin are subspaces.

### Sums
For $$U_1, U_2, ..., U_n$$, the **sum** is defined as

$$U_1 + U_2 + ... + U_n = {u_1 + u_2 + ... + u_n, u_1 \in U_1, ..., u_n \in U_n }$$

If each $$U_i$$ is a subspace of $$V$$, then the sum is also a subspace of $$V$$.

**Direct sum**: $$V$$ is a direct sum of $$U_1, ..., U_n$$ if for every $$v \in V$$

$$v = U_1 + U_2 + ... + U_n$$ uniquely

