[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

### Question
In the BRFSS (see Section 5.4), the distribution of heights is roughly normal with parameters µ = 178 cm and σ = 7.7 cm for men, and µ = 163 cm and σ = 7.3 cm for women.

In order to join Blue Man Group, you have to be male between 5’10” and 6’1” (see http://bluemancasting.com). What percentage of the U.S. male population is in this range? Hint: use scipy.stats.norm.cdf.

### Answer

```python
import scipy.stats

mu = 178
sigma = 7.7
dist = scipy.stats.norm(loc=mu, scale=sigma)

def height_in_cm(inches):
    return inches*2.54
    
low_end = height_in_cm(70)
high_end = height_in_cm(73)

low = dist.cdf(low_end)
high = dist.cdf(high_end)
print(high-low)
```
34.3% of the U.S. male population is in the Blue Man Group eligibility range