The **goal** of projection is to reduce the dimension of the space, so that I can visualize the (porjected) points. 
It can be performed on a **affine subspace** of $\mathbb{R}^n$ or on other surfaces: the "affine" projections use linear algebra and are quite popular.

# Projection results
Once defined a projection criterion, there are three different things associated to a projection:
1. **SCORES**: the position of the samples on the projection surface
2. **LOADINGS**: the function that maps the original space into the projection surface
3. **PROJECTION ERROR**: a quantification of the error I'm doing approximating my points with the scores.

# Objective function
The definition of a projection can be associated with an *objective function* to maximize. We can obtain different projections by changing the objective function:
  1. *maximizing the projected variance*: the idea is that $variance = information$. With this function you get the [[Principal Component Analysis (PCA)]]
  2. *maximizing the “separation” of two or more sample classes*: LDA
  3. *maximizing the correlation with a third property*: Regression problem (PLS for example) 