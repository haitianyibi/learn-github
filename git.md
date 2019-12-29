# 安装Git  
linux使用yum  
$sudo yum install git  
使用apt-get安装  
$sudo apt-get install git  
#anchor

# 升级
```git clone git://git.kernel.org/pub/scm/git/git.git```

# 配置
git config --global user.name "用户名字"  
git config --global user.email 123@132.com  
git config --global core.editor vim

# 查看配置
git config user.name  
git config --list

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