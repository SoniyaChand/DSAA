# Data Transformation Techniques

Data transformation is the process of converting data into a suitable format or scale so that it can be analyzed and used by machine learning algorithms effectively. It is a key step in data preprocessing.

---

## 1. Normalization

Normalization is a technique that rescales data values to a fixed range, usually between 0 and 1. It makes sure that all features are on a similar scale so that no single feature dominates the others.

### Types of Normalization

1. Min-Max Normalization
2. Z-Score Normalization
3. Decimal Scaling Normalization

### a) Min-Max Normalization

It rescales values linearly to a new range, usually [0, 1].

**Formula:**

```
X' = (X - Xmin) / (Xmax - Xmin)
```

Where:
- `X` = original value
- `Xmin` = minimum value in the data
- `Xmax` = maximum value in the data
- `X'` = normalized value

**Example:** Data: 10, 20, 30, 40, 50 (Xmin = 10, Xmax = 50)

| Original (X) | Normalized (X') |
|---|---|
| 10 | 0.00 |
| 20 | 0.25 |
| 30 | 0.50 |
| 40 | 0.75 |
| 50 | 1.00 |

**Advantages:**
- Simple and easy to understand.
- Output is within a fixed range.

**Disadvantages:**
- Highly sensitive to outliers.

### b) Z-Score Normalization

It rescales data using the mean and standard deviation, so the result has mean = 0 and standard deviation = 1.

**Formula:**

```
Z = (X - μ) / σ
```

Where:
- `X` = original value
- `μ` = mean of the data
- `σ` = standard deviation of the data

**Example:** Data: 10, 20, 30, 40, 50 (μ = 30, σ ≈ 14.14)

| Original (X) | Z-Score |
|---|---|
| 10 | -1.41 |
| 20 | -0.71 |
| 30 | 0.00 |
| 40 | 0.71 |
| 50 | 1.41 |

**Advantages:**
- Handles outliers better than Min-Max.
- Works well with normally distributed data.

**Disadvantages:**
- Output is not bounded to a fixed range.

### c) Decimal Scaling Normalization

It moves the decimal point of values by dividing each value by a power of 10.

**Formula:**

```
X' = X / 10^j
```

Where `j` is the smallest integer such that `max(|X'|) < 1`.

**Example:** If the maximum value is 986, then j = 3, so 986 becomes 986 / 1000 = 0.986.

---

## 2. Standardization

Standardization is a technique that rescales data so that it has a mean of 0 and a standard deviation of 1. It is also known as Z-Score Scaling. It does not limit values to a fixed range.

**Formula:**

```
Z = (X - μ) / σ
```

**Interpretation:**
- Z = 0 means the value is equal to the mean.
- Z > 0 means the value is above the mean.
- Z < 0 means the value is below the mean.

**Example:** Heights converted into how many standard deviations they are away from the average height.

**Used in:** Linear regression, logistic regression, SVM, and PCA.

---

## 3. Difference Between Normalization and Standardization

| Normalization | Standardization |
|---|---|
| It is a technique that rescales data to a fixed range, usually [0, 1]. | It is a technique that rescales data to have mean 0 and standard deviation 1. |
| It is also called Min-Max Scaling. | It is also called Z-Score Scaling. |
| It uses the minimum and maximum values of the data. | It uses the mean and standard deviation of the data. |
| It gives output within a fixed, bounded range. | It gives output that is not bounded to a fixed range. |
| It is sensitive to outliers. | It is less sensitive to outliers. |
| It is useful when the data does not follow a normal distribution. | It is useful when the data follows a normal distribution. |
| It is used in algorithms like KNN, neural networks, and image processing. | It is used in algorithms like linear regression, logistic regression, SVM, and PCA. |
| It is used when the range of values is important. | It is used when the distribution of values is important. |