# 经常被问及的问题

??? faq "什么是 nbviewer？"

    nbviewer is a web application that lets you enter the URL of a Jupyter Notebook file, renders that notebook as a static HTML web page, and gives you a stable link to that page which you can share with others. nbviewer also supports browsing collections of notebooks (e.g., in a GitHub repository) and rendering notebooks in other formats (e.g., slides, scripts).

    nbviewer is an open source project under the larger Project Jupyter initiative along with other projects like Jupyter Notebook, JupyterLab, and JupyterHub.

??? faq "什么是 nbviewer.jupyter.org？"

    Project Jupyter runs a free, public instance of nbviewer at https://nbviewer.jupyter.org. You can use it to render Jupyter Notebooks or browse notebook collection on GitHub. In either case, the notebooks must have public web URLs.

    The homepage of nbviewer.jupyter.org includes some examples for you to try.

??? faq "nbviewer 如何呈现笔记本？"

    nbviewer is written in Python and JavaScript, uses nbconvert to render notebooks, and uses Tornado as its web server.

    You can install nbconvert locally and run jupyter nbconvert to get the same functionality (and more). See the nbconvert documentation for details.

??? faq "nbviewer 可以运行我的 Python，Julia，R，Scala 等笔记本吗？"

    nbviewer does not execute notebooks. It only renders the inputs and outputs saved in a notebook document as a web page.

    mybinder.org is a separate web service that lets you open notebooks notebooks in an executable environment, making your code immediately reproducible by anyone, anywhere. nbviewer shows an Execute on Binder icon in its navbar which

??? faq "为什么笔记本上没有出现“执行鼠标”按钮？"

    nbviewer only supports launching notebooks stored on GitHub or as Gists on Binder. Binder does support other providers directly on the mybinder.org site.

??? faq "为什么“按钮上的执行”按钮会导致 Binder 失败？"

    Binder tries to build a Docker image containing the notebooks and requirements declared in a git repository. The build will fail if the repository has a Dockerfile, requirements.txt, environment.yaml, etc. with issues. We suggest letting the repository owner know about the problem or submitting a pull request to help fix it.

??? faq "单击“在活页夹上执行”按钮后，为什么笔记本无法正常运行？"

    Binder builds a Docker image containing the notebooks in a git repository. Those notebooks may have requirements to run correctly such as libraries and data files. Binder can install these prerequisites as part of its build process, if the git repository declares them in a supported manner.

    If a notebook does not run properly in its Binder environment, we suggest letting the repository owner know about the problem or submitting a pull request to help fix it.

??? faq "嵌入在笔记本中的 JavaScript 是否适用于 nbviewer 呈现的页面？"

    Yes. This fact allows plots from plot.ly, Bokeh, and Altair to remain interactive, for example. It also means arbitrary JavaScript maybe execute when you visit the page, as it would on any page you visit on the Internet.

??? faq "我可以在 nbviewer 上加载私人笔记本吗？"

    nbviewer.jupyter.org can only render notebooks that it can access on the public Internet. If you are working on a notebook on your local machine, you need to publish that notebook somewhere with a public URL (e.g., in a GitHub repository, as a gist) in order for nbviewer.jupyter.org to render it.

    Hosting your own nbviewer server opens additional avenues for rendering private notebooks. For example, an nbviewer server on your university network can render notebook files accessible via URLs on that network. Please see the README in the nbviewer repository on GitHub for instructions and options.

??? faq "为什么我从 nbviewer 获得 404：Not Found 错误？"

    The URL you are visiting most likely points to a notebook that was moved or deleted. If you clicked a link on a site that lead to the 404 error page, we suggest you contact the site auownerthor to report the broken link. If a notebook author gave you the URL, we recommend asking them for an updated link.

    If you notice one of the links on the nbviewer.jupyter.org, please report it as a bug in the nbviewer issue tracker.

??? faq "当我尝试查看笔记本时，为什么会出现 4xx 错误？"

    nbviewer fetches notebooks from upstream providers (e.g., GitHub, GitHub gists, a public webserver) which host the the notebook files. You will see 4xx errors if the provider doesn't respond, the file nbviewer receives is invalid, the file is not publicly accessible, and so on.

    If you believe nbviewer is incorrectly showing a 4xx error for an accessible, valid notebook URL, please file a bug in the nbviewer issue tracker.

??? faq "当我尝试查看笔记本时，为什么会出现 5xx 或快速错误？"

    A 5xx error or an error page from fastly may indicate that the public nbviewer.jupyter.org site is being redeployed or is down. If the problem persists for more than a few minutes, please open a bug in the nbviewer issue tracker on GitHub including the URL you are visiting and the error you receive.

??? faq "为什么 nbviewer 显示我的笔记本的过时版本？"

    nbviewer caches rendered notebooks to cut down on rendering time for popular notebooks. The cache duration on nbviewer.jupyter.org is approximately 10 minutes. To invalidate the cache and force nbviewer to re-render a notebook page, append ?flush_cache=true to your URL.

??? faq "你如何选择 nbviewer.jupyter.org 主页上的笔记本？"

    We originally selected notebooks that we found and liked. We are currently soliciting links to refresh the home page using a Google Form. You may also open an issue with your suggestion.

??? faq "如何从 nbviewer 中删除笔记本？"

    nbviewer does not store any notebooks, it only renders notebooks stored elsewhere on the web given their URLs. If you've found a notebook that you think should be removed from the web, you'll need to locate where it is hosted (e.g., on GitHub) in order to update or remove it

??? faq "我可以使用 nbviewer 将笔记本转换为 HTML 以外的格式吗？"

    No. However, you can install nbconvert locally and run jupyter nbconvert to convert notebook files to a variety of format. See the nbconvert documentation for details.

??? faq "nbviewer.jupyter.org 在哪里托管？"

    Rackspace graciously hosts nbviewer.jupyter.org. Thanks to Rackspace, we are able to provider a public nbviewer instance as a free service.

??? faq "我可以通过 https 访问 nbviewer.jupyter.org 吗？"

    Yes. Please do.

??? faq "我可以运行自己的 nbviewer 服务器吗？"

    Yes, absolutely. Please see the README in the nbviewer repository on GitHub for instructions and options.

??? faq "如何报告 nbviewer 的错误或建议功能？"

    Please select the appropriate issue template in the nbviewer issue tracker on GitHub.

??? faq "是否有适用于 nbviewer 的有用工具？"

    Open in nbviewer - browser extensions and bookmarklets for opening the current URL in nbviewer
    gist extension - publish a notebook as a GitHub Gist and view it on nbviewer

??? faq "我在哪里可以提出其他问题？"

    Please post your questions about using nbviewer in the jupyter/help issue tracker or in the Jupyter Google Group. If you would like to propose an enhancement to nbviewer or file a bug report, please open an issue in the jupyter/nbviewer project on GitHub.
