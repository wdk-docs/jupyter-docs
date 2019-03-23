# Jupyter 的通用配置方法

## 内容

- Summary
- The Python config file
- Command line options for configuration

## 摘要

Common Jupyter configuration system The Jupyter applications have a common config system, and a common config directory. By default, this directory is ~/.jupyter.

Kernel configuration directories If kernels use config files, these will normally be organised in separate directories for each kernel. For instance, the IPython kernel looks for files in the IPython directory instead of the default Jupyter directory ~/.jupyter.

## Python 配置文件

To create a default config file, run:

jupyter {application} --generate-config
The generated file will be named jupyter_application_config.py.

By editing the jupyter_application_config.py file, you can configure class attributes like this:

c.NotebookApp.port = 8754
Be careful with spelling. Incorrect names will simply be ignored, with no error message.

To add to a collection which may have already been defined elsewhere, you can use methods like those found on lists, dicts and sets: append, extend, prepend() (like extend, but at the front), add, and update (which works both for dicts and sets):

c.TemplateExporter.template_path.append('./templates')

## 用于配置的命令行选项

Every configurable value can also be set from the command line and passed as an argument, using this syntax:

jupyter notebook --NotebookApp.port=8754
Frequently used options will also have short aliases and flags, such as --port 8754 or --no-browser.

To see the abbreviated options, pass --help or --help-all as follows:

jupyter {application} --help # Just the short options
jupyter {application} --help-all # Includes options without short names
Command line options will override options set within a configuration file.

See also

traitlets.config
The low-level architecture of this config system.
