# 常见目录和文件位置

## 内容

- Configuration files
- Data files
- Runtime files
- Summary

Jupyter stores different files (i.e. configuration, data, runtime) in a number of different locations. Environment variables may be set to customize for the location of each file type.

## 配置文件

Config files are stored by default in the ~/.jupyter directory.

JUPYTER_CONFIG_DIR
Set this environment variable to use a particular directory, other than the default, for Jupyter config files.

Besides the user config directory mentioned above, Jupyter has a search path of additional locations from which a config file will be loaded. Here’s a table of the locations to be searched, in order of preference:

Unix Windows
JUPYTER_CONFIG_DIR
{sys.prefix}/etc/jupyter/
/usr/local/etc/jupyter/ /etc/jupyter/ %PROGRAMDATA%\jupyter\
To list the config directories currrently being used you can run the below command from the command line:

jupyter --paths

## 数据文件

Jupyter uses a search path to find installable data files, such as kernelspecs and notebook extensions. When searching for a resource, the code will search the search path starting at the first directory until it finds where the resource is contained.

Each category of file is in a subdirectory of each directory of the search path. For example, kernel specs are in kernels subdirectories.

JUPYTER_PATH
Set this environment variable to provide extra directories for the data search path. JUPYTER_PATH should contain a series of directories, separated by os.pathsep (; on Windows, : on Unix). Directories given in JUPYTER_PATH are searched before other locations.

Linux (& other free desktops) Mac Windows
JUPYTER_PATH
~/.local/share/jupyter/ (respects \$XDG_DATA_HOME) ~/Library/Jupyter %APPDATA%\jupyter
{sys.prefix}/share/jupyter/
/usr/local/share/jupyter /usr/share/jupyter %PROGRAMDATA\jupyter

## 运行时文件

Things like connection files, which are only useful for the lifetime of a particular process, have a runtime directory.

On Linux and other free desktop platforms, these runtime files are stored in \$XDG_RUNTIME_DIR/jupyter by default. On other platforms, it’s a runtime/ subdirectory of the user’s data directory (second row of the table above).

An environment variable may also be used to set the runtime directory.

JUPYTER_RUNTIME_DIR
Set this to override where Jupyter stores runtime files.

## 摘要

JUPYTER_CONFIG_DIR for config file location

JUPYTER_PATH for datafile directory locations

JUPYTER_RUNTIME_DIR for runtime file location

See also

jupyter_core.paths
The Python API to locate these directories.
The jupyter Command
Locate these directories from the command line.
