## Expectation Maximization algorithm

In clustering problem, we can have hard clustering or soft clustering. Hard clustering assigns each point to distinct cluster. Soft clustering can have same point assigned to more than one cluster.
Gaussian mixture model is one of the soft clustering algorithms. It identifies dataset points distribution in terms of different gaussian models.

Now, question comes, given data points, how one can find from which distribution those data points came?
I will explain this using 1-D gaussians.

We know that 1-D gaussian model has 2 parameters (µ - mean) and (σ^2 - variance). If these points are known then we can find data points distribution.
But how one can find µ and σ^2   , if there is no information of which points belongs to particular gaussian model?
Suppose we have dataset which can be represented by two gaussian models and objective is to find models parameter.
Given,

X = set of data points having (x1,x2……..xi)

µ1, σ1<sup>2</sup>= parameter for gaussian model (A)

µ2, σ2<sup>2</sup>= parameter for gaussian model(B)

We can calculate,
![figure1_2_2](https://github.com/a25/ml-explained.github.io/blob/gh-pages/images/figure_1_2_2.JPG?raw=true)

Now, Using Native Bayes algorithm we can calculate:

![figure1_2_3_4](https://github.com/a25/ml-explained.github.io/blob/gh-pages/images/figure_1_2_3_4.JPG?raw=true)

Where,
P(A), P(B) = prior probability of distributions
P(xi) = probability of data point

P(A|xi), P(B|xi) = posterior probability of distributions given datapoints

Now let’s see in detail steps used in EM algorithm:

Step1 – Algorithm assigns initial random µ and σ to given number of gaussians. 
Based on this it finds probability of particular data point given some distribution P(xi | A) .

![figure1](https://github.com/a25/ml-explained.github.io/blob/gh-pages/images/figure_1.JPG?raw=true)

Figure 1: Initial random distribution assignment

* Data point shades shown in image reflects probability of assignment to particular distribution.

Step2 - Based on bayes theorem it finds probability of distribution given data point P(A | xi).
At initial stage while using bayes theorem, prior probability P(A) can be assumed some constant value.

Step3- Once posterior probability P(A | xi) is found, P(A) can be recalculated using law of total probability.

P(A) = P(A | x1)+P(A | x2)+⋯+P(A|xi)

P(B) = 1-P(A)

Step4- Now, mean (µ1)  and variance (σ1<sup>2</sup>) can also be recalculated as below and Gaussian distributions can be moved as shown in figure 2:

![figure1_1](https://github.com/a25/ml-explained.github.io/blob/gh-pages/images/figure_1_1.JPG?raw=true)


![figure2](https://github.com/a25/ml-explained.github.io/blob/gh-pages/images/figure_2.JPG?raw=true)

Figure 2: points assignment recalculated and distribution adjusted

This step1 to step4 steps repeats in cycle until proper distribution is found.
You may be wondering why mean is not average of points, why there is probability term multiplied in numerator and added in denominator? It’s because some points may be partially assigned to particular cluster as shown in Figure-3.

![figure3](https://github.com/a25/ml-explained.github.io/blob/gh-pages/images/figure_3.JPG?raw=true)

Figure-3: single datapoint partially assigned in different clusters.

### References

(1) https://www.youtube.com/watch?v=iQoXFmbXRJA

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
