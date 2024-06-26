# MVAscabank456
Computes a three dimensional scatterplot for X4 vs. X6 vs. X5 (lower inner frame vs. diagonal vs. upper inner frame) of the Swiss bank notes.

```python
# works on numpy 1.23.5, pandas 1.5.2 and matplotlib 3.6.2
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D

x = pd.read_csv("bank2.dat", sep = "\s+", header=None)
x456 = x.iloc[:,3:]
x1 = [1] * 100
x2  = [2] * 100
x1.extend(x2)
xx = x1

fig = plt.figure(figsize=(10, 10))
ax = fig.add_subplot(111, projection='3d')
ax.scatter(x456.iloc[:100, 0], x456.iloc[:100, 1], x456.iloc[:100, 2], c = "w", edgecolors = "black", s = 25)
ax.scatter(x456.iloc[100:, 0], x456.iloc[100:, 1], x456.iloc[100:, 2], c = "w", edgecolors = "r", marker = "^", s = 25)
ax.set_xlim(6, 14)
ax.set_ylim(6, 14)
ax.set_zlim(137, 142)

ax.set_xticks(list(range(6, 15, 2)))
ax.set_yticks(list(range(6, 15, 2)))

ax.set_xlabel("Lower inner frame (X4)")
ax.set_ylabel("Upper inner frame (X5)")
ax.set_zlabel("Diagonal (X6)")

ax.xaxis.pane.fill = False
ax.yaxis.pane.fill = False
ax.zaxis.pane.fill = False

plt.show()
```
![MVAscabank456](MVAscabank456_1_python.png)