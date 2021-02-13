# 安装和运行 Jupyter Lab

- **本文档拷贝自代码仓库文件[neolee/pilot/x2-students-book.md](https://github.com/neolee/pilot/blob/master/x2-students-book.md)**


因为学习用书都是用 Jupyter Notebook 写就的，要使用就需要安装 Jupyter Lab 环境，在我们已经装好 Python 的前提下这很容易，只要在命令行界面运行下面的命令就可以了：

```shell
python -m pip install --upgrade pip
pip install jupyterlab
```

`pip` 是 Python 自己的软件包管理工具，它负责安装、删除和管理 Python 浩若烟海的第三方代码库，我们以后会经常用到。上面第一行是更新 `pip` 自己，因为我们刚装好 Python，通常需要更新一下 `pip` 自己；第二行则是让 `pip` 安装 Jupyter Lab 以及所有依赖支持包。

> 如果在运行上面第二个命令时报错说找不到、不认识 `pip` 命令，可尝试将 `pip` 换成 `pip3`，即运行 `pip3 install jupyterlab`。

某些环境下运行 Jupyter Lab 需要 nodejs，所以建议也安装好。如果是 Winidows 系统，执行：

```powershell
scoop install nodejs
```

macOS 系统则执行：

```shell
brew install node
```

上述操作都成功后 Jupyter Lab 就准备就绪了，在你克隆好的学习用书目录里运行 `jupyter lab ↩︎` 来启动 Jupyter Lab 的服务程序，并打开一个浏览器页面，里面列出了学习用书里的所有 *notebook*（.ipynb 后缀名的文件），双击就能打开了。

> 注意，运行 `jupyter lab` 的命令行窗口必须保持着，你才能继续在浏览器里使用 Jupyter Lab；如果你用完了，需要退出，在这个命令行窗口按 Control+C 组合键，就会停止 Jupyter Lab 服务，回到命令行交互界面。一般来说不要在 `jupyter lab` 运行时关闭那个窗口。
> 
> 如果在 `jupyter lab` 运行着的时候你需要命令行界面执行一些任务，只要在 ConEmu 里打开一个新的 tab 就可以了，不用动之前的那个。

## 关于 Jupyter lab themes

*此部分来自李笑来老师的《自学是门手艺》一书的代码库 T-appendix.jupyter-installation-and-setup.ipynb 文件。*

对中文用户来说，Jupyter 的默认字号有点过小，阅读起来不是很舒适。但最佳的方案不是去寻找合适的 themes，而是直接使用支持 Stylus 这类终端 CSS 定制插件的浏览器，Chrome/Firefox/Opera 都支持 Stylus 插件。

我用的 Stylus 定制 CSS 是这样的：

```css
a {color: #2456A4 !important;}
strong {color:#6392BF;}
em {color: #A9312A; font-style: normal !important;}
table {font-size: 90% !important;}

#jp-main-dock-panel {background-color: #f9f9f9;}
.jp-RenderedHTMLCommon {font-family: "Yuanti SC"; font-size: 100%;}
.jp-Notebook {background-color: #fbfafa;}
.CodeMirror, .jp-RenderedHTMLCommon pre {font-size: 90%;}
.jp-RenderedHTMLCommon pre {
    padding: 10px 25px;
    background-color: #fafafa;
    border-left: 4px solid #dadada;
    border-radius: 10px;
}

.jp-RenderedHTMLCommon pre code {
    background-color: #fafafa;
}

.jp-RenderedHTMLCommon h1 code,
.jp-RenderedHTMLCommon h2 code,
.jp-RenderedHTMLCommon h3 code,
.jp-RenderedHTMLCommon h4 code,
.jp-RenderedHTMLCommon p code, 
.jp-RenderedHTMLCommon li code,
.jp-RenderedHTMLCommon blockquote p code, 
.jp-RenderedHTMLCommon blockquote li code,
.jp-RenderedHTMLCommon td code {
    background-color: #f6f6f6;
    font-size: 90%;
    color:#2e2e2e;
    padding: 4px 4px;
    margin: 0 8px;
    box-shadow: 0px 1px 2px 0px rgba(0,0,0,0.2);
    border-radius: 4px;
}
```

这样就相当于我把 JupyterLab Light 这个 Theme 稍微 Tweak 了一下。

另，我写的内容里，为了重点突出，特别定制了 `strong` 和 `em` 两个元素的显示，让它们以不同的颜色展示；又因为中文并不适合斜体展示，所以，把 `em` 的 `font-style` 设定为 `normal`……


## 安装插件

*此部分来自李笑来老师的《自学是门手艺》一书的代码库 T-appendix.jupyter-installation-and-setup.ipynb 文件。安装方式有修改。*

*此部分来自李笑来老师的《自学是门手艺》一书的代码库 T-appendix.jupyter-installation-and-setup.ipynb 文件。*

Jupyter notebook 经过很多年的发展，现在有很多扩展插件，但也有其中一些并不兼容最新的 Jupyter lab。不过，刚开始的时候用不着那么多插件，你只用其中的两个就足够开始了：

- @jupyterlab/toc
- ryantam626/jupyterlab_sublime

首先在jupyter lab 浏览器界面左侧标签点击command 标签, 在 Extension Manager 中，勾选 `Enable Extension Manager (experiment)` 选项。界面刷新后出现`extension manager` 标签。点击进入该标签后搜索上述两个插件，点击`install`安装。界面随后会自动刷新出现对应


安装toc 插件后，界面随后会自动刷新出现`Table of contents`标签。点击标签进入后可以看到已经自动将 ipynb 文件中的标题转换成目录。

jupyterlab_sublime 则可以让你在 Jupyter lab 的 cell 中，使用跟 SublimeText 一样的快捷键，比如 ⌘ D 能够多选其它与当前选中内容一样的内容；比如 ⌘ 加鼠标点击，可以生成多个可编辑点……


## 输出所有变量内容

*此部分来自李笑来老师的《自学是门手艺》一书的代码库 T-appendix.jupyter-installation-and-setup.ipynb 文件。*

为了显示最近 evaluate 的多个值，我们总是不得不使用很多的 print()……

如果觉得这事比较烦的话，可以在 Cell 最上面写上：

```python
from IPython.core.interactiveshell import InteractiveShell
InteractiveShell.ast_node_interactivity = "all"
```

如果还想更省事一点，就把这个设置写入配置文件：

```python
c.InteractiveShell.ast_node_interactivity = "all"
```


## 魔法函数

*此部分来自李笑来老师的《自学是门手艺》一书的代码库 T-appendix.jupyter-installation-and-setup.ipynb 文件。*

在 Code Cell 里，可以运行一些 “魔法函数”（Magic Functions），这是秉承了 IPython 的特性。绝大多数在 IPython 里能够使用的魔法函数在 Jupyterlab 里都可以直接使用。完整的 IPython 魔法函数请参照：

> https://ipython.readthedocs.io/en/stable/interactive/magics.html

Jupyterlab 里较为常用的魔法函数整理如下：

| 魔法函数             | 说明                                                         |
| -------------------- | ------------------------------------------------------------ |
| `%lsmagic`           | 列出所有可被使用的 Jupyter lab 魔法函数                      |
| `%run`               | 在 Cell 中运行 `.py` 文件：`%run file_name`                  |
| `%who`               | 列出所有当前 Global Scope 中的变量；类似的还有：`%who df`，`%whos` |
| `%env`               | 列出当前的环境变量                                           |
| `%load`              | 将其他文件内容导入 Cell，`%load source`，`source` 可以是文件名，也可以是 URL。|
| `%time`              | 返回 Cell 内代码执行的时间，相关的还有 `%timeit`             |
| `%writefile`         | 把 Cell 的内容写入文件，`%write file_name`；%write -a file_name，`-a` 是追加 |
| `%matplotlib inline` | 行内展示 matplotlib 的结果                                   |
| `%%bash`             | 运行随后的 shell 命令，比如 %%bash ls；与之类似的还有 `%%HTML`，`%%python2`，`%%python3`，`%%ruby`，`%%perl`……                      |


## 常用快捷键

- 按一下`ESC`，确保已经进入命令模式 
- `Shift L`可切换是否显示代码行号