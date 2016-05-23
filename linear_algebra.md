# Linear Algebra

**Reference book**: [Linear Algebra Done Right](http://linear.axler.net/), Sheldon Axler.

**Blog posts**:

[Linear Algebra, A Primer](https://jeremykun.com/2011/06/19/linear-algebra-a-primer/), Jeremy Kun.

[Inner Product Spaces, A Primer](https://jeremykun.com/2011/07/25/inner-product-spaces-a-primer/), Jeremy Kun.

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

### Span and Linear Independence

A **linear combination** of vectors in $$V$$ is of the form

$$a_1v_1 + a_2v_2 + ... + a_nv_n$$

The **span** of a set of vectors $$v_1, v_2, ..., v_n$$ is the set of all its linear combinations. If the span equals $$V$$, we say that the set **spans** $$V$$.

A list of vectors in $$V$$ is called **linearly independent** if the only way to express 0 as their linear combination is to set all $$a_1, a_2, ... a_n = 0$$.

A **basis** is a list of vectors in $$V$$ that is linearly independent and spans $$V$$. The **standard basis** of $$V$$ is

$$((1, 0, ..., 0), (0, 1, ..., 0), ..., (0, 0, ..., 1))$$

Every vector in $$V$$ can be uniquely expressed as a linear combination of the basis.

Every finite-dimensional vector space has a basis, and all the bases are of the same length, which is the **dimension** of that space.

## Linear Maps

A **linear map** from $$V$$ to $$W$$ is a function $$T: V \to W$$ with the following properties:

**additivity**
    $$T(u + v) = Tu + Tv$$
  
**homogeneity**
    $$T(av) = a(Tv) \, \text{for all} \, v \in V, a \in F$$
    
The set of all linear maps from $$V$$ to $$W$$ is denoted by $$L(V, W)$$.

**zero**: $$0v = v$$

**identity**: $$Iv = v$$

$$L(V, W)$$ is itself a vector space. The **product** of two maps $$ST$$ is the composition of the maps.

### Null Spaces and Ranges

For $$T \in L(V, W)$$, the **null space** (kernel) of $$T$$ is the subset of $$V$$ that $$T$$ maps to 0.

  null $$T = \{v \in V : Tv = 0\}$$
  
The **range** of $$T$$ is the subset of $$W$$ that are the results of the mapping.

  range $$T = \{Tv : v \in V\}$$
  
**Theorem**: If $$V$$ is finite dimensional and $$T \in L(V, W)$$, then range $$T$$ is a finite-dimensional subspace of $$W$$ and

  dim $$V$$ = dim null $$T$$ + dim range $$T$$
  
### Matrices

A linear map $$T: V \to W$$ from n-dimensional space $$V$$ to m-dimensional space $$W$$ is represented by an $$m \times n$$ matrix.

The set of all m-by-n matrices with entries in $$F$$ is denoted $$Mat(m, n, F)$$ and is a vector space w. r. t. matrix addition and scalar multiplication.

### Invertibility

For a linear map $$T$$ the **inverse** ($$T^{-1}$$), if exists, is unique and defined by

  $$TT^{-1} = I$$
  
Two vector spaces are **isomorphic** if an invertible linear map between them exists.

A linear map from a vector space to itself is called an **operator**.

## Eigenvalues and Eigenvectors

For $$T \in L(V)$$ (operator on $$V$$) and $$U$$ a subspace of $$V$$, we say that $$U$$ is **invariant** under $$T$$ if $$u \in U \implies Tu \in U$$.

For $$T \in L(V)$$, $$\lambda$$ is called the **eigenvalue** and $$u$$ is called an **eigenvector** when

  $$Tu = \lambda \, u$$
  
In other words, the set of eigenvectors is given by

  null$$(T - \lambda\,I)$$
  
An operator has an eigenvalue if and only if there exists a nonzero vector in its domain that gets sent by the operator to a scalar multiple of itself.

**Theorem**: The eigenvectors of an operator corresponding to distinct eigenvalues are linearly independent. Each operator on $$V$$ has at most dim $$V$$ eigenvalues.

**Theorem**: Every operator on a finite-dimensional, nonzero, complex vector space has an eigenvalue.

### Upper-Triangular and Diagonal Matrices

A matrix is upper-triangular if all entries below the diagonal are 0.

**Theorem**: Suppose $$V$$ is a complex vector space and $$T \in L(V)$$. Then $$T$$ has an upper-triangular matrix with respect to some basis of $$V$$.

The entries on the diagonal are the eigenvalues of $$T$$.

**Theorem**: Suppose $$T \in L(V)$$. Let $$\lambda_1, \lambda_2, ..., \lambda_m$$ denote distinct eigenvalues of $$T$$. Then the following are equivalent:

  1. $$T$$ has a diagonal matrix with respect to some basis of $$V$$
  2. $$V$$ has a basis consisting of eigenvectors of $$T$$.
  