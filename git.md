[TOC]

# 一、git简介



![img](git.assets/Git-Logo-2Color.png)*注：官方logo下载在https://git-scm.com/downloads/logos*

[git](https://git-scm.com/)是一个免费的开源的分布式版本控制系统，可以快速高效的处理小型到大型项目的所有内容。

git是 [Linus Torvalds]([https://baike.baidu.com/item/%E6%9E%97%E7%BA%B3%E6%96%AF%C2%B7%E6%9C%AC%E7%BA%B3%E7%AC%AC%E5%85%8B%E7%89%B9%C2%B7%E6%89%98%E7%93%A6%E5%85%B9/1034429?fr=aladdin](https://baike.baidu.com/item/林纳斯·本纳第克特·托瓦兹/1034429?fr=aladdin)) 为了帮助管理 Linux 内核开发而开发的一个开放源码的版本控制软件。关于git的诞生可以在[廖雪峰的官方网站](https://www.liaoxuefeng.com/wiki/896043488029600/896202815778784) 或[git简史]([https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-Git-%E7%AE%80%E5%8F%B2](https://git-scm.com/book/zh/v2/起步-Git-简史))看到。

git易于学习，功能强大。它远远高出[Subversion](http://subversion.apache.org/)、[CVS](http://www.nongnu.org/cvs/)、[Perforce](https://www.perforce.com/)和[ClearCase](https://www.ibm.com/us-en/marketplace/rational-clearcase)之类的[SCM](https://baike.baidu.com/item/scm/2039966?fr=aladdin)工具，并且具有本地分支，方便的暂存区和多工作流等功能。

# 二、安装Git

git官网https://git-scm.com/ 可以获取在线教程、官方pdf教程文档以及git相关工具等。

git源存储库https://github.com/git/git

git可安装在mac os x、windows、linux/unix系统上。

---

[下载git](https://git-scm.com/download/)版本2.24.1.2 64位版本。

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

![image-20200104143151362](git.assets/image-20200104143151362.png)

![image-20200104144133527](git.assets/image-20200104144133527.png)



# 三、安装GUI

[GUI客户端](https://git-scm.com/downloads/guis)



# 升级
```git clone git://git.kernel.org/pub/scm/git/git.git```

# 配置
git config --global user.name "用户名字"  
git config --global user.email 123@132.com  
git config --global core.editor vim

# 查看配置
```git config user.name  ```
`git config --list`

# 获取帮助
git help <verb>  
git <verb> --help  
man git-<verb>  
git help config

# 初始化git仓库
**git init**  创建了.git文件子目录

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