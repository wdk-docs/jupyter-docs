# 自定义 mimetypes (MIME types)

## 什么是 mimetype？

发生 Internet 请求和响应时，将传递 Content-Type 标头。
mimetype（也称为 MIME 类型）标识应由应用程序和浏览器根据类型处理或使用返回的内容的方式。
MIME 类型由 MIME 组（即应用程序，图像，音频等）和 MIME 子类型组成。
例如，MIME 类型是 image/png，其中 MIME 组是 image，子类型是 png。

由于类型可能包含供应商特定的项目，因此可以使用自定义供应商特定的 MIME 类型 vnd。
特定于供应商的 MIME 类型将包含 vnd，例如 application/vnd.jupyter.cells。

## Jupyter 和 IPython 项目中使用的自定义 mimetypes

- application/vnd.jupyter
- application/vnd.jupyter.cells
- application/vnd.jupyter.dragindex 由 nbdime 使用
- application/x-ipynb+json 用于笔记本
- text/html

      - metadata:
          - isolated: boolean – HTML应该在`<iframe>`中呈现。

## 列出用于显示的自定义 mimetypes

- application/vnd.geo+json - 现在不推荐使用 GeoJSON 规范 application/vnd.geo + json，并将其替换为 application/geo + json
- application/geo+json - 首选 GeoJSON 规范
- application/vnd.plotly.v1+json - Plotly JSON Schema
- application/vdom.v1+json - 虚拟 DOM 规范
