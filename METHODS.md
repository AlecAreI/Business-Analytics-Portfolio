# Statistical Methods Reference

This file provides a concise reference to the analytical methods demonstrated in the portfolio.

## Normal Distribution

Used for probability questions involving a continuous normally distributed variable.

Typical Excel functions:

```text
=NORM.DIST(x, mean, standard_deviation, TRUE)
=1-NORM.DIST(x, mean, standard_deviation, TRUE)
=NORM.INV(probability, mean, standard_deviation)
```

## Sampling Distribution of the Mean

Standard error:

\[
SE=\frac{\sigma}{\sqrt{n}}
\]

Use the population mean as the center of the sampling distribution and the standard error as its spread.

## Binomial Distribution

Appropriate when:

- the number of trials is fixed,
- each trial has two outcomes,
- the probability is constant,
- trials are independent.

Typical Excel functions:

```text
=BINOM.DIST(k,n,p,FALSE)
=BINOM.DIST(k,n,p,TRUE)
=1-BINOM.DIST(k-1,n,p,TRUE)
```

## Confidence Interval: Mean

Use a **t interval** when the population standard deviation is unknown and the sample standard deviation is used.

Use a **z interval** when the population standard deviation is known.

## Confidence Interval: Proportion

Use the sample proportion:

\[
\hat p=\frac{x}{n}
\]

and its standard error to construct the interval.

## Sample Size

Sample-size planning determines how much data is required to achieve a specified confidence level and margin of error.

**Rule:** always round the final sample-size requirement upward.
