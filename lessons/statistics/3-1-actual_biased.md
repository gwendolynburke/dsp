[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

### Question
Something like the class size paradox appears if you survey children and ask how many children are in their family. Families with many children are more likely to appear in your sample, and families with no children have no chance to be in the sample.

Use the NSFG respondent variable numkdhh to construct the actual distribution for the number of children under 18 in the respondents' households.

Now compute the biased distribution we would see if we surveyed the children and asked them how many children under 18 (including themselves) are in their household.

Plot the actual and biased distributions, and compute their means.  

### Plotted Actual and Biased Distributions

```python

%matplotlib inline

import numpy as np

import nsfg
import first
import thinkstats2
import thinkplot
import matplotlib
import matplotlib.pyplot as plt

resp = nsfg.ReadFemResp()

pmf = thinkstats2.Pmf(resp.numkdhh, label='numkdhh')

thinkplot.Pmf(pmf)
thinkplot.Config(xlabel='Number of Children', ylabel = 'PMF')
plt.savefig('actual.png')
```

![image](/Users/gwendolynburke/prework/ThinkStats2/code/actual.png)

```python
def BiasPmf(pmf, label):
    new_pmf = pmf.Copy(label=label)

    for x, p in pmf.Items():
        new_pmf.Mult(x, x)
        
    new_pmf.Normalize()
    return new_pmf
biased_pmf = BiasPmf(pmf, label='biased')

thinkplot.Pmf(biased_pmf)
thinkplot.Config(xlabel='Number of Children', ylabel = 'PMF')
plt.savefig('biased.png')
```
![image](/Users/gwendolynburke/prework/ThinkStats2/code/biased.png)

### Computed Means
```python
print("Actual mean is str(pmf.Mean()).")
print("Biased mean is str(biased_pmf.Mean()).")
```
