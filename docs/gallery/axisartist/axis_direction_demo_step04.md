# 轴方向演示步骤04

![轴方向演示步骤04示例](/static/images/gallery/sphx_glr_axis_direction_demo_step04_001.png)

```python
import matplotlib.pyplot as plt
import mpl_toolkits.axisartist as axisartist


def setup_axes(fig, rect):
    ax = axisartist.Subplot(fig, rect)
    fig.add_axes(ax)

    ax.set_ylim(-0.1, 1.5)
    ax.set_yticks([0, 1])

    ax.axis[:].set_visible(False)

    ax.axis["x1"] = ax.new_floating_axis(1, 0.3)
    ax.axis["x1"].set_axisline_style("->", size=1.5)

    ax.axis["x2"] = ax.new_floating_axis(1, 0.7)
    ax.axis["x2"].set_axisline_style("->", size=1.5)

    return ax


fig = plt.figure(figsize=(6, 2.5))
fig.subplots_adjust(bottom=0.2, top=0.8)

ax1 = setup_axes(fig, "121")
ax1.axis["x1"].label.set_text("rotation=0")
ax1.axis["x1"].toggle(ticklabels=False)

ax1.axis["x2"].label.set_text("rotation=10")
ax1.axis["x2"].label.set_rotation(10)
ax1.axis["x2"].toggle(ticklabels=False)

ax1.annotate("label direction=$+$", (0.5, 0), xycoords="axes fraction",
             xytext=(0, -10), textcoords="offset points",
             va="top", ha="center")

ax2 = setup_axes(fig, "122")

ax2.axis["x1"].set_axislabel_direction("-")
ax2.axis["x2"].set_axislabel_direction("-")

ax2.axis["x1"].label.set_text("rotation=0")
ax2.axis["x1"].toggle(ticklabels=False)

ax2.axis["x2"].label.set_text("rotation=10")
ax2.axis["x2"].label.set_rotation(10)
ax2.axis["x2"].toggle(ticklabels=False)

ax2.annotate("label direction=$-$", (0.5, 0), xycoords="axes fraction",
             xytext=(0, -10), textcoords="offset points",
             va="top", ha="center")

plt.show()
```

## 下载这个示例
            
- [下载python源码: axis_direction_demo_step04.py](https://matplotlib.org/_downloads/axis_direction_demo_step04.py)
- [下载Jupyter notebook: axis_direction_demo_step04.ipynb](https://matplotlib.org/_downloads/axis_direction_demo_step04.ipynb)