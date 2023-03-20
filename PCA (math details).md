From https://en.wikipedia.org/wiki/Principal_component_analysis.

**Def**: PCA is an **orthogonal linear transformation** that transforms the data to a new **coordinate system** such that the greatest variance of the data comes to lie on the first coordinate (called the first principal component), the second greatest variance on the second coordinate, and so on.

*Why orthogonal?*: PCA wants just to rotate the coordinate system, in such a way that the <ins>new basis found is orthogonal</ins> (from this descends also the <ins>linear independence</ins> of the new axes).  

# How to derive principal components

Consider a $n \times p$ data matrix $\mathbf{X}$, with column-wise zero empirical mean. Here the rows are the samples, whereas the columns are the features of the dataset.

We want to find an orthogonal matrix $\mathbf{W}$, that will define my transformation, so that (invert and traspose because things are transposed in this data matrix)
$$
T = \mathbf{X} \cdot \mathbf{W}
$$
will be the basis change matrix with the desired properties. 
*Columns of* $W$: principal components expressed in the original basis system

## First component

We have to find a unitary vector $\mathbf{w}_1$, such that 
$$
\mathbf{w_1}= argmax_{||w||=1}\Bigl\{\sum_i (T_{i,1})^2\Bigl\} = argmax_{||w||=1}\Bigl\{\sum_i (X_i \cdot \mathbf{w})^2\Bigl\} = 
argmax_{||w||=1}(||X \cdot \mathbf{w}||)^2
$$
Since $|| \mathbf{w} || = 1$, we can re-write the function to maximize as:

$$
argmax_{||w||=1}(||X \cdot \mathbf{w}||)^2 = argmax_{||w||=1}(\mathbf{w}^t \cdot X^t \cdot X \cdot \mathbf{w}) = argmax_{||w||=1}\frac{(\mathbf{w}^t \cdot X^t \cdot X \cdot \mathbf{w})}{\mathbf{w}^t \cdot \mathbf{w}}
$$
This is known as Raileigh quotient, that for a semi-positive definite matrix has as solution the maximum *eigenvalue* of $X^t \cdot X$, that occurs when $\mathbf{w}$ is the relative *eigen-vector* (if the geometric multiplicity is $\geq 2$ , one of the eigen-vector will be selected).

## Further components

In order to find the $k^{th}$ principal component, we have to maximize the *variance of the residual*, i.e. 
$$
\hat{X}_k = X-\sum_{i=1}^{k-1}(X \cdot \mathbf{w_i})\cdot\mathbf{w}_i^t
$$
With this definition, we can proceed as before finding that the solution is the largest *eigen-vector* of $\hat{X}_k^t \cdot \hat{X}_k$, that can be proven to be the $k^{th}$ eigenvector of the original $X^t \cdot X$. 

# Results

The desired matrix $W$ to define the PCA transformation
$$
T = \mathbf{X} \cdot \mathbf{W}
$$
1. Is a $p \times p$ matrix (feature dimension)
2. It has as *columns the eigen-vectors of* $X^t \cdot X$, the covariance matrix. 
3. The *corresponding eigen-values* are the *variance explained* by the component.
4. The transposed of $W$ si called *whitening matrix* (actually you have to divide by the eigen-values). 

# Summary

Given a $n \times p$ sample matrix $X$, centered in zero, we can identifying the principal components as the eigen-vectors of the covariance matrix $X^t \cdot X$. 

The matrix $W$ that has as *columns the normalized and ordered eigen-vector of the covariance matrix* defines an orthogonal transformation:
$$
\alpha(v) = W \cdot v^t \text{ with } v \in \mathbb{R}^p
$$
that allows me to compute the scores of a generic vector $v \in \mathbb{R}^p$. 
Since the transformation is othogonal, the inverse transformation:
$$
\alpha^{-1} = W^t \cdot w^t \text{ with } w \in \mathbb{R}^p
$$
allows me to understand the composition of the principal components (rows of $W$ or columns of $W^t$). 

Since the goal is the dimensionality reduction, it is in some way convenient to shift in the column-major notation, with column-vectors. In this way, I can "crop" the matrix $W$ to the first $m$ prinicipal components, defining the projection transformation:
$$
\pi(v) = v^t \cdot W_m
$$

# Disclaimer about dimensions and ranks
What is the rank of the covariance matrix? It can be shown that it is the same as the one of the original matrix $X$.
![[Pasted image 20230319120252.png]]
We have therefore the first limit that the number of eigen-vectors is bounded by the $min(p, n)$. 

After that, it follows by the *spectral theorem* that there are an othonormal basis of $\mathbb{R}^p$ composed by eigen-vectors: in the not-full-rank scenario, you will end up with some zero-variance components that will be excluded from the dimensionality reduction.