# Normalization
Normalization is used to scale the data of an attribute so that it falls into a range such as [0, 1] or [-1, 1] and is generally used for classification algorithms.
It is required when dealing with attributes on a different scale.

## Methods of data normalization
- Decimal Scaling
- Min- Max Normalization
- z-Score Normalization (zero-mean Normalization)
- for more see [wikipedia](https://en.wikipedia.org/wiki/Normalization_(statistics))

### Decimal Scaling
The simple example of converting milliliters into liters, by multiplying the dataset with 1000. We basically move the decimal point into some direction.

## Min-Max Normalization
The data get's scaled using the min and max values of the dataset. The formula to perform this operation is

```
v' = (v-min(A))/(max(A)-min(A)) * (new_max(A) - new_min(A)) + new_min(A)
```
where v is the old value of each data entry, A the attribute matrix, min(A) and max(A) the minimum and maximum absolute value of A respectively, new_max(A) and new_min(A) are the max and min values of the range respectively

## Z-score normalization

Normalizes data based on mean and standard deviation of the given data.
The formula to compute this is
```
v' = (v - E(A))/(std(A))
```
