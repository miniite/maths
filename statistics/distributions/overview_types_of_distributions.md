# Tabular Comparison of Probability Distributions in Statistical Analysis

## Introduction

Probability distributions are fundamental tools in statistical analysis, enabling data scientists and analysts to model the behavior of random variables in datasets. Each distribution describes how probabilities are distributed over the values of a random variable, providing insights into data patterns and facilitating tasks such as exploratory data analysis (EDA), feature engineering, and predictive modeling. In this article, we focus on six key probability distributions—**Bernoulli**, **Binomial**, **Normal (Gaussian)**, **Poisson**, **Log-Normal**, and **Uniform**—and present a detailed tabular comparison of their characteristics. This comparison highlights their differences in terms of random variable type, probability functions, parameters, moments, and applications, offering a clear reference for selecting appropriate distributions in data analysis.

## Overview of Probability Distributions

### Bernoulli Distribution
The **Bernoulli distribution** models a single trial with two possible outcomes (success or failure, typically coded as 1 or 0). It is used for binary data and forms the basis for more complex distributions like the Binomial distribution.

### Binomial Distribution
The **Binomial distribution** extends the Bernoulli distribution to model the number of successes in a fixed number of independent Bernoulli trials, each with the same probability of success. It is ideal for discrete count data involving multiple trials.

### Normal (Gaussian) Distribution
The **Normal (Gaussian) distribution** is a continuous distribution characterized by a symmetric, bell-shaped curve. It is widely used due to the Central Limit Theorem, which suggests that the sum of many independent random variables approximates a normal distribution.

### Poisson Distribution
The **Poisson distribution** models the number of events occurring in a fixed interval of time or space, given a constant average rate. It is a discrete distribution commonly used for count data.

### Log-Normal Distribution
The **Log-Normal distribution** is a continuous distribution where the logarithm of the random variable follows a normal distribution. It is suitable for positively skewed data, such as financial or biological measurements.

### Uniform Distribution
The **Uniform distribution** assigns equal probability to all outcomes within a specified range, applicable to both discrete and continuous random variables. It models scenarios where outcomes are equally likely.

## Tabular Comparison of Probability Distributions

The following table provides a comprehensive comparison of the six probability distributions based on key characteristics, including their type, random variable, probability function, parameters, moments (mean and variance), shape, and practical applications.

| **Distribution** | **Type** | **Random Variable** | **Probability Function** | **Parameters** | **Mean** | **Variance** | **Shape** | **Applications** |
|------------------|----------|---------------------|--------------------------|----------------|----------|--------------|-----------|------------------|
| **Bernoulli** | Discrete | Binary (0 or 1) | PMF: $ P(X = x) = p^x (1-p)^{1-x} $, $ x \in \{0, 1\} $ | $ p $: Probability of success ($ 0 \leq p \leq 1 $) | $ p $ | $ p(1-p) $ | Two bars (binary outcomes) | Binary classification (e.g., churn prediction), A/B testing, click-through rates |
| **Binomial** | Discrete | Count of successes ($ 0, 1, \ldots, n $) | PMF: $ P(X = k) = \binom{n}{k} p^k (1-p)^{n-k} $, $ k = 0, 1, \ldots, n $ | $ n $: Number of trials, $ p $: Probability of success | $ np $ | $ np(1-p) $ | Skewed (depends on $ p $) or symmetric (if $ p = 0.5 $) | Modeling successes in trials (e.g., defective items, customer conversions) |
| **Normal (Gaussian)** | Continuous | Real numbers ($ -\infty < x < \infty $) | PDF: $ f(x) = \frac{1}{\sigma \sqrt{2\pi}} e^{-\frac{(x - \mu)^2}{2\sigma^2}} $ | $ \mu $: Mean, $ \sigma $: Standard deviation | $ \mu $ | $ \sigma^2 $ | Symmetric, bell-shaped | Modeling symmetric data (e.g., heights, test scores), regression assumptions |
| **Poisson** | Discrete | Non-negative integers ($ 0, 1, 2, \ldots $) | PMF: $ P(X = k) = \frac{\lambda^k e^{-\lambda}}{k!} $, $ k = 0, 1, \ldots $ | $ \lambda $: Average rate of occurrence | $ \lambda $ | $ \lambda $ | Right-skewed (for small $ \lambda $) | Event counts (e.g., customer arrivals, website visits, defects per unit) |
| **Log-Normal** | Continuous | Positive real numbers ($ x > 0 $) | PDF: $ f(x) = \frac{1}{x \sigma \sqrt{2\pi}} e^{-\frac{(\ln x - \mu)^2}{2\sigma^2}} $ | $ \mu $: Mean of logarithm, $ \sigma $: Standard deviation of logarithm | $ e^{\mu + \frac{\sigma^2}{2}} $ | $ (e^{\sigma^2} - 1) e^{2\mu + \sigma^2} $ | Right-skewed | Modeling skewed data (e.g., incomes, time-to-failure, stock prices) |
| **Uniform** | Discrete or Continuous | Discrete: Finite set; Continuous: Interval $[a, b]$ | Discrete PMF: $ P(X = x) = \frac{1}{n} $; Continuous PDF: $ f(x) = \frac{1}{b-a} $, $ a \leq x \leq b $ | Discrete: $ n $ (number of outcomes); Continuous: $ a $, $ b $ (interval bounds) | Discrete: $ \frac{x_1 + x_n}{2} $; Continuous: $ \frac{a + b}{2} $ | Discrete: $ \frac{n^2 - 1}{12} $; Continuous: $ \frac{(b-a)^2}{12} $ | Flat (equal probability) | Random sampling (e.g., lottery numbers, simulation inputs) |

## Detailed Insights into the Comparison

### Type and Random Variable
- **Discrete Distributions** (Bernoulli, Binomial, Poisson, Discrete Uniform): Used for countable outcomes, such as binary results, success counts, or event occurrences. These rely on PMFs to assign probabilities to specific values.
- **Continuous Distributions** (Normal, Log-Normal, Continuous Uniform): Used for uncountable outcomes within a range, such as measurements like height or income. These use PDFs, where probabilities are derived from the area under the curve.

### Probability Functions
- **PMF vs. PDF**: Discrete distributions use PMFs to assign probabilities to specific outcomes, while continuous distributions use PDFs to describe probability density, requiring integration to calculate probabilities over intervals.
- **CDF Relationship**: For all distributions, the CDF ($ F(x) = P(X \leq x) $) is derived from the PMF (sum for discrete) or PDF (integral for continuous). The PDF is the derivative of the CDF for continuous distributions, and the PMF is the difference in CDF values for discrete distributions.

### Parameters
Each distribution is defined by specific parameters that control its shape and behavior:
- **Bernoulli**: Controlled by $ p $, the probability of success.
- **Binomial**: Defined by $ n $ (trials) and $ p $, allowing flexibility in modeling multiple trials.
- **Normal**: Governed by $ \mu $ (center) and $ \sigma $ (spread), critical for symmetric data.
- **Poisson**: Determined by $ \lambda $, the average event rate.
- **Log-Normal**: Parameterized by $ \mu $ and $ \sigma $ of the log-transformed variable, suitable for skewed data.
- **Uniform**: Defined by the range ($ n $ for discrete, $ [a, b] $ for continuous), ensuring equal likelihood.

### Moments (Mean and Variance)
- **Mean**: Represents the expected value, ranging from simple forms ($ p $ for Bernoulli) to complex expressions ($ e^{\mu + \frac{\sigma^2}{2}} $ for Log-Normal).
- **Variance**: Measures variability, with unique forms like equal mean and variance ($ \lambda $) for Poisson or dependency on range ($ \frac{(b-a)^2}{12} $) for Continuous Uniform.

### Shape
- **Bernoulli**: Two-point distribution (0 and 1).
- **Binomial**: Can be symmetric ($ p = 0.5 $) or skewed (small or large $ p $).
- **Normal**: Symmetric, bell-shaped, ideal for naturally symmetric data.
- **Poisson**: Right-skewed for small $ \lambda $, becoming more symmetric as $ \lambda $ increases.
- **Log-Normal**: Right-skewed, suitable for positive, skewed data.
- **Uniform**: Flat, with equal probability across outcomes or intervals.

### Applications
Each distribution has unique applications in data science:
- **Bernoulli**: Ideal for binary features in classification tasks (e.g., spam detection).
- **Binomial**: Models success counts in fixed trials (e.g., product defects).
- **Normal**: Underpins many statistical methods due to its prevalence in natural phenomena.
- **Poisson**: Suits rare event counts (e.g., network failures).
- **Log-Normal**: Models skewed data in finance or biology.
- **Uniform**: Used in simulations and random sampling.

## Practical Applications in Data Science

### Exploratory Data Analysis (EDA)
Identifying the distribution of features in a dataset is a critical step in EDA. For example, in a house price prediction dataset:
- **Size of the house** (continuous) may follow a Log-Normal distribution due to positive skew.
- **Number of rooms** (discrete) may follow a Poisson distribution for count data.
- **Seaside proximity** (binary: Yes/No) follows a Bernoulli distribution.
- **Price** (continuous) may approximate a Normal or Log-Normal distribution.

Understanding these distributions helps analysts detect outliers, assess feature relevance, and prepare data for modeling.

### Feature Engineering
- **Transformation**: Skewed features (e.g., income) may be log-transformed to approximate a Normal distribution for better model performance.
- **Feature Selection**: Features with distributions closely related to the target variable (e.g., house size for price) are prioritized, while irrelevant features (e.g., uniform noise) may be discarded.

### Statistical Modeling
- **Model Assumptions**: Many machine learning algorithms, such as linear regression, assume normality for residuals. Recognizing Normal distributions in features supports these assumptions.
- **Custom Models**: Poisson regression for count data or logistic regression for Bernoulli outcomes leverages specific distributions.

## Python Implementation
To visualize the distributions for comparison:

### Import
```python
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from scipy.stats import bernoulli, binom, norm, poisson, lognorm, uniform
```

### Set up plotting
```python
plt.figure(figsize=(15, 10))
```

#### 1. Bernoulli Distribution
```python
p = 0.5
x_bernoulli = [0, 1]
pmf_bernoulli = bernoulli.pmf(x_bernoulli, p)
plt.subplot(2, 3, 1)
plt.bar(x_bernoulli, pmf_bernoulli)
plt.title("Bernoulli PMF (p=0.5)")
plt.xlabel("Outcome")
plt.ylabel("Probability")
```
#### 2. Binomial Distribution
```python
n, p = 10, 0.2
x_binom = np.arange(0, n+1)
pmf_binom = binom.pmf(x_binom, n, p)
plt.subplot(2, 3, 2)
plt.bar(x_binom, pmf_binom)
plt.title("Binomial PMF (n=10, p=0.2)")
plt.xlabel("Number of Successes")
plt.ylabel("Probability")
```
#### 3. Normal Distribution
```python
mu, sigma = 170, 10
x_norm = np.linspace(140, 200, 100)
pdf_norm = norm.pdf(x_norm, mu, sigma)
plt.subplot(2, 3, 3)
plt.plot(x_norm, pdf_norm)
plt.title("Normal PDF (μ=170, σ=10)")
plt.xlabel("Height (cm)")
plt.ylabel("Probability Density")
```
#### 4. Poisson Distribution
```python
lambda_ = 5
x_poisson = np.arange(0, 15)
pmf_poisson = poisson.pmf(x_poisson, lambda_)
plt.subplot(2, 3, 4)
plt.bar(x_poisson, pmf_poisson)
plt.title("Poisson PMF (λ=5)")
plt.xlabel("Number of Events")
plt.ylabel("Probability")
```
#### 5. Log-Normal Distribution
```python
mu, sigma = 10, 0.5
x_lognorm = np.linspace(0, 50000, 100)
pdf_lognorm = lognorm.pdf(x_lognorm, s=sigma, scale=np.exp(mu))
plt.subplot(2, 3, 5)
plt.plot(x_lognorm, pdf_lognorm)
plt.title("Log-Normal PDF (μ=10, σ=0.5)")
plt.xlabel("Income")
plt.ylabel("Probability Density")
```
#### 6. Uniform Distribution
```python
a, b = 0, 10
x_uniform = np.linspace(a, b, 100)
pdf_uniform = uniform.pdf(x_uniform, loc=a, scale=b-a)
plt.subplot(2, 3, 6)
plt.plot(x_uniform, pdf_uniform)
plt.title("Uniform PDF (a=0, b=10)")
plt.xlabel("Value")
plt.ylabel("Probability Density")
```
---
```python
plt.tight_layout()
plt.show()
```

This Python code generates plots for the PMF or PDF of each distribution, visually demonstrating their shapes and facilitating comparison.

## Conclusion
The Bernoulli, Binomial, Normal, Poisson, Log-Normal, and Uniform distributions each serve unique purposes in modeling random variables in statistical analysis. By understanding their characteristics—type, probability functions, parameters, moments, shapes, and applications—data scientists can select the appropriate distribution for each feature in a dataset. The tabular comparison provided here offers a concise reference for distinguishing these distributions, aiding in EDA, feature engineering, and model selection. These distributions form the backbone of statistical modeling, enabling robust analysis and informed decision-making in fields such as finance, healthcare, and marketing.

