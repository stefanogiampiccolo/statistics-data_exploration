**Def**: arise when a statistical analysis involves multiple simultaneous statistical tests, each of which has a potential to produce a "discovery."

### Example
Suppose we consider the efficacy of a drug in terms of the reduction of any one of a number of disease symptoms. Now suppose that the drug is completely ineffective, so for each symptom $i$ we have a test with signifance level $\alpha \leq 0.05$ to reject the (true) null hypothesis "no effect". If we assume that all the tests are indipendent, for $n$ tests perfomed the probability of rejecting one null hypothesis by chance (event $B$) amounts to
$$
\mathbb{P}(B) = 1-\alpha^n \to 1
$$

# Solutions
Several techniques, requiring a **stricter significance level** for individual tests.

[[Bonferroni correction]]
[[False discovery rate]]
