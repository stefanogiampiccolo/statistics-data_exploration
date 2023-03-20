# Histograms
The first and most powerful tool to grasp an idea about the data distribution is plotting an histogram of my data

![[Pasted image 20230319145429.png | 500]]

From an histogram you can clearly see if the empirical distribution is symmetrical or asymmetrical.

# QQ-plots

**Def**: a QQ-plot, or quantile-quantile plot, is a graphical tool used in statistics to compare the distribution of a given dataset with a reference probability distribution, often a normal (Gaussian) distribution.

## How to create a QQ-plot
1.  Sort the data in ascending order.
2.  Calculate the empirical quantiles for the dataset. For each data point, its empirical quantile is its rank divided by the total number of data points.
3.  Compute the theoretical quantiles of the reference distribution, such as the normal distribution.
4.  Plot the sorted data values (y-axis) against the corresponding theoretical quantiles (x-axis).

An example is the following one

![[Pasted image 20230319145926.png | 400]]

## How to interpret a QQ-plot
1. *Points aigned on identity line*: the data follow the reference distribution
2. *Points exhibiting a linear behaviour but different from identity*: the data may be consistent with your distribution family, although they have different mean and different sd from the reference distribution. In the normal case in particular if the $q$ is different from zero we have a different mean, whereas if the $m$ is different from one we have another variance). 

## Normal QQ-plot
In the case of normal QQ-plot, we can standardize our distribution and compare it with a standard gaussian. The following picture tells us how to interpret a normal QQ-plot if it's not fitting the identity line. 

![[Pasted image 20230319152236.png]]


