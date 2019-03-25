# 交互式小部件

Jupyter 小部件可在 Jupyter 笔记本中实现交互式数据可视化。

![icon to represent multiple notebooks](https://jupyter.org/assets/widget.svg)

Notebook Widgets

使用交互式小部件时，笔记本电脑变得活跃起来。
用户可以可视化和控制数据中的更改。学习成为一种沉浸式，有趣的体验。
研究人员可以很容易地看到改变模型的输入如何影响结果。

## ipyleaflet

地理空间分析

Binder GitHub
A library for creating simple interactive maps with panning and zooming, ipyleaflet supports annotations such as polygons, markers, and more generally any geojson-encoded geographical data structure.

Example
from ipyleaflet import Map

Map(center=[34.6252978589571, -77.34580993652344], zoom=10) +
−
Leaflet | Map data (c) OpenStreetMap contributors
Installation
With conda:
conda install -c conda-forge ipyleaflet
With pip:
pip install ipyleaflet
jupyter nbextension enable --py --sys-prefix ipyleaflet

## bqplot

二维交互式数据可视化

## pythreejs

三维数据可视化

## ipyvolume

三维绘图

## nglview

三维交互式分子可视化

## BeakerX

表格，绘图，表格

## jupyter-gmaps

Google 地图上的数据可视化

## cookiecutter

模板小部件项目
