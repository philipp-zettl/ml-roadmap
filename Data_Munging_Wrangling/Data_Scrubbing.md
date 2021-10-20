# Data Scrubbing
Incorrect or inconsistent data leads to false conclusions. This correlates with fact that the cleaner your data and the better you understand it impacts the quality of your results.

To ensure quality data we can follow a few steps summarized here

## Data quality

### Validity
- Data-Type constraints
- range constraints
- mandatory constraints
- unique constraints
- set-membership constraints
- foreign-key constraints
- regular expression patterns
- cross-field validation

### Accuracy
- Does the data represent the reality?
- Precision is not Accuracy

### Completeness
- existis missing data?
- to what degree is the required data complete?

### Unformity
Does the data need to be transformed or converted to have the same unit within a feature?

## The Workflow
1. Inspection:
    - detect unexpected, incorrect, inconsistent data
2. Cleaning
    - fix or remove anomalies
3. Verifying
    - after cleaning inspect data to verify correctness
4. Reporting
    - create report about the performed changes and the quality of the current data

This workflow can be iterated many times to achive better results.

### Inspection
Inspecting data is time consuming and there are many methods to perform inspections.
#### Data profiling
Generate a summary statistic to get a general idea of the data.
- How's the data distributed?
- what kind of datatypes do we have? ...

#### Visualization
By using statistical methods like mean, std, range, or quantiles one can find unexpected or erroneous values.

### Cleaning
Data cleaning involve different techniques based on the problem and the data type. Different methods can be applied with each has its own trade-offs.
Overall, incorrect data is either removed, corrected, or imputed.

#### Irrelevant data
Irrenevant data that doesn't fit into the context of the problem we're solving.

**Only if** you are sure that a piece of data is unimporant you may drop it.
Otherwise use the correlation matrix to explore feature correlations or consult domain experts.

#### Duplicates
Duplicates are not needed and only overfit the model

#### Type conversions
Convert enums into numericals. This step basically moves the whole data into some domain we can later use. Unknown values should be converted to NA and produce errors. Those values need to be fixed.

#### Syntax errors
- remove whitespaces
- pad strings to fixed lengths
- fix typos in values
- combine equal values to same identifiers (example: "No", "no", "n", "N" are all the same value)

#### Standardize
- put strings into lower-/uppercase
- numerical values have all same precision / units
- date formats are equal
- ...

#### Scaling / Transforming
- Scale values to some specific domain, like [0, 1] or [0, 100]
- scaling and transforming allows plotting and visualization of different scores

#### Normalization
[see here](Data_Munging_Wrangling/Normalization.md)

#### Missing values
1. Drop
    - if missing values are very rare and randomly we can just drop those records
    - if many missing values we can most likely drop the whole column
2. Impute
    - generates new data points based on existings
    - uses statistical values like mean (not [skewed data](https://medium.com/omarelgabrys-blog/statistics-probability-exploratory-data-analysis-714f361b43d1#92d4)) or median (not sensitive to outliners; skewed data)
3. Hot-deck

currently at [here](https://towardsdatascience.com/the-ultimate-guide-to-data-cleaning-3969843991d4#4acb)