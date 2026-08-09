# Business Analytics: Applied Statistical Analysis

## Alec J. Thomas

Business analytics is useful when statistical output can be converted into a clear decision. The examples below demonstrate the use of probability, sampling, confidence intervals, and sample-size planning to answer practical quantitative questions.

Rather than presenting a list of formulas, each example follows the same analytical structure:

> **Question → Method → Calculation → Result → Interpretation**

---

## Portfolio Navigation

1. [Normal Distribution: Soft-Drink Example](#1-normal-distribution-soft-drink-example)
2. [Normal Distribution: Ball-Bearing Tolerance](#2-normal-distribution-ball-bearing-tolerance)
3. [Binomial Probability: LED Defects](#3-binomial-probability-led-defects)
4. [Sampling Distribution: Sample Mean](#4-sampling-distribution-sample-mean)
5. [Normal Distribution: Range and Percentiles](#5-normal-distribution-range-and-percentiles)
6. [Confidence Interval for a Mean — t Method](#6-confidence-interval-for-a-mean--t-method)
7. [Confidence Interval for a Mean — z Method](#7-confidence-interval-for-a-mean--z-method)
8. [Confidence Interval for a Proportion](#8-confidence-interval-for-a-proportion)
9. [Sample Size for Estimating a Mean](#9-sample-size-for-estimating-a-mean)
10. [Sample Size for Estimating a Proportion](#10-sample-size-for-estimating-a-proportion)
11. [Method-Selection Framework](#11-method-selection-framework)
12. [Analytical Takeaways](#12-analytical-takeaways)

---

## 1. Normal Distribution: Soft-Drink Example

### Question

A normally distributed variable has:

- Mean: **19.45**
- Standard deviation: **4**

What is the probability that an observation exceeds **13**?

### Method

For a continuous normally distributed variable, standardize or use the cumulative normal distribution and calculate the upper-tail probability.

**Calculation:** `P(X > 13) = 1 - P(X ≤ 13)`

### Result

**P(X > 13) = 0.946573**

**Answer: 94.66%**

### Interpretation

An observation above 13 is highly likely under this distribution. From a business perspective, this type of analysis can be used to estimate the percentage of products, customers, transactions, or process outcomes expected to exceed a specified threshold.

---

## 2. Normal Distribution: Ball-Bearing Tolerance

### Question

Ball-bearing measurements are modeled with:

- Mean: **0.764**
- Standard deviation: **0.004**

What proportion is expected to exceed **0.770**?

### Method

This is another upper-tail normal-distribution problem:

**Calculation:** `P(X > 0.770) = 1 - P(X ≤ 0.770)`

### Result

**P(X > 0.770) = 0.066807**

**Answer: 6.68%**

### Interpretation

Approximately 6.7% of observations are expected above the specified threshold. In a quality-control setting, this type of result can be used to estimate how much output may fall beyond a tolerance boundary and whether process adjustment is warranted.

---

## 3. Binomial Probability: LED Defects

### Question

For a process with:

- Number of trials: **10**
- Probability of the event: **0.09**

What is the probability of observing **exactly one** event?

### Method

Because there is a fixed number of trials and each trial has a constant probability, the appropriate model is the binomial distribution.

**Binomial probability formula:** `P(X = k) = C(n,k) × p^k × (1-p)^(n-k)`

with:

- \(n=10\)
- \(p=0.09\)
- \(k=1\)

### Result

**P(X = 1) = 0.385137**

**Answer: 38.51%**

Additional calculated results from the same model include:

| Probability | Result |
|---|---:|
| \(P(X=1)\) | 0.3851 |
| \(P(X\le1)\) | 0.7746 |
| \(P(X\ge1)\) | 0.6106 |
| \(P(X=0)\) | 0.3894 |
| \(P(X\le3)\) | 0.9912 |
| \(P(X\ge4)\) | 0.0088 |

### Interpretation

The exact-one-event outcome is fairly common, while four or more events are very unlikely. In operations or quality analytics, that distinction helps separate routine variation from outcomes that may warrant investigation.

---

## 4. Sampling Distribution: Sample Mean

### Question

A population has:

- Mean: **50**
- Standard deviation: **8**
- Sample size: **100**

What is the probability that a sample mean is below **49**?

### Method

For the sampling distribution of the mean:

**Standard error:** `SE = σ / √n`

**Calculation:** `SE = 8 / √100 = 0.8`

The probability is then evaluated using the sampling distribution centered at 50 with a standard error of 0.8.

### Result

**P(X̄ < 49) = 0.105650**

**Answer: 10.56%**

Additional results:

| Sampling-distribution calculation | Result |
|---|---:|
| Standard error | 0.8000 |
| \(P(\bar X<49)\) | 0.1056 |
| \(P(\bar X>49)\) | 0.8944 |
| \(P(49<\bar X<49.5)\) | 0.1603 |
| 70th-percentile sample mean | 50.4195 |
| Value with 70% above it | 49.5805 |

### Interpretation

A sample mean behaves differently from an individual observation because averaging reduces variability. This is central to business analytics because many decisions are made from samples rather than entire populations.

---

## 5. Normal Distribution: Range and Percentiles

Using an individual normal distribution with:

- Mean: **50**
- Standard deviation: **8**

the calculator produced the following:

| Analysis | Result |
|---|---:|
| \(P(X<49)\) | 0.4503 |
| \(P(X>49)\) | 0.5497 |
| \(P(49<X<49.5)\) | 0.0248 |
| Value with 70% below it | 54.1952 |
| Value with 70% above it | 45.8048 |

### Analytical significance

These calculations demonstrate both directions of probability analysis:

- **Forward probability:** given a value, determine its probability.
- **Inverse probability:** given a probability, determine the corresponding value.

That distinction is useful in forecasting, threshold design, service-level planning, inventory decisions, and performance benchmarking.

---

## 6. Confidence Interval for a Mean — t Method

### Question

Estimate a population mean when:

- Sample mean: **1200**
- Sample standard deviation: **150**
- Sample size: **100**
- Confidence level: **90%**
- Population standard deviation is **unknown**

### Method

Because the population standard deviation is unknown and the sample standard deviation is used, the appropriate method is a **t confidence interval**.

Key calculations:

- Degrees of freedom: **99**
- Critical \(t^*\): **1.660391**
- Standard error: **15**
- Margin of error: **24.9059**

### Result

**Point estimate ± margin of error:** `1200 ± 24.9059`

**90% confidence interval:**

**90% confidence interval: 1175.09 to 1224.91**

### Interpretation

The interval provides a range of plausible values for the population mean, incorporating sampling uncertainty. A manager can use this type of analysis to avoid treating a sample estimate as if it were an exact population value.

---

## 7. Confidence Interval for a Mean — z Method

Using the same sample mean and sample size, but treating the population standard deviation as known:

- Sample mean: **1200**
- Population standard deviation: **150**
- Sample size: **100**
- Confidence level: **90%**

### Method

A **z confidence interval** is appropriate when the population standard deviation is known.

Calculated values:

- Critical \(z^*\): **1.644854**
- Standard error: **15**
- Margin of error: **24.6728**

### Result

**90% confidence interval:**

**90% confidence interval: 1175.33 to 1224.67**

### Comparison

The t interval is slightly wider than the z interval because the t method accounts for additional uncertainty when the population standard deviation is unknown.

This demonstrates an important analytical principle: **method selection changes the level of uncertainty reflected in the result.**

---

## 8. Confidence Interval for a Proportion

### Question

A sample contains:

- Observations with the characteristic: **1197**
- Total sample size: **3794**
- Confidence level: **95%**

Estimate the population proportion.

### Method

First calculate the sample proportion:

**Sample proportion:** `p̂ = 1197 / 3794 = 0.315498`

Then use a z-based confidence interval for a proportion.

Calculated values:

- Critical \(z^*\): **1.959964**
- Standard error: **0.007545**
- Margin of error: **0.014787**

### Result

**95% confidence interval: 0.300711 to 0.330285**

**95% confidence interval: 30.07% to 33.03%**

### Interpretation

The estimate is not simply “31.55%.” The interval communicates the uncertainty surrounding that estimate and provides a more decision-useful range for the underlying population proportion.

---

## 9. Sample Size for Estimating a Mean

### Question

How large should a sample be to estimate a population mean when:

- Estimated population standard deviation: **48**
- Desired margin of error: **5**
- Confidence level: **90%**

### Method

The sample-size calculation uses the critical z value, estimated standard deviation, and desired margin of error.

Calculated raw sample size:

**Calculated sample size:** `n = 249.3429`

### Result

Sample sizes must be rounded **up**, not to the nearest whole number.

**Required sample size: 250**

### Interpretation

Sample-size planning connects statistical precision to resource requirements. A tighter margin of error or higher confidence level generally requires a larger sample and therefore more time, cost, or data collection effort.

---

## 10. Sample Size for Estimating a Proportion

### Question

Determine the sample size required when:

- Estimated proportion: **0.50**
- Desired margin of error: **0.05**
- Confidence level: **95%**

### Method

When no better estimate is available, \(p=0.50\) is commonly used because it produces the most conservative variance and therefore a sufficiently large sample.

Raw result:

**Calculated sample size:** `n = 384.1459`

### Result

**Required sample size: 385**

### Interpretation

This is an example of using analytics before data collection begins. The analysis determines how much data is required to achieve a desired level of precision.

---

## 11. Method-Selection Framework

A large part of statistical analysis is choosing the correct method before performing any calculation.

| Business question | Appropriate method |
|---|---|
| Probability for one continuous observation | Normal distribution |
| Probability involving a sample mean | Sampling distribution |
| Exact number of events in fixed trials | Binomial distribution |
| Estimate mean, population σ unknown | t confidence interval |
| Estimate mean, population σ known | z confidence interval |
| Estimate percentage/proportion | z interval for a proportion |
| Determine data needed for a target precision | Sample-size calculation |

### Practical workflow

1. Identify the type of variable or outcome.
2. Determine whether the question concerns an individual observation, count, sample mean, or population estimate.
3. Identify what population information is known.
4. Select the statistical model.
5. Calculate using full precision.
6. Round only the final reported answer.
7. Interpret the result in the context of the decision.

---

## 12. Analytical Takeaways

The work in this portfolio demonstrates several core business-analytics capabilities:

**Quantifying uncertainty.** Probability and confidence intervals provide more information than a single point estimate.

**Separating individual and sample behavior.** Sampling distributions demonstrate why sample means have less variability than individual observations.

**Selecting methods based on assumptions.** Choosing between normal, binomial, t, z, and proportion methods is part of the analysis—not an afterthought.

**Planning data collection.** Sample-size calculations show how confidence and precision translate into data requirements.

**Interpreting results for decisions.** The value of a calculation comes from explaining what the result means and what it does—and does not—support.

---

## Supporting Workbook

The repository includes the Excel workbook used to organize and verify these calculations:

[`supporting_material/statistics_probability_calculator_updated.xlsx`](supporting_material/statistics_probability_calculator_updated.xlsx)

The workbook includes sections for:

- Individual normal-distribution calculations
- Sampling distributions
- Binomial distributions
- Confidence intervals for means
- Confidence intervals for proportions
- Required sample sizes
- Worked examples

---

## Additional Coursework

Additional coursework has included hypothesis testing, comparative statistical analysis, and ANOVA. Those topics are not presented here as reconstructed case studies unless the original numerical inputs and outputs are available for verification. This portfolio prioritizes defensible analysis over padding the repository with unsupported examples.
