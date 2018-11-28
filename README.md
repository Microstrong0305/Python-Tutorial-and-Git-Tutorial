# git-guide
git-guide

# 创建新仓库
创建新文件夹，打开，然后执行
```bash 
git init
```
以创建新的git仓库。

# 检出仓库
执行如下命令以创建一个本地仓库的克隆版本：
```bash
git clone /path/to/repository
```
如果是远端服务器上的仓库，你的命令会是这个样子：
```bash 
git clone usernamr@host:/path/to/repository
```

# 工作流
你的本地仓库由git维护的三颗“树”组成。第一个是你的《工作目录》，它持有实际文件；第二个是《缓存区（Index）》，它像个缓存区域，临时保存你的改动；最后是《HEAD》，指向你最近一次提交后的结果。
![工作流](https://github.com/Microstrong0305/git-guide/blob/master/workflow.png)



# 添加与提交
你可以计划改动（把它们添加到缓存区），使用如下命令：
```bash
git add <filename>
git add *
```
这是git基本工作流程的第一步；使用如下命令以实际提交改动：
```bash
git commit -m "代码提交信息"
```
现在，你的改动已经提交到了HEAD,但是还没到你的远端仓库。

# 推送改动
你的改动现在已经在本地仓库的HEAD中了。执行如下命令以将这些改动提交到远端仓库：
```bash
git push origin master
```
可以把master换成你想要推送的任何分支。
如果你还没有克隆现有仓库，并欲将你的仓库连接到某个远程服务器，你可以使用如下命令添加：
```bash
git remote add origin <server>
```
如此你就能够将你的改动推送到所添加的服务器上去了。

# 分支
分支是用来将特性开发绝缘开来的。在你创建仓库的时候，master是“默认的”。在其他分支上进行开发，完成后再将它们合并到主分支上。
![分支](https://github.com/Microstrong0305/git-guide/blob/master/branch.png)
创建一个叫做“feature_x”的分支，并切换过去：
```bash
git checkout -b feature_x
```
切换回主分支：
```bash
git checkout master
```
再把新建的分支删掉：
```bash
git branch -d feature_x
```
除非你将分支推送到远端仓库，不然该分支就是 不为他人所见的：
```bash
git push origin <branch>
```

# 更新与合并
要更新你的本地仓库至最新改动，执行：
```bash
git pull
```
以在你的工作目录中获取（fetch）并合并（merge）远端的改动。
要合并其他分支到你的当前分支（例如master）,执行：
git merge <branch>
两种情况下，git 都会尝试去自动合并改动。不幸的是，自动合并并非次次都能成功，并可能导致 冲突（conflicts）。 这时候就需要你修改这些文件来人肉合并这些 冲突（conflicts） 了。改完之后，你需要执行如下命令以将它们标记为合并成功：
```bash
git add <filename>
```
在合并改动之前，也可以使用如下命令查看：
```bash
git diff <source_branch> <target_branch>
```

# 标签
在软件发布时创建标签，是被推荐的。这是个旧有概念，在 SVN 中也有。可以执行如下命令以创建一个叫做 1.0.0 的标签：
```bash
git tag 1.0.0 1b2e1d63ff
```
1b2e1d63ff 是你想要标记的提交 ID 的前 10 位字符。使用如下命令获取提交 ID：
```bash
git log
```
你也可以用该提交 ID 的少一些的前几位，只要它是唯一的。

# 替换本地改动
假如你做错事（自然，这是不可能的），你可以使用如下命令替换掉本地改动：
```bash
git checkout -- <filename>
```
此命令会使用 HEAD 中的最新内容替换掉你的工作目录中的文件。已添加到缓存区的改动，以及新文件，都不受影响。

假如你想要丢弃你所有的本地改动与提交，可以到服务器上获取最新的版本并将你本地主分支指向到它：
```bash
git fetch origin
git reset --hard origin/master
```
# [git - 简易指南](http://www.bootcss.com/p/git-guide/)