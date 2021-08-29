# Python Cheat Sheet for R Users / R Cheat Sheet for Python Developers

If you are both an R User and a Python developer, feel free to contribute.

| R                               | Python                                                           |
| :------------------------------ | :--------------------------------------------------------------- |
| getwd()                         | os.getcwd()                                                      |
| setwd(path)                     | os.chdir(path)                                                   |
| ls()                            | globals()                                                        |
| rm(a)                           | del(a)                                                           |
| **R Data Frames**               | **Pandas Data Frames**                                           |
| `read.csv(path)`                | `pd.read_csv(path)`                                              |
| `colnames(df)`                  | `df.columns`                                                     |
| `rownames(df)`                  | `df.index`                                                       |
| `head(df)`                      | `df.head()`                                                      |
| `tail(df)`                      | `df.tail()`                                                      |
| `dim(df)`                       | `df.shape`                                                       |
| `length(df)`                    | `len(df)`                                                        |
| `summary(df)`                   | `df.describe()`                                                  |
| `df[1:3]`                       | `df[0:3]`                                                        |
| `df$A`                          | `df.A`                                                           |
| `df[c('A', 'B')]`               | `df[['A', 'B']]`                                                 |
| `df[1:3, c('A', 'B')]`          | `df.loc[0:3, ['A', 'B']]`                                        |
| `df[1:3, 1:2]`                  | `df.iloc[0:3, 0:2]`                                              |
| `df[1,1]`                       | `df.iat[0,0]`                                                    |
| `df$C <- C`                     | `df['C'] = C`                                                    |
| **R base Math**                 | **Python/NumPy Math**                                            |
| a^b or a\*\*b                   | a\*\*b or pow(a, b)                                              |
| sqrt(a)                         | math.sqrt(a)                                                     |
| log(a)                          | math.log(a)                                                      |
| sd(iter)                        | np.std(iter)                                                     |
| sum(iter)                       | math.fsum(iter) or np.sum(iter)                                  |
| sum(iter, na.rm=TRUE)           | np.nansum(iter)                                                  |
| mean(iter)                      | np.mean(iter)                                                    |
| median(iter)                    | np.median(iter)                                                  |
| a xor b                         | a ^ b                                                            |
| cbind(A, B)                     | np.hstack((A, B))                                                |
| rbind(A, B)                     | np.vstack(A, B)                                                  |
| **Common Ops in R base**        | **Common Ops in Python**                                         |
| `is.na(iter)`                   | `np.isnan(iter)`                                                 |
| `iter[is.na(iter)] <- 0`        | [`np.nan_to_num(iter)`][np missing]                              |
| `TRUE & FALSE`                  | `True and False`                                                 |
| `seq()`                         | `np.linspace()`                                                  |
| [`apply(df, 2, func)`][r apply] | [`df.apply(func, 0)`][pd apply]                                  |
| [`table(df$X)`][r table]        | [`df['X'].value_counts()`][pd value_counts]                      |
| `table(df$X, df$Y)`             | [`pd.crosstab(df['X'], df['Y'])`][pd crosstab]                   |
| `df[is.na(df)] <- a`            | [`df.fillna(a, inplace=True)`][pd fillna]                        |
| `df[order(df$A),]`              | [`df.sort_values(by='A', inplace=True)`][pd sort_values]         |
| `unique(iter)`                  | [`pd.unique(iter)`][pd unique] or [`np.unique(iter)`][np unique] |
| `factor(iter)`                  | `pd.factorize(iter)`                                             |
| `model.matrix(~factor(iter)-1)` | [`pd.get_dummies(iter)`][pd get_dummies]                         |
| **RNG in R base**               | **RNG in Numpy**                                                 |
| set.seed(a)                     | rng = np.random.default_rng(a)                                   |
| rnorm()                         | rng.normal()                                                     |

Footnote:

1. import statements are ommited. Referenced libraries include [os](https://docs.python.org/3/library/os.html), [pandas](https://pandas.pydata.org/docs/), [NumPy](https://numpy.org/doc/).
2. `path` is a file path, `df` is a data frame, `a` and `b` are scalars, `iter` is a vector, `func` is a function.
3. Code blocks are used as an aesthetic style to seperate different sections of the table.

[r apply]: https://stat.ethz.ch/R-manual/R-devel/library/base/html/apply.html
[r table]: https://stat.ethz.ch/R-manual/R-devel/library/base/html/table.html
[pd apply]: https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.apply.html#pandas.DataFrame.apply
[pd value_counts]: https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.value_counts.html#pandas.DataFrame.value_counts
[pd fillna]: https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.fillna.html#pandas.DataFrame.fillna
[pd sort_values]: https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.sort_values.html
[pd get_dummies]: https://pandas.pydata.org/docs/reference/api/pandas.get_dummies.html
[pd unique]: https://pandas.pydata.org/docs/reference/api/pandas.unique.html
[pd crosstab]: https://pandas.pydata.org/docs/reference/api/pandas.crosstab.html
[np unique]: https://numpy.org/doc/stable/reference/generated/numpy.unique.html
[np missing]: https://numpy.org/doc/stable/reference/generated/numpy.nan_to_num.html
