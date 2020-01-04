[TOC]

# 一、git简介



![img](git.assets/Git-Logo-2Color.png)*注：官方logo下载在https://git-scm.com/downloads/logos*

[git](https://git-scm.com/)是一个免费的开源的分布式版本控制系统，可以快速高效的处理小型到大型项目的所有内容。

git是 [Linus Torvalds]([https://baike.baidu.com/item/%E6%9E%97%E7%BA%B3%E6%96%AF%C2%B7%E6%9C%AC%E7%BA%B3%E7%AC%AC%E5%85%8B%E7%89%B9%C2%B7%E6%89%98%E7%93%A6%E5%85%B9/1034429?fr=aladdin](https://baike.baidu.com/item/林纳斯·本纳第克特·托瓦兹/1034429?fr=aladdin)) 为了帮助管理 Linux 内核开发而开发的一个开放源码的版本控制软件。关于git的诞生可以在[廖雪峰的官方网站](https://www.liaoxuefeng.com/wiki/896043488029600/896202815778784) 或[git简史]([https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-Git-%E7%AE%80%E5%8F%B2](https://git-scm.com/book/zh/v2/起步-Git-简史))看到。

git易于学习，功能强大。它远远高出[Subversion](http://subversion.apache.org/)、[CVS](http://www.nongnu.org/cvs/)、[Perforce](https://www.perforce.com/)和[ClearCase](https://www.ibm.com/us-en/marketplace/rational-clearcase)之类的[SCM](https://baike.baidu.com/item/scm/2039966?fr=aladdin)工具，并且具有本地分支，方便的暂存区和多工作流等功能。

## 1.关于

### 分支与合并

真正使git能够从其它SCM工具中脱颖而出的功能是分支

git允许鼓励有多个彼此完全独立的本地分支，可以执行的操作：

* 自由的上下文切换：分支和合并
* 基于角色的代码行：不同分支的不同影响
* 基于特征的工作流：功能受分支影响
* 用后即弃的实验：分支删除不影响主分支

![Branches](git.assets/branches@2x.png)

---

### 小而快速

git几乎所有操作都在本地执行，与集中式版本控制需要网络速度相比更快。

git在linux内核上构建，可以有效处理大型存储库，git用c语言编写，速度和性能是git的主要设计目标

git最慢的操作是初始克隆操作，需要下载整个历史记录，而不是最新版本。

git在整个项目的整个历史记录具有每个文件的版本，但是客户端的数据大小由于压缩和存储数据的效率几乎不变。

---

### 分布式

可以实现无限数量的工作流，多重备份

集中式：

![工作流程A](git.assets/workflow-a@2x.png)





---

### 暂存区

与其他系统不同，Git具有称为“暂存区”或“索引”的名称。这是一个中间区域，可以在完成提交之前对提交进行格式化和检查。

使Git与其他工具区分开的一件事是，可以快速暂存某些文件并提交它们，而无需在工作目录中提交所有其他修改的文件，也不必在提交期间在命令行中列出它们。

![索引1](git.assets/index1@2x.png)

这使您只能暂存已修改文件的一部分。在意识到忘记提交其中一个文件之前，对文件进行两个在逻辑上不相关的修改的日子已经一去不复返了。现在，您可以暂存当前提交所需的更改，并暂存下一次提交的其他更改。此功能可根据需要扩展到文件的许多不同更改。

当然，如果您不想要这种控制，Git还可以轻松忽略此功能-只需在commit命令中添加“ -a”，以将对所有文件的所有更改添加到登台区域。

![索引2](git.assets/index2@2x.png)

---

# 二、安装Git

git官网https://git-scm.com/ 可以获取在线教程、官方pdf教程文档以及git相关工具等。

git源存储库https://github.com/git/git

git可安装在mac os x、windows、linux/unix系统上。git for windows（msysgit）与git是不同的项目

---

[下载git](https://git-scm.com/download/)版本2.24.1.2 64位版本，双击安装。

![image-20200104135038239](git.assets/image-20200104135038239.png)

---

Git是GNU通用公共许可证版本2（[GPLv2](https://www.gnu.org/licenses/old-licenses/gpl-2.0.html)）涵盖的开放源代码项目

![image-20200104140056009](git.assets/image-20200104140056009.png)

---

选择要安装的组件

* 在桌面添加icon图标
* 在windows右键快捷键加入集成**git bash here**和**git GUI here**
* 添加[git大文件支持](https://git-lfs.github.com/)
* 用默认文本编辑器关联.git配置文件夹
* [Bash](https://www.gnu.org/software/bash/)关联.sh文件
* 在windows控制台使用[truetype字体](https://docs.microsoft.com/en-us/typography/truetype/)
* 为git的windows版本每日检查更新

![image-20200104140544352](git.assets/image-20200104140544352.png)

---

选择git的默认编辑器

* [vim](https://www.vim.org/)是git的默认编辑器，现在已经不推荐使用了。
* [Notepad++](https://notepad-plus-plus.org/)
* [visual studio code](https://code.visualstudio.com/)
* [visual studio code insider](https://code.visualstudio.com/insiders/)相当于bate版本
* [sublime text](https://www.sublimetext.com/)
* [Atom](https://github.com/atom/atom)

![image-20200104143151362](git.assets/image-20200104143151362.png)

这里选择visual studio code作为默认编辑器。

![image-20200104144133527](git.assets/image-20200104144133527.png)

---

设置PATH环境

* 仅在git bash命令行使用：不会影响现有path
* git 命令行和第三方软件（推荐）：git bash、命令提示符、windows powershell可以找到git的path
* 在命令提示符和可选的unix工具中使用git：会覆盖windows的工具路径，unix和windows有重名工具

![image-20200104150355344](git.assets/image-20200104150355344.png)

---

选择[HTTPS](https://baike.baidu.com/item/https/285356?fr=aladdin)传输后端

* 使用[OpenSSL](https://www.openssl.org/)库
* 使用本地[windows安全通道](https://docs.microsoft.com/zh-cn/windows-hardware/drivers/display/communicating-through-a-secure-channel)库

![image-20200104151642023](git.assets/image-20200104151642023.png)

这里选择openssl

---

配置结束转换的行

* **检查**换行格式为windows格式，**提交**为unix换行格式

git检查文本时会将**LF**替换为**CRLF**，提交文件时会将CRLF替换为LF，交叉平台项目建议设置在windows

* 检查不做替换，提交时转化为unix换行格式

git在检查时不做转换，提交文件时CRLF替换为LF，交叉平台项目建议设置在unix,core.autocrlf设为input

* 不对换行格式转换

git不会再检查和提交时对**换行符**替换，不建议在交叉平台项目上选择，core.autocrlf设为false

![image-20200104153033470](git.assets/image-20200104153033470.png)

这里选择windows格式的换行

不同平台下结束符差别，配置不对会出错，[参考](https://my.oschina.net/moooofly/blog/228467)

 Windows 使用回车CR\r和换行LF\n两个字符来结束一行，而 Mac 和 Linux 只使用换行LF一个字符

---

配置git bash的终端模拟器

* mintty（[MSYS2](http://www.msys2.org/))的默认终端）

git bash 使用[mintty](http://mintty.github.io/)作为终端模拟器，mintty支持可变窗口大小，非矩形选择和unicode格式，windows控制台程序，如交互的python程序必须在mintty通过winpty启动，winpty使mintty终端具有交互性

* windoes自带的控制台

即cmd.exe,可以很好适应windows32位系统控制台程序，如[python](https://www.python.org/)、[node.js](https://nodejs.org/en/)。但是默认限制stroll-back回滚,需要配置使用[unicode](http://unicode.org/main.html)格式才能正确显示非[ASCII](https://www.iana.org/assignments/character-sets/character-sets.xhtml)编码格式,在windows10之前不允许自由调整字体大小，只允许矩形文本选择。

![image-20200104155102263](git.assets/image-20200104155102263.png)

这里选择mintty

---

配置额外的选项

* 允许文件系统缓存

文件系统数据会被批量读，特定操作会在内存上缓存数据(core.fscache设置为true)，可以有效提升速度。

* 允许[git凭证管理器](https://github.com/Microsoft/Git-Credential-Manager-for-Windows)

windows版本的git凭证管理器提供安全windows的git凭证保存，最著名的多重身份验证被github和visual studio 支持，需要,NET framework v4.5.1以上。

* 允许[符号链接](https://github.com/git-for-windows/git/wiki/Symbolic-Links)

允许符号链接（需要secreatesymmboliclink许可）通过设置声明已存在的仓库不会被影响

![image-20200104164013210](git.assets/image-20200104164013210.png)

默认选择前两个选项

---

配置实验选项（前沿特性）

* 使用实验性功能，内置 add -i/-p命令

使用实验性功能内置交互命令add(git add -i或git add -p),这会使启动更快，但是目前还不健壮。

![image-20200104170751932](git.assets/image-20200104170751932.png)

---

点击安装

从cmd或者右键git bash here出现的mingw64，输入`git`回车会弹出git的一些命令消息

![image-20200104171631604](git.assets/image-20200104171631604.png)

在mingw64输入mintty会弹出选项选择一个终端

![image-20200104171711812](git.assets/image-20200104171711812.png)



# 三、安装GUI

[GUI客户端](https://git-scm.com/downloads/guis)

使用GUI客户端不需要命令行的键入，更友好、更智能。

选择目前比较流行的[github桌面](https://desktop.github.com/)windows64位，注册github

# 四、git基础
### 更新git

git升级本质也是git clone将最新版本的git下载到本地

选择一个空文件夹，右键`git bash here`，在终端键入

```git clone git://git.kernel.org/pub/scm/git/git.git```

将会出现git文件夹，子文件夹包含.git文件夹，该方法速度较慢建议在官网直接下载最新版安装替换

![image-20200104200413213](git.assets/image-20200104200413213.png)

### 配置git

git config --global user.name "用户名字"  
git config --global user.email 123@132.com  
git config --global core.editor vim

使用--globa选项只需运行一次，需要对项目做特殊配置则在项目目录下使用无--global选项的命令配置

### 检查配置信息

git config --list或使用git config <key>对某一项配置检查，如：git  config user.name

### 获取帮助

git help <verb>  
git <verb> --help  
git help config获取config命令的手册，以浏览器打开或者git config --help

### 初始化git仓库

想要对现有项目进行管理，在该项目目录使用git bash here并键入

**git init**  创建了.git文件子目录，该目录含有初始化git仓库的所有必须文件，提示初始化空git仓库在G://github/git/.git文件夹中，无论git文件夹中有无文件都会提示相同信息，但是如果已经存在了.git文件夹，会提示重新初始化存在的git仓库在G://github/git/.git文件夹中，如果对文件添加了跟踪或者提交，git init不会影响这个状态，即如果有.git文件夹git init操作将不会做任何动作。

![image-20200104203115809](git.assets/image-20200104203115809.png)

![image-20200104204810988](git.assets/image-20200104204810988.png)

想要克隆别人的项目需要使用git clone命令，git支持多种数据传输协议，包括https://协议和git://协议，SSH传输协议，GitHub在仓库主页选择clone or download即下载或clone本质是一样的

![image-20200104214400751](git.assets/image-20200104214400751.png)

![image-20200104214842972](git.assets/image-20200104214842972.png)

可以选择open in deesktop会自动clone下载，或选择下载zip压缩文件，或选择复制https协议的URL或SSH协议

![image-20200104215107731](git.assets/image-20200104215107731.png)

完成后会在clone的目录下出现仓库名称的文件夹



**echo "# 标题" >  abc.md** 建立**文件名.类型**，并输入内容。

# 文件跟踪及忽略
**git add <file.type> **加入到暂存区

创建.gitignore文件。

#表示注释，每一行指定一个忽略规则，并且忽略规则有[优先级参考](https://www.cnblogs.com/kevingrace/p/5690241.html)

*。[oa] 忽略以.o或.a结尾的文件。星号匹配零个或任意多个字符

*~ 忽略以波浪线结尾的文件。

！123.txt 除了123.txt跟踪之外其它文件都忽略，！表示取反。

忽略规则扩展<https://github.com/github/gitignore>

 

 # 提交
git commit -m'描述目的'

若已跟踪内容修改后未跟踪而提交，则提交的是之前的副本。

git checkout -- 文件名.类型   撤销提交，返回上一次提交状态。



# 克隆已有仓库
http://协议

git clone <url>

git clone <url>  别名

git://协议

ssh协议



# 检查当前文件状态
git status  
git status -s 新添加未跟踪文件？？，暂存区文件A，修改过文件M在左边未跟踪，右边已跟踪，

git status --short  

git diff 比较当前文件和在暂存区文件的差异，即修改后未跟踪最新文件。

# 移除文件

git rm 文件名.文件类型

# 查看提交历史

git log 

# 远程仓库

git remote  -v 显示origin表示克隆仓库的默认名字，已经克隆到本地。-v显示URL。

git remote add 简写名字 URL 添加远程仓库并设置简名代替URL，

git fetch 简名  拉取简名代替的URL内容。仅将远程仓库复制本地不会合并修改当前工作。

使用git clone 会自动克隆仓库并添加远程仓库，设置简名origin

git pull origin master 备份到服务器master分支，若以有人先pull后，本地版本和服务器版本不同，需要拉取下来合并后才能推送，

git remote show origin 显示更多远程仓库信息。

git remote rename origin abc   远程仓库重命名将origin修改为abc

git remote rm 简名  移除远程仓库的指向 ，本质远程仓库还在，如不在未某个仓库贡献了。

# 标签

# 分支

git branch 分支名  创建分支

# git参考

 