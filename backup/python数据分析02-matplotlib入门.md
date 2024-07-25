# 什么是matplotlib？
matplotlib是使用纯python实现的将数据进行可视化，更直观的呈现。使数据更加客观的、更具有说服力。

# 入门eg1
```python
# 引入
from matplotlib import pyplot as plt
x = range(2,26,2)
y = [15,13,14.5,17,20,25,26,26,27,22,18,15]
# 绘制
plt.plot(x,y)
```
> 效果如下
![689SRgE5ydXwhxu.png](https://s2.loli.net/2024/07/25/689SRgE5ydXwhxu.png)

# 课后名词
1. axis轴，指的是x轴或y这种坐标轴
