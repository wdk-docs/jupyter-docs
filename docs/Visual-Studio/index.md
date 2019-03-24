# 在 Visual Studio 代码中使用 Jupyter 笔记本

Jupyter（以前称为 IPython）是一个开源项目，它允许您在一个称为笔记本的画布上轻松组合 Markdown 文本和可执行 Python 源代码。

要使用 Jupyter 笔记本，必须在 VS Code 或其他安装了 Jupyter 软件包的 Python 环境中激活 Anaconda 环境。
要选择环境，请使用命令选项板中的 **Python：Select Interpreter** 命令（**⇧⌘P**）。

激活适当的环境后，您可以创建和运行类似 Jupyter 的代码单元，连接到远程 Jupyter 服务器以运行代码单元，直接打开 Jupyter 笔记本，并将 Python 文件导出为 Jupyter 笔记本。

## Jupyter 代码单元格

您可以使用`＃%%`注释在 Python 代码中定义类似 Jupyter 的代码单元:

```py
#%%
msg = "Hello World"
print(msg)
```

当 Python 扩展检测到代码单元时，它会在注释上方添加一个 Run Cell 或 Run All Cells CodeLens:

Jupyter 在 VS Code 编辑器中为代码单元装饰

选择任一命令都会启动 Jupyter（如果需要，可能需要一分钟），然后在 Python 交互式窗口中运行单元格。

## 在 Python Interactive 窗口中运行的代码单元

您还可以使用 Python 运行代码单元：在 Python 终端中运行选择/行命令（Shift + Enter）。
使用此命令后，Python 扩展会自动将光标移动到下一个单元格。
如果您位于文件的最后一个单元格中，则扩展会自动为新单元格插入另一个＃%%分隔符，模仿 Jupyter 笔记本的行为。

### Python 交互式窗口

上一节中提到的 Python 交互式窗口可以用作具有任意代码的独立控制台（带或不带代码单元）。

要将窗口用作控制台，请使用命令选项板中的 Python：Show Python Interactive 窗口命令将其打开。
然后，您可以输入代码，使用 Enter 转到新行，按 Shift + Enter 运行代码。

要将窗口与文件一起使用，请使用命令选项板中的“在 Python 交互中运行当前文件”窗口命令。

## 连接到远程 Jupyter 服务器

您可以通过连接到远程 Jupyter 服务器将 Jupyter 笔记本中的密集计算卸载到其他计算机。
连接后，代码单元在远程服务器而不是本地计算机上运行。

要连接到远程 Jupyter 服务器：:

运行 Python：从命令选项板（⇧⌘P）指定 Jupyter 服务器 URI 命令。

出现提示时，提供服务器的 URI（主机名）以及包含在？token = URL 参数中的身份验证令牌。
(如果在启用了身份验证令牌的 VS Code 终端中启动服务器，则带有令牌的 URL 通常会显示在您可以复制它的终端输出中。)

提示提供 Jupyter 服务器 URI

Python 交互式窗口通过显示 URI（在下面的图像中模糊）来指示代码的运行位置:

Python 交互式窗口显示代码在远程 Jupyter 服务器上运行

## 打开 Jupyter 笔记本

当您激活安装了 Jupyter 的环境时，可以将 VS 代码中的 Jupyter 笔记本文件（.ipynb）导入为 Python 代码。
导入文件后，您可以像运行任何其他 Python 文件一样运行代码，也可以使用 VS Code 调试器。
在 VS Code 中打开和调试笔记本是查找和解决代码错误的便捷方式，这在 Jupyter 笔记本中很难直接进行。

当您打开笔记本文件时，Python 扩展会提示您将笔记本导入为 Python 代码文件：

提示导入 Jupyter 笔记本文件

选择 Import，等待几秒钟，然后 VS Code 在无标题文件中打开转换后的笔记本。
笔记本的单元格在 Python 文件中用＃%%注释分隔; Markdown 单元格完全转换为以＃%% [markdown]开头的注释，并在交互式窗口中呈现为 HTML 以及代码和输出（如图形）:

Jupyter 笔记本在 VS Code 和 Python 交互式窗口中运行

如果在不导入的情况下打开文件，它将显示为纯文本。

!!! Note ""

    第一次在笔记本文件中运行代码时，Python扩展会启动Jupyter服务器。
    服务器可能需要一些时间才能启动，并且Python Interactive窗口可能会显示代码的结果。

## 调试 Jupyter 笔记本

Visual Studio 代码调试器使您可以单步执行代码，设置断点，检查状态和分析问题。
使用调试器是查找和更正笔记本代码中的问题的有用方法。

在 VS Code 中，激活安装了 Jupyter 的 Python 环境，如本文开头所述。

将笔记本的.ipynb 文件导入 VS 代码，如上一节所述。
(如果您使用的是基于云的 Jupyter 环境（如 Azure 笔记本），请先下载该文件。)

按照说明配置和运行调试器，如配置并运行调试器，当然使用导入的.ipynb 文件，并在笔记本代码中的适当位置设置断点。

要熟悉 VS 代码的常规调试功能，例如检查变量，设置断点和其他活动，请查看 VS 代码调试。

当您发现问题时，请停止调试器，更正代码，保存文件，然后再次运行调试器。

如果您对所有代码都正确感到满意。
保存文件，然后按照以下部分中的说明导出笔记本。
然后，您可以将笔记本上载到普通的 Jupyter 环境中。

## 导出 Jupyter 笔记本

除了打开 Jupyter 笔记本之外，您还可以使用命令选项板（⇧⌘P）中的以下命令之一将内容从 VS Code 导出到 Jupyter 笔记本（扩展名为.ipynb）。

Python：将当前 Python 文件导出为 Jupyter Notebook：使用＃%%和＃%% [markdown]分隔符从当前文件的内容创建 Jupyter 笔记本，以指定其各自的单元格类型。

Python：将当前 Python 文件和输出导出为 Jupyter Notebook：根据当前文件的内容创建一个 Jupyter 笔记本，并包含代码单元格的输出。

Python：将 Python Interactive 窗口导出为 Jupyter Notebook：从 Python 交互窗口的内容创建一个 Jupyter 笔记本。

导出内容后，VS Code 会显示一个提示，您可以通过该提示在浏览器中打开笔记本。
