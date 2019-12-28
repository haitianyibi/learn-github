#安装Git  
linux使用yum
$sudo yum install git
使用apt-get安装
$sudo apt-get install git
# 升级
```git clone git://git.kernel.org/pub/scm/git/git.git```
# 配置
git config --global user.name "haitianyibi"  
git config --global user.email 842497899@qq.com  
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
git init
# 指定文件跟踪
git add <file.type>
# 提交
git commit -m'描述目的'
# 克隆已有仓库
git clone <url>
# 检查当前文件状态
git status  
git status -s  
git status -short  
>新添加的未跟踪文件前面有 ?? 标记，新添加到暂存区中的文件前面有 A 标记，修改过的文件前面有 M 标记。 你
可能注意到了 M 有两个可以出现的位置，出现在右边的 M 表示该文件被修改了但是还没放入暂存区，出现在靠左
边的 M 表示该文件被修改了并放入了暂存区。 例如，上面的状态报告显示： README 文件在工作区被修改了但
是还没有将修改后的文件放入暂存区,lib/simplegit.rb 文件被修改了并将修改后的文件放入了暂存区。 而
Rakefile 在工作区被修改并提交到暂存区后又在工作区中被修改了，所以在暂存区和工作区都有该文件被修改
了的记录
