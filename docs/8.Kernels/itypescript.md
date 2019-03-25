# ITypescript

[ITypescript](https://github.com/nearbydelta/itypescript) is an [`npm` package](https://www.npmjs.com/) that implements a TypeScript kernel for the [Jupyter notebook](http://jupyter.org/), as a modification of [IJavascript kernel](http://n-riesco.github.io/ijavascript).
Jupyter 笔记本将富文本文档（包括方程式，图形和视频）的创建与许多编程语言中的代码执行相结合。

代码的执行是通过实现[IPython/Jupyter 消息传递协议](http://jupyter-client.readthedocs.io/en/latest/messaging.html)的内核来执行的.
There are kernels available for [Python](http://ipython.org/notebook.html), [Julia](https://github.com/JuliaLang/IJulia.jl), [Ruby](https://github.com/minad/iruby), [Haskell](https://github.com/gibiansky/IHaskell) and [many other languages](https://github.com/ipython/ipython/wiki/IPython-kernels-for-other-languages).

Again, We have to emphasize these code is originally come from [IJavascript kernel](http://n-riesco.github.io/ijavascript).
We converted the code into typescript, and modified tiny fraction of it.

## 主要特点

- Run TypeScript code within a `node.js` session

Following examples are translation of [IJavascript](http://n-riesco.github.io/ijavascript)'s
examples, from javascript to typescript.

- [Hello, World!](https://github.com/nearbydelta/itypescript/tree/master/doc/hello.ipynb)
- [Graphical
  output](https://github.com/nearbydelta/itypescript/tree/master/doc/graphics.ipynb) for
  `HTML`, `SVG`, `PNG`, ...
- [Asynchronous
  output](https://github.com/nearbydelta/itypescript/tree/master/doc/async.ipynb)
- [Autocompletion](https://github.com/nearbydelta/itypescript/tree/master/doc/Completion.Inspection.ipynb):
  press `TAB` to complete keywords and object properties
- [Object
  inspection](https://github.com/nearbydelta/itypescript/tree/master/doc/Completion.Inspection.ipynb): press
  `Shift-TAB` to inspect an object and show its content or, if available, its
  documentation

## 安装

### 先决条件

如果您使用的是 Typescript，则应首先安装`node.js`。
按照[Node.js 下载页面](https://nodejs.org/en/download/)或[Node.js 安装页面](https://nodejs.org/en/download/package-manager/)的说明进行操作.

此外，你必须安装`jupyter`.按照[安装 Jupyter 笔记本](http://jupyter.readthedocs.io/en/latest/install.html)的说明进行操作.

### 单机

安装完成后，键入以下 shell 命令（Linux/Unix/Mac）安装 ITypescript:

```sh
sudo -H npm install -g itypescript
```

对于 Windows，找到`node.js prompt`，以管理员身份运行，然后输入:

```sh
npm install -g itypescript
```

### Jupyter 内核

您可以使用以下命令全局安装`itypescript`内核:

```sh
sudo -H its --install=global
```

或者您可以在本地安装它:

```sh
its --install=local
```

如需进一步使用，请查看[usage.md](https://github.com/nearbydelta/itypescript/blob/master/doc/usage.md)

## 捐款

First of all, thank you for taking the time to contribute.
Please, read [CONTRIBUTING](http://github.com/nearbydelta/itypescript/blob/master/CONTRIBUTING.md) and use the [issue tracker](http://github.com/nearbydelta/itypescript/issues) for any contributions: support requests, bug reports, enhancement requests, pull requests, submission of tutorials...
