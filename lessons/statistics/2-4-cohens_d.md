[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

### Question
Using the variable totalwgt_lb, investigate whether first babies are lighter or heavier than others.  

Compute Cohen’s effect size to quantify the difference between the groups. How does it compare to the difference in pregnancy length?  

## Answer

First babies are lighter than others on average by about 0.12 lbs. Cohen's effect size is -0.089, meaning the difference in mean weights in lbs of first babies and others is -0.089 standard deviations. The difference in weight is greater than the difference in pregnancy length.

```python
import nsfg
import math
import thinkstats2

difference = firsts.totalwgt_lb.mean() - others.totalwgt_lb.mean()
print(difference)

d = CohenEffectSize(firsts.totalwgt_lb, others.totalwgt_lb)
print(d)
```



