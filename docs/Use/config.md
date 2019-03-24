# 配置

## 摘要

常见的 Jupyter 配置系统 Jupyter 应用程序有一个通用的配置系统和一个通用的配置目录。
默认情况下，此目录为`~/.jupyter`。

内核配置目录如果内核使用配置文件，通常会将这些配置文件组织在每个内核的单独目录中。
例如，IPython 内核在 IPython 目录中查找文件而不是默认的 Jupyter 目录`〜/ .jupyter`。

## Python 配置文件

要创建默认配置文件，请运行:

```sh
jupyter {application} --generate-config
```

生成的文件将命名为 `jupyter_application_config.py`。

通过编辑 `jupyter_application_config.py` 文件，您可以像这样配置类属性:

```sh
c.NotebookApp.port = 8754
```

拼写小心。

将忽略不正确的名称，没有错误消息。

要添加到可能已在其他地方定义的集合，您可以使用列表，dicts 和集合中的方法：append，extend，prepend（）（如 extend，但在前面），添加和更新（适用于 dicts 和 sets）:

```sh
c.TemplateExporter.template_path.append('./templates')
```

## 用于配置的命令行选项

每个可配置的值也可以从命令行设置，并使用此语法作为参数传递:

```sh
jupyter notebook --NotebookApp.port=8754
```

经常使用的选项也会有短的别名和标志，例如`--port 8754`或`--no-browser`。

要查看缩写选项，请按以下方式传递`--help`或`--help-all`:

```sh
jupyter {application} --help # Just the short options
jupyter {application} --help-all # Includes options without short names
```

命令行选项将覆盖配置文件中设置的选项。

!!! note "See also"

    traitlets.config

    此配置系统的低级体系结构。
