## 终端操作 ##

终端(Terminal) 操作对于很多开发者来说是必需的，
在终端下几乎可以进行所有的系统管理、开发调试、运行分析任务。

在Jupyter Notebook工作面板中，
点击 **New** - **Terminal** 可以创建一个新Terminal并进入其中进行操作，
如调用 vi 编辑文件，运行程序等。

Jupyter Notebook的WEB Terminal有个很重要的特点：可以在后台运行。
即使用户在浏览器中关闭了 Terminal 页面，其仍然在后台运行。
用户可以在 Jupyter Notebook的工作面板 - **Running** - **Terminals**
中找到正在运行的 Terminal ，点击进入其中，恢复工作场景。
这对于长运行的作业很有意义。

如果长时间没有操作 Terminal，可能会出现操作无反应现象，
刷新页面通常即可激活。 

如果要执行多个任务，可以打开多个 Terminal，
也可以在一个 Terminal 中使用 [tmux](https://tmux.github.io) 。

**补充**：
对于 Chrome 浏览器的用户，终端的字体可能不是等宽的，导致终端的宽度
会常常变化，可以通过设置 Chrome 的字体来修复这一问题。具体做法是： Chrome -> 
设置 -> 显示高级设置 -> 自定义字体 中，将**宽度固定的字体**修改为某种等宽字体，
比如 Droid Sans Mono.

### 安装软件包 ###

用户可以在WEB Terminal中安装软件包。基础系统是Ubuntu，用户使用 `apt-get`
命令进行安装。

```
$ apt-get install clang
```

如果用户希望未来将工作区保存为镜像，建议清除 `apt-get` 的缓存以减少空间
占用:

```
$ apt-get clean
```

有关`apt-get`，可参阅 
[帮助文档](https://help.ubuntu.com/community/AptGet/Howto)。

### 使用本地终端访问 ###

用户有时希望用本地计算机上的终端通过ssh访问docklet vnode. 由于docklet
vnode 在防火墙后面，因此用户不能直接用自己的计算机访问，但可以借助于一个
公共的ssh服务器实现.

假定有一个公共ssh服务器, 地址为 **pub.ssh**, 用户在该服务器上有一个帐号
**myname** .

用户在docklet vnode里执行下面的命令:

```
ssh -fNR 2222:localhost:22 myname@pub.ssh
```

成功后，所有连接到 **pub.ssh** 服务器上的 2222 端口 的ssh 请求都会转到
docklet vnode的 **localhost:22** 地址.

在本地计算机的终端中执行ssh命令 

```
ssh myname@pub.ssh
```

在pub.ssh上面再执行ssh命令连接到本地的2222端口:

```
ssh root@localhost -p 2222
```

此时可能会要求输入密码。该密码是docklet vnode上的账号密码。可以用**passwd**
命令为root用户设置一个，即可登录。

更多关于 ssh 端口转发的技术，可网上咨询相关资料。
