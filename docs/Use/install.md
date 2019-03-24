# 安装

此信息说明如何安装 Jupyter Notebook 和 IPython 内核。

## 先决条件：Python

虽然 Jupyter 在许多编程语言中运行代码，但 Python 是安装 Jupyter Notebook 的必要条件（Python 3.3 或更高版本，或 Python 2.7）。

我们建议使用 Anaconda 发行版来安装 Python 和 Jupyter。
我们将在下一节中介绍它的安装。

## 使用 Anaconda 和 conda 安装 Jupyter

对于新用户，我们强烈建议安装 Anaconda。
Anaconda 可以方便地安装 Python，Jupyter 笔记本以及其他常用的科学计算和数据科学软件包。

使用以下安装步骤:

下载 Anaconda。我们建议下载 Anaconda 最新的 Python 3 版本（目前是 Python 3.5）。

按照下载页面上的说明安装您下载的 Anaconda 版本。

恭喜，您已经安装了 Jupyter Notebook。 要运行笔记本:

```sh
jupyter notebook
```

有关详细信息，请参阅运行笔记本。

## 有经验的 Python 用户的替代方案：使用 pip 安装 Jupyter

重要

Jupyter 安装需要 Python 3.3 或更高版本，或 Python 2.7。 IPython 1.x，包括后来成为 Jupyter 的部分，是支持 Python 3.2 和 2.6 的最后一个版本。

作为现有的 Python 用户，您可能希望使用 Python 的包管理器 pip 而不是 Anaconda 来安装 Jupyter。

首先，确保你有最新的点子;旧版本可能在某些依赖项上遇到问题:

```sh
pip3 install --upgrade pip
```

然后使用安装 Jupyter Notebook:

```sh
pip3 install jupyter
```

(如果使用旧版 Python 2，请使用 pip。)

恭喜。您已经安装了 Jupyter Notebook。有关详细信息，请参阅运行笔记本。
