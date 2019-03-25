# JupyterLab

[JupyterLab](http://jupyterlab.github.io/jupyterlab/)

基于 Web 的交互式和可重现计算的可扩展环境 Jupyter 笔记本和架构。 [目前已为用户准备](https://blog.jupyter.org/jupyterlab-is-ready-for-users-5a6f039b8906)。

[JupyterLab](http://jupyterlab.readthedocs.io/en/stable/)是[Project Jupyter](https://jupyter.org)的下一代用户界面，在灵活而强大的用户界面中提供经典 Jupyter 笔记本（笔记本，终端，文本编辑器，文件浏览器，丰富输出等）的所有熟悉构建模块。
JupyterLab 最终将取代经典的 Jupyter 笔记本。

JupyterLab can be extended using [npm](https://www.npmjs.com/) packages that use our public APIs. To find JupyterLab extensions, search for the npm keyword [jupyterlab-extension](https://www.npmjs.com/search?q=keywords:jupyterlab-extension) or the GitHub topic [jupyterlab-extension](https://github.com/topics/jupyterlab-extension). To learn more about extensions, see the [user documentation](https://jupyterlab.readthedocs.io/en/latest/user/extensions.html).

当前的 JupyterLab 版本适用于一般用途，扩展 API 将继续使用为 JupyterLab 扩展开发人员进化。

阅读[ReadTheDocs](http://jupyterlab.readthedocs.io/en/latest/)上的最新版本文档.

## 入门

### 安装

[install](http://jupyterlab.readthedocs.io/en/stable/getting_started/installation.html) JupyterLab using `conda`, `pip`, or `pipenv`. Conda is recommended if you have no installation preference.

Project installation instructions from the git sources are available in the [contributor documentation](CONTRIBUTING.md).

#### conda

Conda is an open source package management system and environment management system that runs on Windows, macOS, and Linux. Conda packages and distributes software for any language, and by default uses the Anaconda repository managed by Anaconda Inc. To install conda, please [see the conda installation instructions](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html).

Install the [JupyterLab `conda` package](https://anaconda.org/conda-forge/jupyterlab) with:

```bash
conda install -c conda-forge jupyterlab
```

#### pip

pip is a package management system for installing and updating Python packages, and comes with any Python installation. On Ubuntu and Fedora Linux, use the system package manager to install the `python3-pip` package. [\_The Hitchhiker's Guide to Python_provides guidance on how to install Python](https://docs.python-guide.org/starting/installation/); Another option is to [install Python directly from python.org](https://www.python.org/getit/). We suggest you [upgrade pip](https://pip.pypa.io/en/stable/installing/) before using it to install other programs.

JupyterLab requires Python 3.5 or higher.

1.  When using Windows with Python version 3.5 or higher, use the [Python Launcher for Windows](https://docs.python.org/3/using/windows.html?highlight=shebang#python-launcher-for-windows) to use `pip` with Python version 3:
    ```bash
    py -3 -m pip install jupyterlab
    ```
2.  If the system has a `python3` command (standard on Unix-like systems), install with the comand:
    ```bash
    python3 -m pip install jupyterlab
    ```
3.  Using the `python` command directly is another option, but this will use the _current_ version of Python (which may be Python version 2 or version 3 if both are installed):
    ```bash
    python -m pip install jupyterlab
    ```

Some systems have a `pip3` command that has the same effect as `python3 -m pip` and/or a `pip` command that behaves the same as `python -m pip`.

Adding `--user` after `pip install` will install the files to a local user install directory (typically `~/.local/` or `%APPDATA%\Python` on Windows) instead of the system-wide directory. This can be helpful, especially if writing to the system-wide directory is not permitted. However, the user-level `bin` directory must be added to the `PATH` environment variable in order to launch `jupyter lab`.

#### pipenv

`Pipenv` provides users and developers of applications with an easy method to setup a working environment, however Python must be installed first. See the [pipenv installation documentation](https://docs.pipenv.org/install) to use Pipenv if it is not installed.

`pipenv` can be installed as:

```bash
pipenv install jupyterlab
pipenv shell
```

or from a git checkout:

```bash
pipenv install git+git://github.com/jupyterlab/jupyterlab.git#egg=jupyterlab
pipenv shell
```

When using `pipenv`, in order to launch `jupyter lab`, activate the project's virtualenv. For example, in the directory where `pipenv`'s `Pipfile` and `Pipfile.lock` live (i.e., where the above commands were run):

```bash
pipenv shell
jupyter lab
```

#### 使用以前版本的 Jupyter Notebook 进行安装

When using a version of Jupyter Notebook earlier than 5.3, the following command must be run
after installation to enable the JupyterLab server extension:

```bash
jupyter serverextension enable --py jupyterlab --sys-prefix
```

### 运行

Start up JupyterLab using:

```bash
jupyter lab
```

JupyterLab will open automatically in the browser. See the [documentation](http://jupyterlab.readthedocs.io/en/stable/getting_started/starting.html) for additional details.

### 先决条件和支持的浏览器

Jupyter notebook version 4.3 or later is required. To check the notebook version, run the command:

```bash
jupyter notebook --version
```

The latest versions of the following browsers are currently _known to work_:

- Firefox
- Chrome
- Safari

See our [documentation](http://jupyterlab.readthedocs.io/en/latest/getting_started/installation.html) for additional details.

## 发展

### 特约

To contribute to the project, please read the [contributor documentation](CONTRIBUTING.md).

JupyterLab follows the Jupyter [Community Guides](https://jupyter.readthedocs.io/en/latest/community/content-community.html).

### 扩展 JupyterLab

To start developing an extension, see the [developer documentation](https://jupyterlab.readthedocs.io/en/latest/developer/extension_dev.html) and the [API docs](http://jupyterlab.github.io/jupyterlab/index.html).

### 执照

JupyterLab uses a shared copyright model that enables all contributors to maintain the
copyright on their contributions. All code is licensed under the terms of the revised [BSD license](https://github.com/jupyterlab/jupyterlab/blob/master/LICENSE).

### 球队

JupyterLab is part of [Project Jupyter](http://jupyter.org/) and is developed by an open community. The maintenance team is assisted by a much larger group of contributors to JupyterLab and Project Jupyter as a whole.

JupyterLab's current maintainers are listed in alphabetical order, with affiliation, and main areas of contribution:

- Chris Colbert, Project Jupyter (co-creator, application/low-level architecture,
  technical leadership, vision, PhosphorJS)
- Afshin Darian, Two Sigma (co-creator, application/high-level architecture,
  prolific contributions throughout the code base).
- Jessica Forde, Project Jupyter (demo, documentation)
- Tim George, Cal Poly (UI/UX design, strategy, management, user needs analysis)
- Brian Granger, Cal Poly (co-creator, strategy, vision, management, UI/UX design,
  architecture).
- Jason Grout, Bloomberg (co-creator, vision, general development).
- Fernando Perez, UC Berkeley (co-creator, vision).
- Ian Rose, UC Berkeley (Real-time collaboration, document architecture).
- Saul Shanabrook, Quansight (general development, extensions)
- Steven Silvester, JPMorgan Chase (co-creator, release management, packaging,
  prolific contributions throughout the code base).

Maintainer emeritus:

- Cameron Oelsen, Cal Poly (UI/UX design).

This list is provided to give the reader context on who we are and how our team functions.
To be listed, please submit a pull request with your information.

## 获得帮助

We encourage you to ask questions on the [Discourse forum](https://discourse.jupyter.org/c/jupyterlab). A question answered there can become a useful resource for others.

Please use the [GitHub issues page](https://github.com/jupyterlab/jupyterlab/issues) to provide feedback or submit a bug report.

### 每周开发会议

We have videoconference meetings every week where we discuss what we have been working on and get feedback from one another.

Anyone is welcome to attend, if they would like to discuss a topic or just to listen in.

- When: Wednesdays 9AM PT
- Where: [`calpoly/jupyter` Zoom](https://calpoly.zoom.us/my/jupyter)
- What: [Meeting notes on Dropbox Paper](https://paper.dropbox.com/doc/JLab-Dev-Meeting-Minutes-2019--AZlv6L3jnv8ntl6kJK88y5M5Ag-Lj0P4kI2JrbA0eXHZSdY5)
