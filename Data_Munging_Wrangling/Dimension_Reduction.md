# Dimension Reduction
What is Dimension Reduction?

Reducing dimensions of feature sets (basically the number of columns of each frame)

## Motivation
Problems with higher dimensions:
- higher dimensions create problems, which don't exist in lower dimensions
- more features is more or less equivalent ("<=>") to more samples required for training
- higher chance of overfitting with higher dimensional features => bad performance

Advantages of dimensioanlity reduction:
- higher accuracy due to less misleading data
- less features = less training samples = less training time
- less storage for samples required
- no redundant features or noise

## Feature selection and feature engineering

### Feature selection
The process of identifying and selecting relevant features from samples.
- can be done manually or programmatically

**Tools**:
- heatmaps for correlation between features
- visualizing relationships between features and target variables by plotting features against targets
- Variance-Threshold
    - drops features which variance along the column does not exeed a threshold value
- Univariante selection
    - uses statistical tests to select features

#### Linear dimensionality reduction methods
- PCA (Principal Component Analysis) see more [here](https://wiki.godesteem.de/wiki/pca-using-svd/)
    - used for continuous data
- Factor Analysis
    - reduces alarge number of variables to fewer number of factors
    - observations are assumed to be caused by linear transf. of lower dimensional latent factors and added Gaussian noise
- LDA (Linear Discriminant Analysis)
    - projects data to maximise separability

#### Non-linear dimensionality reduction methods (manifold learning methods)
- used for data outside of a linear subspace
- based on the manifold hypothesis which says that in a high dimensional structure, most relevant information is concentrated in small number of low dimensional manifolds
- methods
    - Multi-dimensional scaling (MDS)
        - used to analyze similarity or dissimilarity of data as distance in geometric spaces
        - projects data points into a lower dimension, but keeps data points that are close to each other (Eukl. dist.) close to each other
    - Isometric Feature Mapping (Isomap)
        - same as MDS, but uses gedesic distance (shortest distance between points on a curve)
    - Locally Linear Embedding (LLE)
        - recovers global non-linear structure from linear fits
    - Hessian Eigenmapping (HLLE)
        - reduces dimension while preserving the local neighbourhood, like LLE but uses Hessian operator
    - Spectral Embedding (Laplacian Eigenmaps)
        - maps nearby input to nearby outputs
        - preservves locality rather than local linearity
    - t-distributed Stocastic Neighbor Embedding (t-SNE)
        - computes probability that data point pairs in higher dimensional space are related and then chooses a low-dimensional embedding which produces a similar distribution

#### Auto-encoders
Type of artificial NN that aims to copy their inputs to their outputs by compressing the input into a latent-space representation and then reconstruct the output from this representation and is composed of two parts
- encoder
    - compresses input into latent-space
- decoder
    - reconstructs the input from latent-space

### Feature engineering
Manually generating new features from existing features, by applying transformations or some operation on them.