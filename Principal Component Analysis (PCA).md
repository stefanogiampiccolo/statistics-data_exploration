**GOAL**: to transform the original high-dimensional dataset into a lower-dimensional space **while preserving as much of the variance** or structure in the data as possible.

# Overview
PCA identifies **principal components** of the dataset:

**Def (Principal components)**: the p.c. are *linear combinations* of the original features, so that
1. they are *uncorrelated*
2. the first principal component *captures the largest amount of variance*, the second principal component *captures the second largest amount*, and so on.

Principal components are a new basis for the space, that has some nice properties regarding the covariance structure of my data (that allows me to consider just the first $n$ components).

Since PCA relies on variance as an indicator of information:
1. It's sensitive to *variable re-scaling*
2. It's sensitive to *outliers*.

# Mathematical explanation
See [[PCA (math details)]].

# How to interpret the PCA results

## Step 1: check the explained variance
Given by the eigen-values of the covariance matrix, it is particularly important to know how many  principal components I should keep. For example, in IRIS dataset:
![[Pasted image 20230319122016.png]]
The PCA is telling me that the IRIS points living in $\mathbb{R}^4$ where actually substantially laying on a two dimensional plane. 

The highest variance explained the better, it is telling me *how much I am simplifying the actual structure fo the data* by considering only the first $m$ principal components. 

## Step 2: the scoreplot
It's the plot in which I'm visualizing the scores of my samples considering just the first principal components. It can give insights about clustering and about what is the cause the experimental variability.  

![[Pasted image 20230319122626.png]]

## Step 3: the loadings 
Loadings tell us how the principal components are formed (as linear combinations of the original features). For example, for the IRIS dataset, we have

![[Pasted image 20230319123623.png | 500]]

This is telling me that, for example, sepal.width is less contributing to the PC1, but it has a greater contribution of PC2. In some sense, this states how variable are represented in the first principal components.

I can have the same information by looking at the *loading plot*:

![[Pasted image 20230319123943.png | 300]]

(even if I think that this must be in some way correlated with the variance explained: it's alway true, however, that if one original feature is under-represented in the first components, I cannot draw any conclusion about it by considering just the first PCs).

## Step 4: the biplots
![[Pasted image 20230319124318.png | 600]]

The biplot is a very effective visualization of my dataset, it could be a great starting point for data exploration of an highly dimensional dataset. In particular, here we can see together:

1. If the label (species in this case) is the greatest source of variability (*data structure*)
2. The *loadings* with the direction of the arrows (even if we have to be *careful* because here they're *rescaled*)
3. The *arrows* are *pointing* in the direction of the samples in which the *feature is higher* (e.g. petal width and petal length will be higher in virginica)
4. Two *arrows pointing in the same direction* suggest that the associated variables *could be correlated*. 

