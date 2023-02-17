## matplotlib

matplotlib is xxx

### Quick Examples

#### 1, Plot a simple line


```python
import matplotlib.pyplot as plt
# define the 1st point's coordinate (x=1, y=2)
pt1 = [1, 2]
# define the 2nd point's coordinate (x=3, y=8)
pt2 = [3, 8]
# draw a line from point1 to point2, also mark these 2 points
plt.plot(pt1, pt2, marker="o")
plt.show()
```

<img src="../../assets/img/matplotlib-line.png" width="400px"/>
