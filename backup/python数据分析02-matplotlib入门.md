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

# 入门eg2
```python
from matplotlib import pyplot as plt

# 设置图片大小
plt.figure(figsize=(20, 8), dpi=80)
_xtick_labels = [i / 2 for i in range(4, 50)]

x = range(2, 26, 2)

y = [15, 13, 14.5, 17, 20, 25, 26, 26, 27, 22, 18, 15]
# 设置刻度
plt.xticks(_xtick_labels[::3])
_ytick_labels = range(min(y), max(y) + 1)
plt.yticks(_ytick_labels)

# 绘图
plt.plot(x, y)

# 显示
plt.show()

```
> 效果如下
![1FA72cHKQnBN5ks.png](https://s2.loli.net/2024/07/25/1FA72cHKQnBN5ks.png)

# 课后练习
1. 如果列表a表示10点到12点的每一分钟的气温，如何绘制折线图观察每分钟气温的变化情况？
  a = [random.randint(20,35) for i in range(120)]
```python
import random

from matplotlib import pyplot as plt
import matplotlib

font = {'family': 'MicroSoft YaHei',
        'weight': 'bold',
        'size': 10}
# 设置中文适配
matplotlib.rc("font", **font)
plt.figure(figsize=(20, 8), dpi=80)
x = range(120)
y = [random.randint(20, 25) for i in range(120)]
_x = list(x)[::10]
_xticks_lalbel = ["十点{}分".format(i) for i in range(60)]
_xticks_lalbel += ["十一点{}分".format(i) for i in range(60)]
plt.xticks(_x, _xticks_lalbel[::10], rotation=45)

# 添加描述信息
plt.xlabel("时间")
plt.ylabel("温度 单位（℃）")
plt.title("十点到十一点每分钟的气温变化情况")
plt.plot(x, y)
plt.show()

```

2. 绘制散点图
```python
from matplotlib import pyplot as plt
import matplotlib

font = {'family': 'MicroSoft YaHei',
        'weight': 'bold',
        'size': 10}
matplotlib.rc("font", **font)
y_3 = [11, 17, 16, 11, 12, 11, 12, 6, 6, 7, 8, 9, 12, 15, 14, 17, 18, 21, 16, 17, 20, 14, 15, 15, 15, 19, 21, 22, 22,
       22,
       23]
y_10 = [26, 26, 28, 19, 21, 17, 16, 19, 18, 20, 20, 19, 22, 23, 17, 20, 21, 20, 22, 15, 11, 15, 5, 13, 17, 10, 11, 13,
        12,
        13, 6]
x_3 = range(1, 32)
x_10 = range(51, 82)
# 设置图形大小
plt.figure(figsize=(20, 8), dpi=80)
plt.scatter(x_3, y_3, label="111")
plt.scatter(x_10, y_10, label=222)

# 设置x轴的刻度
x_3tick_labels = ['3月{}日'.format(i) for i in x_3]
x_10tick_labels = ['3月{}日'.format(i - 50) for i in x_10]
plt.xticks((list(x_3) + list(x_10))[::3], (x_3tick_labels + x_10tick_labels)[::3])
plt.xlabel("时间")
plt.ylabel("温度")
plt.legend(loc="upper right")
plt.show()

```
效果图如下
![a7D4SvTwHVolKc6.png](https://s2.loli.net/2024/07/26/a7D4SvTwHVolKc6.png)

3. 绘制条形图
```python
from matplotlib import pyplot as plt
import matplotlib

font = {'family': 'MicroSoft YaHei',
        'weight': 'bold',
        'size': 10}
plt.figure(figsize=(18, 8), dpi=80)
matplotlib.rc("font", **font)
a = ["战狼2", "速度与激情8", "功夫瑜伽", "西游伏妖篇", "变形金刚5：最后的骑士", "摔跤吧爸爸", "加勒比海盗5：死无对证",
     "金刚：骷髅岛", "极限特工：终极回归", "生化危机6：终章", "乘风破浪", "神偷奶爸3", "智取威虎山", "大闹天竺",
     "金刚狼3：殊死一战", "蜘蛛侠：英雄归来", "悟空传", "银河护卫队2", "情圣", "新木乃伊"]
b = [56.01, 26.94, 17.53, 16.49, 15.45, 12.96, 11.8, 11.61, 11.28, 11.12, 10.49, 10.3, 8.75, 7.55, 7.32,
     6.99, 6.88, 6.86, 6.58, 6.23]
plt.yticks(range(len(a)), a, label="电影")
plt.barh(range(len(a)), b, height=0.5, color="red")
plt.grid(alpha=0.5)
plt.legend(loc='upper right')
plt.show()
```
效果图如下
![feCVbsyJjNRn1ui.png](https://s2.loli.net/2024/07/26/feCVbsyJjNRn1ui.png)
4. 绘制条形图（横）
```python
from matplotlib import pyplot as plt
import matplotlib

font = {'family': 'MicroSoft YaHei',
        'weight': 'bold',
        'size': 10}
plt.figure(figsize=(18, 8), dpi=80)
matplotlib.rc("font", **font)
a = ["战狼2", "速度与激情8", "功夫瑜伽", "西游伏妖篇", "变形金刚5：最后的骑士", "摔跤吧爸爸", "加勒比海盗5：死无对证",
     "金刚：骷髅岛", "极限特工：终极回归", "生化危机6：终章", "乘风破浪", "神偷奶爸3", "智取威虎山", "大闹天竺",
     "金刚狼3：殊死一战", "蜘蛛侠：英雄归来", "悟空传", "银河护卫队2", "情圣", "新木乃伊"]
b = [56.01, 26.94, 17.53, 16.49, 15.45, 12.96, 11.8, 11.61, 11.28, 11.12, 10.49, 10.3, 8.75, 7.55, 7.32,
     6.99, 6.88, 6.86, 6.58, 6.23]
plt.yticks(range(len(a)), a, label="电影")
plt.barh(range(len(a)), b, height=0.5, color="red")
plt.grid(alpha=0.5)
plt.legend(loc='upper right')
plt.show()

```
效果图如下
![image](https://github.com/user-attachments/assets/9a6f57fc-77a9-493e-a1c5-2efa08867bf0)

# 课后名词/api
1. axis轴，指的是x轴或y这种坐标轴
2. figure 设置图片大小
6. xticks yticks 设置x/y轴的间隔
7. plot 绘制
8. legend 图例
9. scatter 散点图
