# 命令

## 概要

```sh
jupyter <subcommand> [options]
```

## 描述

像 `jupyter notebook` 这样的命令启动 Jupyter 应用程序。
jupyter 命令主要是子命令的命名空间。
在 `PATH` 上找到的像 `jupyter-foo` 这样的命令将作为子命令 `jupyter foo` 提供。

jupyter 命令也可用于执行除启动 Jupyter 应用程序之外的操作。

## 命令选项

```sh
# 显示帮助信息，包括可用的子命令。
-h, --help
```

```sh
# 显示 config 目录的位置。
--config-dir
```

```sh
# 显示数据目录的位置。
--data-dir
```

```sh
# 显示数据目录的位置。
--runtime-dir
```

```sh
# 显示所有 Jupyter 目录和搜索路径。
--paths
```

```sh
# 以机器可读的 JSON 格式打印目录和搜索路径。
--json
```
