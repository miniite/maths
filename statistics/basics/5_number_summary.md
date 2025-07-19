

# Five Number Summary and Box Plots for Outlier Detection in Statistics

## Introduction

In statistical analysis, understanding the distribution and variability of a dataset is crucial for drawing meaningful insights. The **five number summary** and **box plots** are powerful tools in descriptive statistics that summarize a dataset's spread and facilitate the identification of outliers. These techniques build upon concepts like percentiles and quartiles, providing a concise yet comprehensive overview of data distribution. This article explains the five number summary, how to construct a box plot, and their application in detecting outliers, with detailed examples and practical implications for data science and analytics.

## The Five Number Summary

The **five number summary** encapsulates a dataset's distribution through five key statistics:
1. **Minimum**: The smallest value in the dataset (excluding outliers).
2. **First Quartile (Q1)**: The 25th percentile, below which 25% of the data lies.
3. **Median (Q2)**: The 50th percentile, representing the middle value of the dataset.
4. **Third Quartile (Q3)**: The 75th percentile, below which 75% of the data lies.
5. **Maximum**: The largest value in the dataset (excluding outliers).

These five values provide a snapshot of the dataset's range, central tendency, and spread, making them essential for summarizing data and preparing for outlier detection.

## Box Plots: Visualizing the Five Number Summary

A **box plot** (or box-and-whisker plot) is a graphical representation of the five number summary, designed to visualize the distribution and identify outliers. The plot consists of:
- A **box** spanning from Q1 to Q3, representing the interquartile range (IQR), which contains the middle 50% of the data.
- A line inside the box marking the **median** (Q2).
- **Whiskers** extending from the box to the minimum and maximum values (within a defined range).
- **Outliers**, plotted as individual points beyond the whiskers.

Box plots are widely used in data analysis, supported by libraries like **Seaborn** in Python, to provide an intuitive visualization of data distribution and variability.

## Outlier Detection Using the Five Number Summary

Outliers are data points that significantly deviate from the rest of the dataset, potentially skewing statistical analyses. The five number summary helps identify outliers by defining **lower** and **upper fences**, which establish boundaries for acceptable data values. Data points outside these fences are considered outliers.

### Formulas for Fences
- **Interquartile Range (IQR)**:
  $$
  \text{IQR} = Q3 - Q1
  $$
- **Lower Fence**:
  $$
  \text{Lower Fence} = Q1 - 1.5 \times \text{IQR}
  $$
- **Upper Fence**:
  $$
  \text{Upper Fence} = Q3 + 1.5 \times \text{IQR}
  $$

Any value below the lower fence or above the upper fence is classified as an outlier.

## Example: Calculating the Five Number Summary and Detecting Outliers

Consider the dataset: [1, 2, 2, 2, 3, 3, 4, 5, 5, 6, 6, 6, 7, 8, 8, 8, 9, 9, 29]. We will calculate the five number summary, identify outliers, and construct a box plot.

### Step 1: Calculate the Five Number Summary
1. **Total Number of Values ($ n $)**:
   - The dataset has 19 values ($ n = 19 $).

2. **Minimum**:
   - Excluding potential outliers, the smallest value is 1.

3. **First Quartile (Q1, 25th Percentile)**:
   - Position:
     $$
     \text{Position} = \frac{25}{100} \times (19 + 1) = 0.25 \times 20 = 5
     $$
   - The 5th value in the sorted dataset is 3.
   - Thus, $ Q1 = 3 $.

4. **Median (Q2, 50th Percentile)**:
   - Position:
     $$
     \text{Position} = \frac{50}{100} \times (19 + 1) = 0.5 \times 20 = 10
     $$
   - The 10th value is 5.
   - Thus, $ Q2 = 5 $.

5. **Third Quartile (Q3, 75th Percentile)**:
   - Position:
     $$
     \text{Position} = \frac{75}{100} \times (19 + 1) = 0.75 \times 20 = 15
     $$
   - The 15th value is 7.
   - Thus, $ Q3 = 7 $.

6. **Maximum**:
   - Excluding potential outliers, the largest value is 9.

### Step 2: Calculate the IQR and Fences
- **IQR**:
  $$
  \text{IQR} = Q3 - Q1 = 7 - 3 = 4
  $$
- **Lower Fence**:
  $$
  \text{Lower Fence} = Q1 - 1.5 \times \text{IQR} = 3 - 1.5 \times 4 = 3 - 6 = -3
  $$
- **Upper Fence**:
  $$
  \text{Upper Fence} = Q3 + 1.5 \times \text{IQR} = 7 + 1.5 \times 4 = 7 + 6 = 13
  $$

### Step 3: Identify Outliers
- **Values below the lower fence (-3)**: The smallest value is 1, which is greater than -3. No outliers on the lower side.
- **Values above the upper fence (13)**: The value 29 is greater than 13, so 29 is an outlier.

### Step 4: Final Five Number Summary
Excluding the outlier (29):
- **Minimum**: 1
- **Q1**: 3
- **Median (Q2)**: 5
- **Q3**: 7
- **Maximum**: 9

### Step 5: Constructing the Box Plot
To create a box plot:
1. Draw a number line covering the range of the data (e.g., -2 to 30 for clarity).
2. Mark the **minimum (1)** and **maximum (9)** as the ends of the whiskers.
3. Draw a box from **Q1 (3)** to **Q3 (7)**, with a line at the **median (5)**.
4. Plot the outlier (29) as a point beyond the upper fence (13).

The resulting box plot visually displays:
- The box spanning Q1 to Q3, showing the middle 50% of the data.
- The median line dividing the box.
- Whiskers extending to the minimum and maximum values within the fences.
- The outlier (29) as a distinct point, indicating its deviation from the main distribution.

## Visualizing the Box Plot
A box plot for this dataset would look like this (conceptually):
- **Minimum**: A whisker starting at 1.
- **Q1**: The bottom of the box at 3.
- **Median**: A line inside the box at 5.
- **Q3**: The top of the box at 7.
- **Maximum**: A whisker ending at 9.
- **Outlier**: A point at 29, far beyond the upper fence.

In Python, using the **Seaborn** library, you can generate this plot with the following code:

### Import

```
import seaborn as sns
import matplotlib.pyplot as plt
```

### Dataset

```
data = [1, 2, 2, 2, 3, 3, 4, 5, 5, 6, 6, 6, 7, 8, 8, 8, 9, 9, 29]
```

### Create box plot

```
sns.boxplot(data=data)
```

### Display the plot

```
plt.title("Box Plot with Outlier Detection")
plt.show()
```

This code produces a box plot that visually highlights the outlier at 29 as a point beyond the upper whisker.

## Practical Applications

### Outlier Detection
Outliers can significantly affect statistical analyses, such as means and regressions, by skewing results. The five number summary and box plot help:
- **Identify Anomalies**: In datasets like financial transactions, outliers might indicate fraud.
- **Data Cleaning**: Removing or investigating outliers ensures more accurate models in data science.

### Real-World Examples
1. **Healthcare**: In diabetes or cancer prediction models, outliers may represent rare cases (e.g., extreme glucose levels or tumor sizes). Identifying these outliers is crucial for accurate diagnosis and modeling.
2. **Finance**: Outliers in stock price data might indicate market anomalies or errors, requiring further investigation.
3. **Quality Control**: In manufacturing, outliers in product measurements (e.g., defective items) can signal process issues.

### Data Science and Machine Learning
- **Exploratory Data Analysis (EDA)**: Box plots are used to visualize data distributions and detect outliers during EDA, guiding preprocessing steps.
- **Model Performance**: Outliers can distort machine learning models, such as regression or clustering. Removing or handling outliers improves model accuracy.
- **Feature Engineering**: The five number summary can inform feature scaling or transformation by highlighting data spread.

## Assignment: Practice Problem
To reinforce understanding, consider the following dataset: [-13, -12, -5, -6, 3, 4, 5, 6, 7, 7, 8, 10, 11, 55]. Perform the following tasks:
1. Calculate the five number summary (minimum, Q1, median, Q3, maximum).
2. Compute the IQR and determine the lower and upper fences.
3. Identify any outliers.
4. Construct a conceptual box plot and describe the outliers visually.

### Solution Outline
- **Sort the dataset**: [-13, -12, -6, -5, 3, 4, 5, 6, 7, 7, 8, 10, 11, 55].
- **Number of values**: $ n = 14 $.
- **Minimum**: -13.
- **Q1 (25th Percentile)**:
  $$
  \text{Position} = \frac{25}{100} \times (14 + 1) = 3.75
  $$
  Interpolate between the 3rd (-6) and 4th (-5) values:
  $$
  Q1 = \frac{-6 + (-5)}{2} = -5.5
  $$
- **Median (Q2, 50th Percentile)**:
  $$
  \text{Position} = \frac{50}{100} \times (14 + 1) = 7.5
  $$
  Interpolate between the 7th (5) and 8th (6) values:
  $$
  Q2 = \frac{5 + 6}{2} = 5.5
  $$
- **Q3 (75th Percentile)**:
  $$
  \text{Position} = \frac{75}{100} \times (14 + 1) = 11.25
  $$
  Interpolate between the 11th (8) and 12th (10) values:
  $$
  Q3 = \frac{8 + 10}{2} = 9
  $$
- **Maximum**: 55 (before outlier check).
- **IQR**:
  $$
  \text{IQR} = Q3 - Q1 = 9 - (-5.5) = 14.5
  $$
- **Lower Fence**:
  $$
  \text{Lower Fence} = -5.5 - 1.5 \times 14.5 = -5.5 - 21.75 = -27.25
  $$
- **Upper Fence**:
  $$
  \text{Upper Fence} = 9 + 1.5 \times 14.5 = 9 + 21.75 = 30.75
  $$
- **Outliers**: Values below -27.25 or above 30.75. Here, 55 is above 30.75, so it is an outlier. No values are below -27.25.
- **Five Number Summary (excluding outlier)**:
  - Minimum: -13
  - Q1: -5.5
  - Median: 5.5
  - Q3: 9
  - Maximum: 11

The box plot would show a box from -5.5 to 9, a median line at 5.5, whiskers to -13 and 11, and a point at 55 indicating the outlier.

## Conclusion
The five number summary and box plots are indispensable tools in statistics for summarizing data distributions and detecting outliers. By calculating the minimum, Q1, median, Q3, and maximum, and using the IQR to define lower and upper fences, analysts can identify anomalies that may affect data interpretation. Box plots provide a visual representation of these statistics, making it easy to spot outliers and understand data spread. These techniques are widely applied in data science, healthcare, finance, and quality control, where managing outliers is critical for accurate analysis and modeling. By mastering these concepts, researchers and practitioners can enhance their ability to explore and preprocess data effectively.

