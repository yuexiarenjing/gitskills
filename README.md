# gitskills

$ git config --global user.name "Your Name"     
$ git config --global user.email "email@example.com"

$ git init

$ git add <file>

$ git commit -m "record message"

$ git status     查看工作区状态

$ git diff <file>     查看修改内容，e.g. git diff HEAD -- readme.txt 查看当前文件和master分支中文件的不同

$ git reset --hard <commit-id>     HEAD指向当前版本，时光穿梭

$ git log     查看提交历史，以便回退到哪个版本

$ git reflog     查看命令历史，以便回到未来的哪个版本

$ git checkout -- <file>     改乱了工作区某文件，想直接丢弃工作区的修改 / 在工作区中误删文件，从版本库中恢复文件

$ git reset HEAD <file>     改乱了工作区且已经add，想丢弃的第一步，将暂存区内容返回到工作区，之后再执行git checkout -- <file>命令即可

$ git rm <file>     在工作区中删除一个文件，之后继续执行commit命令，删除版本库中的文件
 
$ ssh-keygen -t rsa -C "youremail@example.com"     生成公钥、私钥对

$ git remote add origin git@github.com:server-name:path/repo-name.git     关联一个远程库，远程库的名称为origin

$ git remote remove origin     删除远程库origin的关联

$ git push -u origin master     第一次推送master分支的所有内容，-u使本地master与远程库master建立连接，简化以后的操作

$ git push origin master     推送最新修改

$ git clone git@github.com:server-name:path/repo-name.git     通过ssh克隆，速度快

$ git clone https://github.com/server-name:path/repo-name.git     通过https协议克隆，速度慢

$ git branch     查看分支

$ git branch <name>     创建分支

$ git checkout <name>     切换分支

$ git checkout -b <name>     创建+切换分支

$ git merge <name>     合并某分支到当前分支

$ git branch -d <name>     删除分支

$ git log --graphy     查看分支合并图

$ git merge --no-ff -m "merge with no-ff" dev     不用fast forward合并分支，带有一个commit，并非简单的指针移动

$ git stash     保存工作现场，比如要去修改bug

$ git stash list     查看工作现场列表

$ git stash apply stash@{0}     恢复工作现场，不删除stash内容

$ git stash drop     上条命令需要这个命令手动删除stash内容

$ git stash pop     恢复工作现场并删除stash内容

$ git remote -v     查看远程信息库

$ git push origin branch-name     从本地推送分支

$ git pull     如果推送失败，先用此命令抓取新提交

$ git checkout -b branch-name origin/branch-name     在本地创建和远程分支对应的分支

$ git branch --set-upstream branch-name orgin/branch-name     建立本地分支和远程分支的关联，可解决git pull提示"no tracking information"问题

$ git tag <name>     新建一个标签，默认为HEAD，也可以指定一个commit id，后面加上<commit-id>

$ git tag -a <tagname> -m "message"     可以指定标签信息

$ git tag -s <tagname> -m "message"     可以用PGP签名标签

$ git tag     查看所有标签

$ git show <tagname>     查看标签信息

$ git push origin <tagname>     推送一个本地标签

$ git push origin --tags     推送全部未推送过的本地标签

$ git tag -d <tagname>     删除一个本地标签

$ git push origin :refs/tags/<tagname>     删除一个远程标签，需要先在本地删除再执行此命令

$ git config --global color.ui true     让Git显示颜色，会让命令看起来更醒目

忽略某些文件时，需要编写.gitignore     http://github.com/github/githubignore可以查找所有配置文件

.gitignore文件本身要放到版本库里，并且可以对.gitignore做版本管理

$ git config --global alias.st status

$ git config --global alias.co checkout

$ git config --global alias.ci commit

$ git config --global alias.br branch

$ git config --global alias.unstage 'reset HEAD'

$ git config --global alias.last 'log -1'

$ git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"

配置Git加上--global是针对当前用户其作用的，如果不加，只针对当前仓库起作用，每个仓库的Git配置文件都放在.git/config文件中，而当前用户的Git配置文件放在用户主目录下的一个隐藏文件.gitconfig中
