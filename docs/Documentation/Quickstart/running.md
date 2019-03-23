# 运行笔记本

## Contents

- Basic Steps
- Starting the Notebook Server
- Introducing the Notebook Server’s Command Line Options

      - How do I open a specific Notebook?
      - How do I start the Notebook using a custom IP or port?
      - How do I start the Notebook server without opening a browser?
      - How do I get help about Notebook server options?

## 基本步骤

1.  从命令行启动笔记本服务器:

    ```sh
    jupyter notebook
    ```

2.  您应该在浏览器中看到笔记本打开.

## 启动 Notebook 服务器

在计算机上安装 Jupyter Notebook 后，即可运行笔记本服务器。
您可以通过运行命令行(使用 Mac/Linux 上的终端，Windows 上的命令提示符)启动笔记本服务器:

```sh
jupyter notebook
```

这将打印终端中有关笔记本服务器的一些信息，包括 Web 应用程序的 URL(默认情况下为 http://localhost:8888):

```sh
$ jupyter notebook
[I 08:58:24.417 NotebookApp] 从本地目录提供笔记本: /Users/catherine
[I 08:58:24.417 NotebookApp] 0个活动内核
[I 08:58:24.417 NotebookApp] Jupyter笔记本正在运行: http://localhost:8888/
[I 08:58:24.417 NotebookApp] 使用Control-C停止此服务器并关闭所有内核（两次跳过确认）.
```

然后，它将打开您的默认 Web 浏览器到此 URL。

当笔记本电脑在浏览器中打开时，您将看到 Notebook Dashboard，它将显示笔记本服务器启动目录中的笔记本，文件和子目录列表。
大多数情况下，您希望在包含笔记本的最高级目录中启动笔记本服务器。
通常这将是您的主目录。

笔记本仪表板

![_images/tryjupyter_file.png](https://jupyter.readthedocs.io/en/latest/_images/tryjupyter_file.png)

## 介绍笔记本服务器的命令行选项

### 如何打开特定的笔记本？

以下代码应在当前运行的笔记本服务器中打开给定的笔记本，必要时启动一个。

```sh
jupyter notebook notebook.ipynb
```

### 如何使用自定义 IP 或端口启动 Notebook？

默认情况下，笔记本服务器在端口 8888 上启动。如果端口 8888 不可用或正在使用，则笔记本服务器将搜索下一个可用端口。
您也可以手动指定端口。在此示例中，我们将服务器的端口设置为 9999:

```sh
jupyter notebook --port 9999
```

### 如何在不打开浏览器的情况下启动 Notebook 服务器？

无需打开 Web 浏览器即可启动笔记本服务器

```sh
jupyter notebook --no-browser
```

### 如何获得有关 Notebook 服务器选项的帮助？

笔记本服务器使用`--help`标志为其他命令行参数提供帮助消息:

```sh
jupyter notebook --help
```

!!! note "也可以看看"

    Jupyter安装，配置和使用
    有关命令行参数，配置和用法的详细信息。
