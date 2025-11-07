# Git提交练习文档
> —康思晟
***

## hello.md推送流程
> git clone https://github.com/xinrkk/task.git
cd task
echo "# Hello 康思晟" > hello.md
git status
git add hello.md
git commit -m "add hello.md"
git push origin main
***
## 关于git bash的思考
- 我认为对初学者来说，git bash还是有一些麻烦的，命令行操作步骤多、容易出错
其他的推送方法
1. GitHub Desktop

- 图形化界面简单直观
- 一键提交、推送、拉取
2. VS Code 内置 Git

- 内置 Git，无需打开 Git Bash
- 直接可视化查看修改、暂存、提交
- 集成终端可执行命令
3. VS 内置 Git

- 内置 Git，无需打开 Git Bash
- 直接可视化查看修改、暂存、提交
- 集成终端可执行命令
***
## 关于版本回滚的思考
1. 撤销刚刚的提交（保留修改）

- 回退到上一个提交，但保留文件修改，可以重新 git commit

2. 撤销刚刚的提交（丢弃修改）

- 彻底回到上一个提交，修改也被清空

3. 已推送到远程，想回退

- 生成一个新的“撤销提交”，不会破坏提交历史（安全）

