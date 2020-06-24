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
 - Position or central tendency measurements, such as mean, median, mode, and quantiles --- i.e. **how concentrated data is**.
 - Dispersion measurements, such as standard deviation, variance, and covariance --- i.e. **how scattered data is, *in* relation to a position measurement**.

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
There are various types of means, all based on the concept of an average --- i.e. a single number taken as representative of a list of numbers. The most known is the **arithmetic mean**, which is simply the sum of all elements in a set divided by the number of elements of said set. For a sample ![Sample](http://www.sciweavers.org/tex2img.php?eq=x_%7B1%7D%2Cx_%7B2%7D%2C%5Cldots%20%2Cx_%7Bn%7D&bc=Transparent&fc=Black&im=png&fs=12&ff=modern&edit=0) :

![Arithmetic Mean](http://www.sciweavers.org/tex2img.php?eq=%7B%5Cdisplaystyle%20%7B%5Cbar%20%7Bx%7D%7D%3D%7B%5Cfrac%20%7B1%7D%7Bn%7D%7D%5Cleft%28%5Csum%20_%7Bi%3D1%7D%5E%7Bn%7D%7Bx_%7Bi%7D%7D%5Cright%29%3D%7B%5Cfrac%20%7Bx_%7B1%7D%2Bx_%7B2%7D%2B%5Ccdots%20%2Bx_%7Bn%7D%7D%7Bn%7D%7D%7D&bc=Transparent&fc=Black&im=png&fs=18&ff=modern&edit=0)

It is colloquially just called *the* average, but it's better to specify depending in context. For a variable with independent realizations (where the occurrence of each does not affect the probability of occurrence of the others), it is the theoretical expected value.

A second type is the **geometric mean**. Instead of the sum of elements, it uses the product of their values, being the *n*th root of this:

![Geometric Mean](http://www.sciweavers.org/tex2img.php?eq=%7B%5Cdisplaystyle%20%7B%5Cbar%20%7Bx%7D%7D%3D%5Cleft%28%5Cprod%20_%7Bi%3D1%7D%5E%7Bn%7Dx_%7Bi%7D%5Cright%29%5E%7B%5Cfrac%20%7B1%7D%7Bn%7D%7D%3D%7B%5Csqrt%5B%7Bn%7D%5D%7Bx_%7B1%7Dx_%7B2%7D%5Ccdots%20x_%7Bn%7D%7D%7D%7D&bc=Transparent&fc=Black&im=png&fs=18&ff=modern&edit=0)

This measure is better when we are looking at sets interpreted according to their product, such as rates of growth or widely different magnitudes.

Thirdly, we have the **harmonic mean**. It's defined by the number of elements divided by the sum of their reciprocals (multiplicative inverses). I know it sounds bewildering, but in this case the formula makes it clearer:

![Harmonic Mean](http://www.sciweavers.org/tex2img.php?eq=%7B%5Cdisplaystyle%20%7B%5Cbar%20%7Bx%7D%7D%3Dn%5Cleft%28%5Csum%20_%7Bi%3D1%7D%5E%7Bn%7D%7B%5Cfrac%20%7B1%7D%7Bx_%7Bi%7D%7D%7D%5Cright%29%5E%7B-1%7D%7D%3D%7B%5Cfrac%20%7Bn%7D%7B%7B%5Cfrac%20%7B1%7D%7Bx_%7B1%7D%7D%7D%2B%7B%5Cfrac%20%7B1%7D%7Bx_%7B2%7D%7D%7D%2B%5Ccdots%20%2B%7B%5Cfrac%20%7B1%7D%7Bx_%7Bn%7D%7D%7D%7D%7D&bc=Transparent&fc=Black&im=png&fs=18&ff=modern&edit=0)

This is used for sets defined in relation to some unit --- e.g. speed (distance per unit of time) or certain price indices in economics (prices across time periods).

These three are known as the Pythagorean means. All together:

![Pythagorean Means](http://www.sciweavers.org/tex2img.php?eq=%7B%5Cdisplaystyle%20%7B%5Cbegin%7Baligned%7D%5Coperatorname%20%7BAM%7D%20%5Cleft%28x_%7B1%7D%2C%5C%3B%5Cldots%20%2C%5C%3Bx_%7Bn%7D%5Cright%29%26%3D%7B%5Cfrac%20%7B1%7D%7Bn%7D%7D%5Cleft%28x_%7B1%7D%2B%5C%3B%5Ccdots%20%5C%3B%2Bx_%7Bn%7D%5Cright%29%5C%5C%5B9pt%5D%5Coperatorname%20%7BGM%7D%20%5Cleft%28x_%7B1%7D%2C%5C%3B%5Cldots%20%2C%5C%3Bx_%7Bn%7D%5Cright%29%26%3D%7B%5Csqrt%5B%7Bn%7D%5D%7B%5Cleft%5Cvert%20x_%7B1%7D%5Ctimes%20%5C%2C%5Ccdots%20%5C%2C%5Ctimes%20x_%7Bn%7D%5Cright%5Cvert%20%7D%7D%5C%5C%5B9pt%5D%5Coperatorname%20%7BHM%7D%20%5Cleft%28x_%7B1%7D%2C%5C%3B%5Cldots%20%2C%5C%3Bx_%7Bn%7D%5Cright%29%26%3D%7B%5Cfrac%20%7Bn%7D%7B%5Cdisplaystyle%20%7B%5Cfrac%20%7B1%7D%7Bx_%7B1%7D%7D%7D%2B%5C%3B%5Ccdots%20%5C%3B%2B%7B%5Cfrac%20%7B1%7D%7Bx_%7Bn%7D%7D%7D%7D%7D%5Cend%7Baligned%7D%7D%7D&bc=Transparent&fc=Black&im=png&fs=18&ff=modern&edit=0)

They also follow these inequalities:

![Mean Inequalities](http://www.sciweavers.org/tex2img.php?eq=%7B%5Cdisplaystyle%20%5Cmathrm%20%7BAM%7D%20%5Cgeq%20%5Cmathrm%20%7BGM%7D%20%5Cgeq%20%5Cmathrm%20%7BHM%7D%20%5C%2C%7D&bc=Transparent&fc=Black&im=png&fs=18&ff=modern&edit=0)


Notice they are in alphabetical order. The equality case only applies if all set elements have the exact same value. Let's put it all together with a simple example. Given the numbers 4, 36, 45, 50, and 75:

![Example AM](http://www.sciweavers.org/tex2img.php?eq=%7B%5Cdisplaystyle%20%7BAM%7D=%7B%5Cfrac%20%7B4%2b36%2b45%2b50%2b75%7D%7B5%7D%7D=%7B%5Cfrac%20%7B210%7D%7B5%7D%7D=42%7D&bc=Transparent&fc=Black&im=png&fs=18&ff=modern&edit=0)
![Example GM](http://www.sciweavers.org/tex2img.php?eq=%7B%5Cdisplaystyle%20%7BGM%7D%3D%284%5Ctimes%2036%5Ctimes%2045%5Ctimes%2050%5Ctimes%2075%29%5E%7B%5Cfrac%20%7B1%7D%7B5%7D%7D%3D%7B%5Csqrt%5B%7B5%7D%5D%7B24%5C%3B300%5C%3B000%7D%7D%3D30%7D&bc=Transparent&fc=Black&im=png&fs=18&ff=modern&edit=0)
![Example HM](http://www.sciweavers.org/tex2img.php?eq=%7B%5Cdisplaystyle%20%7BHM%7D%3D%7B%5Cfrac%20%7B5%7D%7B%7B%5Ctfrac%20%7B1%7D%7B4%7D%7D%2B%7B%5Ctfrac%20%7B1%7D%7B36%7D%7D%2B%7B%5Ctfrac%20%7B1%7D%7B45%7D%7D%2B%7B%5Ctfrac%20%7B1%7D%7B50%7D%7D%2B%7B%5Ctfrac%20%7B1%7D%7B75%7D%7D%7D%7D%3D%7B%5Cfrac%20%7B5%7D%7B%5C%3B%7B%5Ctfrac%20%7B1%7D%7B3%7D%7D%5C%3B%7D%7D%3D15%7D&bc=Transparent&fc=Black&im=png&fs=18&ff=modern&edit=0)

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

![Skewness](https://upload.wikimedia.org/wikipedia/commons/thumb/c/cc/Relationship_between_mean_and_median_under_different_skewness.png/640px-Relationship_between_mean_and_median_under_different_skewness.png)
A negative or left-skewed distribution has a long tail on the left, and a skewness lower than zero. The median and mean also move to the left of the peak where the mode is, with the mean further away from it. The opposite is true for a positive or right-skewed distribution.

There are several ways to calculate asymmetry. Pearson's first and second coefficients of skewness are the ones most used. For the first, subtract the mode from the mean and divide the difference by the standard deviation of the sample:

![Pearson's First Coefficient of Skewness](http://www.sciweavers.org/tex2img.php?eq=Sk_1%20%3D%20%5Cfrac%7B%5Cbar%7Bx%7D%20-%20Mode%7D%7Bs%7D&bc=Transparent&fc=Black&im=png&fs=18&ff=modern&edit=0)
... Don't worry, we'll see what exactly standard deviation is later. (Edit sentence?)

"Pearson’s second coefficient of skewness, or Pearson median skewness, subtracts the median from the mean, multiplies the difference by three and divides the product by the standard deviation."

"Pearson’s first coefficient of skewness is useful if the data exhibit a strong mode. If the data have a weak mode or multiple modes, Pearson’s second coefficient may be preferable, as it does not rely on mode as a measure of central tendency."

![Pearson's Second Coefficient of Skewness](http://www.sciweavers.org/tex2img.php?eq=Sk_2%20=%20%5Cfrac%7B3%28%5Cbar%7Bx%7D%20-%20Median%29%7D%7Bs%7D&bc=Transparent&fc=Black&im=png&fs=18&ff=modern&edit=0)
TO BE CONTINUED...
*To improve: change equations to LaTeX, instead of linked images.*

> Written with [StackEdit](https://stackedit.io/).

