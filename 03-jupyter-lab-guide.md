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