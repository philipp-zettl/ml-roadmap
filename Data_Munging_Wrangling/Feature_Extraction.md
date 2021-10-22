# Feature Selection/Extraction
- big datasets require dimensionality reduction
- feature selection can significantly improve the learning algorithm's performance
- the required number of samples grows exponentially with the number of variables

## Relevance of features
- two degrees of relevance: weak and strong

### Strong relevance
Imagine we have the set of features `S_i = {f1, …, f_{i-1}, f_{i+1}, …, f_n}`.  
A feature `f_i` is strongly relevant, if there exstists some `x_i`, `y` and `s_i` for which  
`P(f_i = x_i, S_i = s_i) > 0` such that
```
P(Y = y | f_i = x_i; S_i = s_i) != P(Y = y | S_i = s_i)
```
This means that removing `f_i` will always result in a performance deterioration of an optimal Bayes classifier.

### Weak relevance
A feature `f_i` is weakly relevant, if it is not strong relevant and there existis a subset of features `S_i'` of `S_i` for which there exists some `x_i`, `y` and `s_i'` with `P(f_i = x_i; S_i' = si') > 0` such that
```
P(Y = y | f_i = x_i; S_i' = s_i') != P(Y = y | S_i' = s_i')
```
That means that there exists a subset of features, `S_i'`, such that the performance of an optimal Bayes classifier on `S_i'` is worse than `S_i'` with` f_i`