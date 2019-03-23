# Jupyter 项目

## 内容

- Jupyter User Interfaces
- Kernels
- Formatting and Conversion
- Education
- Deployment
- Architecture

Project Jupyter is developed as a set of subprojects. This section describes the subprojects with links to their documentation or GitHub repositories.

## Jupyter 用户界面

The Jupyter user interfaces offer a foundation of interactive computing environments where scientific computing, data science, and analytics can be performed using a wide range of programming languages.

Jupyter Notebook
Web-based application for authoring documents that combine live-code with narrative text, equations and visualizations. Documentation | Repo
Jupyter Console
Terminal based console for interactive computing. Documentation | Repo
Jupyter QtConsole
Qt application for interactive computing with rich output. Documentation | Repo

## 内核

Kernels are programming language specific processes that run independently and interact with the Jupyter Applications and their user interfaces. IPython is the reference Jupyter kernel, providing a powerful environment for interactive computing in Python.

IPython
interactive computing in Python. Documentation | Repo
ipywidgets
interactive widgets for Python in the Jupyter Notebook. Documentation | Repo
ipyparallel
lightweight parallel computing in Python offering seamless notebook integration. Documentation | Repo
See also

Jupyter kernels

A full list of kernels available for other languages. Many of these kernels are developed by third parties and may or may not be stable.

## 格式化和转换

Notebooks are rich interactive documents that combine live code, narrative text (using markdown), visualizations, and other rich media. The following utility subprojects allow programmatic format conversion and manipulation of notebook documents.

nbconvert
Convert dynamic notebooks to static formats such as HTML, Markdown, LaTeX/PDF, and reStrucuredText. Documentation | Repo
nbformat
Work with notebook documents programmatically. Documentation | Repo

## 教育

Jupyter Notebooks offer exciting and creative possibilities in education. The following subprojects are focused on supporting the use of Jupyter Notebook in a variety of educational settings.

nbgrader
tools for managing, grading, and reporting of notebook based assignments. Documentation | Repo
Deployment
To serve a variety of users and use cases, these subprojects are being developed to support notebook deployment in various contexts, including multiuser capabilities and secure, scalable cloud deployments.

jupyterhub
Multi-user notebook for organizations with pluggable authentication and scalability. Documentation | Repo
jupyter-drive
Store notebooks on Google Drive. Documentation | Repo
nbviewer
Share notebooks as static HTML on the web. Documentation | Repo
tmpnb
Create temporary, transient notebooks in the cloud. Documentation | Repo
tmpnb-deploy

## tmpnb 的部署工具。文档|回购

dockerspawner
Deploy notebooks for ‘jupyterhub’ inside Docker containers. Documentation | Repo
docker-stacks
Stacks of Jupyter applications and kernels as Docker containers. Documentation | Repo

## 结构

The Jupyter architecture relies on these projects’ specifications and implementation.

jupyter_client
The specification of the Jupyter message protocol and a client library in Python. Documentation | Repo
jupyter_core
Core functionality and miscellaneous utilities. Documentation | Repo
