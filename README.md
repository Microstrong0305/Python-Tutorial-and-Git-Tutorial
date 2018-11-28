# git-guide
git-guide

# 创建新仓库
1. 创建新文件夹，打开，然后执行
```bash 
git init
```
以创建新的git仓库。

# 检出仓库
1. 执行如下命令以创建一个本地仓库的克隆版本：
```bash
git clone /path/to/repository
```
2. 如果是远端服务器上的仓库，你的命令会是这个样子：
```bash 
git clone usernamr@host:/path/to/repository
```

# 工作流
1. 你的本地仓库由git维护的三颗“树”组成。第一个是你的《工作目录》，它持有实际文件；第二个是《缓存区（Index）》，它像个缓存区域，临时保存你的改动；最后是《HEAD》，指向你最近一次提交后的结果。
![工作流][/workflow.png]

# 添加与提交
1. 你可以计划改动（把它们添加到缓存区），使用如下命令：```

