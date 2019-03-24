# IPython 和 Jupyter Notebook 如何工作

## 抽象

本节重点介绍 IPython 和 Jupyter 笔记本以及它们如何交互。
当我们讨论 IPython 时，我们谈论两个基本角色:

终端 IPython 作为熟悉的 REPL。
IPython 内核，提供与前端接口的计算和通信，如笔记本。
Jupyter Notebook 及其灵活的界面将笔记本电脑从代码扩展到可视化，多媒体，协作等。

## 终端 IPython

当您键入 ipython 时，您将获得在终端中运行的原始 IPython 接口。
它做了这样的事情:

```py
while True:
code = input(">>> ")
exec(code)
```

当然，它要复杂得多，因为它必须处理多行代码，使用 readline 完成制表符，魔术命令等等。
但该模型就像代码示例：提示用户输入一些代码，当他们输入代码时，在同一个进程中执行它。
此模型通常称为 REPL 或 Read-Eval-Print-Loop。

## IPython 内核

所有其他接口 - Notebook，Qt 控制台，终端中的 ipython 控制台和第三方接口 - 都使用 IPython 内核。
IPython 内核是一个单独的进程，负责运行用户代码，以及计算可能的完成情况。
前端，如笔记本或 Qt 控制台，使用通过 ZeroMQ 套接字发送的 JSON 消息与 IPython 内核通信;在 Jupyter 的 Messaging 中描述了前端和 IPython 内核之间使用的协议。

内核的核心执行机制与终端 IPython 共享:

![ipy_kernel_and_terminal.png](https://jupyter.readthedocs.io/en/latest/_images/ipy_kernel_and_terminal.png)

内核进程可以同时连接到多个前端。
在这种情况下，不同的前端将可以访问相同的变量。

这种设计旨在允许基于相同内核轻松开发不同的前端，但它也可以通过开发这些语言的内核来支持同一前端的新语言，并且我们正在改进 IPython 以使其更加实用。

今天，有两种方法可以为另一种语言开发内核。
包装器内核重用 IPython 中的通信机制，并仅实现核心执行部分。
本机内核以目标语言实现执行和通信:

![other_kernels.png](https://jupyter.readthedocs.io/en/latest/_images/other_kernels.png)

对于具有良好 Python 包装的语言（如 octave_kernel），或者实现通信机制（如 bash_kernel）不切实际的语言，包装器内核更容易快速编写。
使用它们的社区可能会更好地维护本机内核，例如 IJulia 或 IHaskell。

!!! note "See also"

    为Jupyter制作内核

    内核

## 笔记本

笔记本前端做了额外的事情。
除了运行代码之外，它还将代码和输出以及降价笔记存储在名为 notebook 的可编辑文档中。
保存时，会将其从浏览器发送到笔记本服务器，笔记本服务器将其作为带有.ipynb 扩展名的 JSON 文件保存在磁盘上。

![notebook_components.png](https://jupyter.readthedocs.io/en/latest/_images/notebook_components.png)

笔记本服务器，而不是内核，负责保存和加载笔记本，因此即使您没有该语言的内核，您也可以编辑笔记本 - 您将无法运行代码。
笔记本服务器而不是内核负责保存和加载笔记本，因此即使您没有该语言的内核，也可以编辑笔记本 - 您将无法运行代码。

## 将笔记本导出为其他格式

Jupyter 中的 Nbconvert 工具将笔记本文件转换为其他格式，例如 HTML，LaTeX 或 reStructuredText。
此转换经历了一系列步骤:

![nbconvert.png](https://jupyter.readthedocs.io/en/latest/_images/nbconvert.png)

预处理器修改内存中的笔记本。
例如。 ExecutePreprocessor 运行笔记本中的代码并更新输出。
导出器将笔记本转换为另一种文件格式。
大多数出口商都使用模板。
后处理器处理导出生成的文件。
nbviewer 网站使用 nbconvert 和 HTML 导出器。
当您为其提供 URL 时，它会从该 URL 获取笔记本，将其转换为 HTML，并将该 HTML 提供给您。

## IPython.parallel

IPython 还包括一个并行计算框架，IPython.parallel。
这允许您控制许多单独的引擎，这些引擎是上述 IPython 内核的扩展版本。
