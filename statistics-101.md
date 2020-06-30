# Statistics 101
Definition: a set of techniques to organize, describe, analyze, and interpret data systematically, with the ultimate goal of extracting conclusions from said data.

Alternatively:
> “If you torture the data long enough, it will confess.” - Ronald Coase

Statistics can be divided into four areas:

 1. Descriptive Statistics
 2. Probability
 3. Sampling
 4. Inferential Statistics

Let's take a closer look at each one:

### Descriptive Statistics
Focuses on organizing and describing data. Can be further subdivided into two:
 - Measures of central tendency, such as mean, median, mode, and quantiles --- i.e. **how concentrated data is**.
 - Measures of dispersion, such as standard deviation, variance, and covariance --- i.e. **how scattered data is, *in* relation to a measure of central tendency**.

### Probability
Allows us to describe phenomena that present uncertainty or randomness in a numerical form.

### Sampling
Procedures for selecting a sample from a given population, looking to obtain information from certain characteristics of interest that might lead to conclusions about the parameters of said population.

### Inferential Statistics
Comprises methods that enable extrapolating conclusions obtained from a sample to the whole of the population or data set.

All together:

```mermaid
graph TD
A((Population/Data Set)) --> B{Sample}
B --> C(Conclusions about Population/Data Set Characteristics & Parameters)
C --> A
```

## Variable Types

```mermaid
graph LR
A((Variable)) --> B(Numerical/Quantitative)
A --> C(Categorical/Qualitative)
B --> D[Discrete]
B --> E[Continuous]
C --> F[Nominal]
C --> G[Ordinal]
```

To distinguish between discrete and continuous, ask *"is this countable (only whole numbers/integers) or measurable (any value within a range, including fractions and decimals)?"* --- e.g. number of students in a class or results of rolling a dice (discrete) vs. a person's height or time taken to finish a race (continuous).

To distinguish between nominal and ordinal, ask *"does this have an specific order or intrinsic hierarchy to it?"* --- e.g. race or gender (nominal) vs. educational stage or rating scale (ordinal).

## Measures of Central Tendency

As stated above, measures of central tendency, also known as position measures, tell us how **concentrated** data is.

### Mean
There are various types of means, all based on the concept of an average --- i.e. a single number taken as representative of a list of numbers. The most known is the **arithmetic mean**, which is simply the sum of all elements in a set divided by the number of elements of said set. For a sample ![Sample](https://raw.githubusercontent.com/Frentan/statistics101.github.io/master/images/sample.png) :

![Arithmetic Mean](https://raw.githubusercontent.com/Frentan/statistics101.github.io/master/images/arithmetic_mean.png)

It is colloquially just called *the* average, but it's better to specify depending in context. For a variable with independent realizations (where the occurrence of each does not affect the probability of occurrence of the others), it is the theoretical expected value.

A second type is the **geometric mean**. Instead of the sum of elements, it uses the product of their values, being the *n*th root of this:

![Geometric Mean](https://raw.githubusercontent.com/Frentan/statistics101.github.io/master/images/geometric_mean.png)

This measure is better when we are looking at sets interpreted according to their product, such as rates of growth or widely different magnitudes.

Thirdly, we have the **harmonic mean**. It's defined by the number of elements divided by the sum of their reciprocals (multiplicative inverses). I know it sounds bewildering, but in this case the formula makes it clearer:

![Harmonic Mean](https://raw.githubusercontent.com/Frentan/statistics101.github.io/master/images/harmonic_mean.png)

This is used for sets defined in relation to some unit --- e.g. speed (distance per unit of time) or certain price indices in economics (prices across time periods).

These three are known as the Pythagorean means. All together:

![Pythagorean Means](https://raw.githubusercontent.com/Frentan/statistics101.github.io/master/images/pythagorean_means.png)

They also follow these inequalities:

![Mean Inequalities](https://raw.githubusercontent.com/Frentan/statistics101.github.io/master/images/mean_inequalities.png)

Notice they are in alphabetical order. The equality case only applies if all set elements have the exact same value. Let's put it all together with a simple example. Given the numbers 4, 36, 45, 50, and 75:

![Example AM](https://raw.githubusercontent.com/Frentan/statistics101.github.io/master/images/example_am.png)

![Example GM](https://raw.githubusercontent.com/Frentan/statistics101.github.io/master/images/example_gm.png)

![Example HM](https://raw.githubusercontent.com/Frentan/statistics101.github.io/master/images/example_hm.png)

We can see that the results satisfy the inequalities shown above.

### Median
A median is the number that divides the set into two parts of equal frequency --- i.e. the value at the 50th percentile. It can be simply thought as the "middle" value. Its difference from (and advantage over) the mean is that it is not skewed by very large or small values. Take the numbers 1, 2, 2, 3, 4, 7, and 9 for example. Their arithmetic mean is 4 (given that (1 + 2 + 2 + 3 + 4 + 7 + 9) / 7 = **4**), but the median is 3 (1, 2, 2, **3**, 4, 7, 9). If we have a set with an odd number of elements, the median will be the arithmetic mean of the two middle values --- e.g. for 1, 2, 3, **4, 5**, 6, 8, 9: (4 + 5) / 2 = **4.5**.

Another way of looking at it is as a more "typical" value. This is why it's used as the main indicator for evaluating income distribution (median household income).

### Mode
Very straightforward, the mode is the value that occurs most frequently in a given set of elements. Consequently, it has the highest probability of occurrence in a set without values grouped into classes. Given the numbers 4, 5, 4, 6, 5, 8, and 4, the mode is **4**, since it appears three times, more than any other. Note that the mode is not always unique: if two values are tied for the highest frequency, the set is said to be **bimodal**, and if more than two values are tied, **multimodal**.

## Quantiles

Quantiles are simply the result of dividing your data into equal and adjacent subgroups. They can also be called fractiles. The median, as seen above, is the quantile that divides the sample into halves. Besides the median, the most used are qua**r**tiles and percentiles. Quartiles divide the data into four parts, or quarters. So, the first quartile (Q1) is the middle number between the smallest data point and the median. (It can also be called the lower quartile.) The second quartile (Q2) is equal to the median, and the third or upper quartile (Q3) is exactly between the median and the highest data point. Percentiles (also known as centiles), on the other hand, divide the data into a hundred parts, so they are equivalent to percentages. So, for example, the 30th percentile marks the value below which 30% of the sample remains. It's easy then to derive that the 25th percentile is equal to Q1, the 50th to Q2 (and the median), and the 75th to Q3.

## Skewness

Skewness is the measure of asymmetry of your data. With a perfectly symmetrical, or normal, distribution (the famous bell curve), our position measures will be equal and skewness with be equal to zero. However, many data sets we encounter are not symmetrical, and so their position measures will vary:

![Skewness](https://raw.githubusercontent.com/Frentan/statistics101.github.io/master/images/skewness_wikipedia.png)
A negative or left-skewed distribution has a long tail on the left, and a skewness lower than zero. The median and mean also move to the left of the peak where the mode is, with the mean further away from it. The opposite is true for a positive or right-skewed distribution.

There are several ways to calculate asymmetry. Pearson's first and second coefficients of skewness are the ones most used. For the first, subtract the mode from the mean and divide the difference by the standard deviation of the sample:

![Pearson's First Coefficient of Skewness](https://raw.githubusercontent.com/Frentan/statistics101.github.io/master/images/pearson_skewness_1.png)
Don't worry, we'll cover what standard deviation is later. Pearson's first coefficient is better when the data presents a strong mode. When the data has a weak mode or is multimodal (see above), the second is preferable, as it uses the median instead:

![Pearson's Second Coefficient of Skewness](https://raw.githubusercontent.com/Frentan/statistics101.github.io/master/images/pearson_skewness_2.png)

## Kurtosis

*"Kurtosis (from Greek: κυρτός, kyrtos or kurtos, meaning "curved, arching") is a measure of the "tailedness" of the probability distribution of a real-valued random variable. Like skewness, kurtosis describes the shape of a probability distribution and there are different ways of quantifying it for a theoretical distribution and corresponding ways of estimating it from a sample from a population.
This number is related to the tails of the distribution, not its peak;[2] hence, the sometimes-seen characterization of kurtosis as "peakedness" is incorrect. For this measure, higher kurtosis corresponds to greater extremity of deviations (or outliers), and not the configuration of data near the mean.
The kurtosis of any univariate normal distribution is 3 (mesokurtic, normal distribution). It is common to compare the kurtosis of a distribution to this value. Distributions with kurtosis less than 3 are said to be platykurtic, although this does not imply the distribution is "flat-topped" as is sometimes stated. Rather, it means the distribution produces fewer and less extreme outliers than does the normal distribution. An example of a platykurtic distribution is the uniform distribution, which does not produce outliers. Distributions with kurtosis greater than 3 are said to be leptokurtic. An example of a leptokurtic distribution is the Laplace distribution, which has tails that asymptotically approach zero more slowly than a Gaussian, and therefore produces more outliers than the normal distribution. It is also common practice to use an adjusted version of Pearson's kurtosis, the excess kurtosis, which is the kurtosis minus 3, to provide the comparison to the standard normal distribution."*

Easy proxy to calculate: Percentile coefficient of kurtosis (adjusted to zero):
K = Q3 - Q1 / 2(P90 - P10) all MINUS 3

Q3 - Q1 = IQR (interquartile range), commonly seen as the box in the boxplot

OR... K = QD / P90 - P10 all MINUS 3

Where QD (quartile deviation) = Q3 - Q1 /2
QD aka semi-interquartile range (useful dor studying distrs where samples are concentrated in the middle values)

![Kurtosis](https://raw.githubusercontent.com/Frentan/statistics101.github.io/master/images/kurtosis.png)

## Measures of Dispersion

As we saw in the beginning, measures of dispersion tell us how **scattered** data is, ***in relation to*** a position measure, usually one of the means.

### Range
Simply the difference between the largest and smallest values in the sample. It just gives a very rough idea of how scattered the data is, since it's extremely distorted by outliers:

![Range](https://raw.githubusercontent.com/Frentan/statistics101.github.io/master/images/range.png)

### Variance
"measures how far a set of numbers are spread out from their average value"

![Variance](https://raw.githubusercontent.com/Frentan/statistics101.github.io/master/images/variance.png)

### Standard Deviation
"is a measure of the amount of variation or dispersion of a set of values.[1] A low standard deviation indicates that the values tend to be close to the mean (also called the expected value) of the set, while a high standard deviation indicates that the values are spread out over a wider range. " "A useful property of the standard deviation is that, unlike the variance, it is expressed in the same units as the data."

"In addition to expressing the variability of a population, the standard deviation is commonly used to measure confidence in statistical conclusions. For example, the margin of error in polling data is determined by calculating the expected standard deviation in the results if the same poll were to be conducted multiple times. This derivation of a standard deviation is often called the "standard error" of the estimate or "standard error of the mean" when referring to a mean. It is computed as the standard deviation of all the means that would be computed from that population if an infinite number of samples were drawn and a mean for each sample were computed. "

"In science, many researchers report the standard deviation of experimental data, and by convention, only effects more than two standard deviations away from a null expectation are considered statistically significant—normal random error or variation in the measurements is in this way distinguished from likely genuine effects or associations. The standard deviation is also important in finance, where the standard deviation on the rate of return on an investment is a measure of the volatility of the investment. "

"68–95–99.7 rule, also known as the empirical rule, is a shorthand used to remember the percentage of values that lie within a band around the mean in a normal distribution with a width of two, four and six standard deviations, respectively; more precisely, 68.27%, 95.45% and 99.73% of the values lie within one, two and three standard deviations of the mean, respectively."

![Standard Deviation](https://raw.githubusercontent.com/Frentan/statistics101.github.io/master/images/standard_deviation.png)

Normal distr, also known as Gaussian, "Normal distributions are important in statistics and are often used in the natural and social sciences to represent real-valued random variables whose distributions are not known. Their importance is partly due to the central limit theorem. It states that, under some conditions, the average of many samples (observations) of a random variable with finite mean and variance is itself a random variable whose distribution converges to a normal distribution as the number of samples increases. Therefore, physical quantities that are expected to be the sum of many independent processes (such as measurement errors) often have distributions that are nearly normal..." aka. bell curve, even though many other distrs. are bell-shaped as well.

![Normal Distribution](https://raw.githubusercontent.com/Frentan/statistics101.github.io/master/standard_deviation_wikipedia.png)

### Coefficient of Variation
"also known as relative standard deviation (RSD), is a standardized measure of dispersion of a probability distribution or frequency distribution. It is often expressed as a percentage,"

CV is adimensional (lacks unit of measurement). In general, a CV <25% is a good indicator that the data is relatively homogenous (similarity of data points to each other, variability, how scattered they are, etc)

![Coefficient of Variation](https://raw.githubusercontent.com/Frentan/statistics101.github.io/master/images/coefficient_of_variation.png)

### Covariance
"measure of the joint variability of two random variables", how much they walk together, so to speak.
"If the greater values of one variable mainly correspond with the greater values of the other variable, and the same holds for the lesser values, (i.e., the variables tend to show similar behavior), the covariance is positive. [>0] In the opposite case, when the greater values of one variable mainly correspond to the lesser values of the other, (i.e., the variables tend to show opposite behavior), the covariance is negative [<0]. [IF IT IS (squiggly = 0) THE SAMPLES ARE UNCORRELATED] The sign of the covariance therefore shows the tendency in the linear relationship (correlation) between the variables."

For two samples ![Sample x](https://raw.githubusercontent.com/Frentan/statistics101.github.io/master/images/sample_x.png) and ![Sample y](https://raw.githubusercontent.com/Frentan/statistics101.github.io/master/images/sample_y.png):

![Covariance](https://raw.githubusercontent.com/Frentan/statistics101.github.io/master/images/covariance.png)

## Conclusion
Statistics is a fascinating and exciting discipline that's always near us, even if unnoticed. If the laws of nature are indeed written in the language of mathematics, statistics is an essential dialect, important not only to data scientists, but for almost anyone in almost every field. I hope this small introduction was helpful and inspires your further knowledge journey.

*To improve: change equations to LaTeX, instead of linked images.*

> Written with [StackEdit](https://stackedit.io/).

