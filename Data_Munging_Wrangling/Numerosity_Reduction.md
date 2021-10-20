# Numerosity Reduction
Numerosity Reduction is a technique which replaces the original data by smaller form of data representation. There are two techniques for numerosity reduction
- Parametric Methods
- Non-Parametric Methods

## Parametric Methods
Data is represented as some model, which estimates the data, so that only parameters of data are required to be stored, instead of actual data.
**Regression** and **Log-Linear** methods are used for creating such models.
Both models can be used on sparse data, although their application may be limited

### Regression Model
Can be linear or mutiple linear regression ([more notes and orthogonal example](https://wiki.godesteem.de/wiki/orthogonal-linear-regression/))

### Log-Linear Model
Used to estimate the probability of each data point in a multidimensional space for a set of discretized attributes, based on a smaller subset of dimensional combinations.

## Non-Parametric Methods
- Histograms
    - frequency representations
    - approximates data distribution which uses binning
- Clustering
    - clusters data into groups/clusters
    - clustered data will be promoted to used dataset
    - helps detecting outliners
- Sampling
    - allows a large data set to be represented by a much smaller random data sample
- Data Cube Aggregation
    - moves the data from detailed level to a fewer number of dimensions
    - resulting set is smaller in volume but without loss of information