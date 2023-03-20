From https://en.wikipedia.org/wiki/Curse_of_dimensionality

**Def**: term that refers to various problems and issues manifesting when dealing with **high dimensional data**. 

The same problem can arise in different forms.

# Data sparsity
<small>From <ins>Domingos, Pedro. "A few useful things to know about machine learning." _Communications of the ACM_ 55.10 (2012): 78-87.</ins>. See also https://mathematical-coffees.github.io/slides/mc08-delon.pdf for a mathematical discussion</small>.

1. In high dimensions **all examples look alike** in terms of distance. We cannot rely on Euclidean distance to infer a data structure.

![[Pasted image 20230318213546.png]]

Furthermore, the more the dimensions, the more data are sparse in the sample space, with the high risk of overfitting
![[Pasted image 20230320144335.png]]


2. In high dimensions **most of the volume of an orange is in the skin**, not in the pulp. This can be proven mathematically by taking into account the volume of a unit hypersphere, compared with the unitary hypercube. 
![[Pasted image 20230318212905.png]]

![[Pasted image 20230318214339.png]]

**Consequence**: samples are closer to the boundary of the sample space than to other samples, which makes prediction much more difficult. Indeed, near the edges of the training sample, one must extrapolate from neighboring sample points rather than interpolate between them.

# Overfitting 
The number of affine independent points  in $\mathbb{R}^d$ is $d-1$ , that increases with the increase of dimensionality. This is one of the reason why, increasing the number of observed features, can lead to indetifying a structure that can't be generalized, because you find it just by chance

# Remedy
[[Dimensionality reduction]] can mitigate the problem.

