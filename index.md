## Expectation Maximization algorithm

You can use the [editor on GitHub](https://github.com/a25/ml-explained.github.io/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

In clustering problem, we can have hard clustering or soft clustering. Hard clustering assigns each point to distinct cluster. Soft clustering can have same point assigned to more than one cluster.
Gaussian mixture model is one of the soft clustering algorithms. It identifies dataset points distribution in terms of different gaussian models.
Now, question comes, given data points, how one can find from which distribution those data points came?
I will explain this using 1-D gaussians.
We know that 1-D gaussian model has 2 parameters (µ - mean) and (σ^2 - variance). If these points are known then we can find data points distribution.
But how one can find µ and σ^2   , if there is no information of which points belongs to particular gaussian model?
Suppose we have dataset which can be represented by two gaussian models and objective is to find models parameter.
Given,

X = set of data points having (x1,x2……..xi)
µ1, 〖σ1〗^2= parameter for gaussian model (A)
µ2, 〖σ2〗^2= parameter for gaussian model(B)
We can calculate,
P(xi | A )= probability of data point from given gaussian distribution (A) =(1*ⅇ^((-(xi-u1)^2)/(2〖σ1〗^2 )))/√(2π〖σ1〗^2 )
P(xi | B)= probability of data point from given gaussian distribution (B) =(1*ⅇ^((-(xi-u2)^2)/(2〖σ2〗^2 )))/√(2π〖σ2〗^2 )

Now, Using Native Bayes algorithm we can calculate:
P(A | xi) = (P(xi | A)* P(A))/(P(xi│A)*P(A)  + P(xi│B)*P(B)) = (P(xi | A)* P(A))/(P(xi))
P(B | xi) = (P(xi | B)* P(B))/(P(xi│A)*P(A)  + P(xi│B)*P(B))=(P(xi | B)* P(B))/(P(xi))
Where,
P(A), P(B) = prior probability of distributions
P(xi) = probability of data point

P(A | xi), P(B | xi) = posterior probability of distributions given datapoints

Now let’s see in detail steps used in EM algorithm:
Step1 – Algorithm assigns initial random µ and σ to given number of gaussians. Based on this it finds probability of particular data point given some distribution P(xi | A) .

![figure1](https://github.com/a25/ml-explained.github.io/blob/gh-pages/images/figure_1.JPG?raw=true)


```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/a25/ml-explained.github.io/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
