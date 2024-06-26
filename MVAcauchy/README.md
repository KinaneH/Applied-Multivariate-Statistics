# MVAcauchy
Plots three probability density functions and three cumulative density functions of
the Cauchy distribution with m = 0 and different scale parameters (s=1, s=1.5, s=2).

```python
# works on numpy 1.23.5, matplotlib 3.6.2 and scipy 1.10.0
import numpy as np
from scipy.stats import cauchy
import matplotlib.pyplot as plt

# PDF of cauchy distribution
xx = np.arange(-6, 6, 0.1)
pdf1 = cauchy.pdf(xx, scale = 1)
pdf1_5 = cauchy.pdf(xx, scale = 1.5)
pdf2 = cauchy.pdf(xx, scale = 2)

fig1, ax1 = plt.subplots(1,1,figsize=(10, 10))

ax1.plot(xx, pdf1, 'k-', linewidth=3, label='s = 1')
ax1.plot(xx, pdf1_5, 'b-', linewidth=3, label='s = 1.5')
ax1.plot(xx, pdf2, 'r-', linewidth=3, label='s = 2')
ax1.set_xlabel('X', fontsize=16)
ax1.set_ylabel('Y', fontsize=16)
ax1.set_title('PDF of Cauchy distribution', fontsize=23)
fig1.legend(fontsize=18, loc =(0.79, 0.45))

plt.tight_layout()
plt.show()

# CDF of cauchy distribution
cdf1 = cauchy.cdf(xx, scale = 1)
cdf1_5 = cauchy.cdf(xx, scale = 1.5)
cdf2 = cauchy.cdf(xx, scale = 2)

fig2, ax2 = plt.subplots(1,1,figsize=(10, 10))

ax2.plot(xx, cdf1, 'k-', linewidth=3, label='s = 1')
ax2.plot(xx, cdf1_5, 'b-', linewidth=3, label='s = 1.5')
ax2.plot(xx, cdf2, 'r-', linewidth=3, label='s = 2')
ax2.set_xlabel('X', fontsize=16)
ax2.set_ylabel('Y', fontsize=16)
ax2.set_title('CDF of Cauchy distribution', fontsize=23)
fig2.legend(fontsize=18, loc =(0.79, 0.45))

plt.tight_layout()
plt.show()
```
![MVAcauchy](MVAcauchy01_python.png)
![MVAcauchy](MVAcauchy02_python.png)
