# Git学习笔记

> —康思晟

***

## 🧭学习背景

优秀的程序员不仅能写出好代码，更能让自己的代码可追踪、可回溯、可维护

***

## ✨学习内容的目录
- 一、Git 是什么？
- 二、安装与配置
- 三、常用命令
- 四、Git 工作流程
- 五、分支管理
- 六、远程仓库操作
- 七、查看历史与回退版本

***

## 💾学习内容

### 🧩 一、Git 是什么？

**Git** 是一个分布式版本控制系统，用于记录文件的变化、协作开发、管理项目历史。

简单理解：
- 📜 记录文件的每一次修改；
- 🔙 随时回到任意历史版本；
- 👥 多人协作时自动合并修改。

---

### ⚙️ 二、安装与配置

#### 1. 安装
前往 [Git 官网](https://git-scm.com/) 下载并安装。

安装完成后，验证是否成功：

git --version  

#### 2. 配置用户信息

设置你的用户名和邮箱（用于提交记录）：

git config --global user.name "你的名字"
git config --global user.email "你的邮箱@example.com"

### 🗂️ 三、常用命令
> git init                 # 初始化仓库
git clone <url>          # 克隆仓库
git add .                # 添加所有文件
git commit -m "msg"      # 提交更改
git status               # 查看状态
git log --oneline        # 简洁查看历史
git branch               # 查看分支
git checkout -b dev      # 创建并切换分支
git merge dev            # 合并分支
git push origin main     # 推送到远程
git pull origin main     # 拉取远程更新

### 🧾 四、Git 工作流程

> 工作区 (Working Directory)  
     ↓ git add  
暂存区 (Staging Area)  
     ↓ git commit  
本地仓库 (Local Repository)  
     ↓ git push  
远程仓库 (Remote Repository)  

### 🌳 五、分支管理
- 创建与切换
git branch feature-x
git checkout feature-x

- 合并与删除
git checkout main
git merge feature-x
git branch -d feature-x

### 🧰 六、远程仓库操作
- 添加远程仓库
git remote add origin 仓库地址

- 推送到远程
git push -u origin main

- 拉取更新
git pull origin main

### 🕵️ 七、查看历史与回退版本
- 查看提交记录
git log --oneline

- 回退到上一个版本
git reset --hard HEAD~1

- 回退到指定提交
git reset --hard 提交ID

***

## 🚀参考资料

1. [廖雪峰](https://liaoxuefeng.com/books/git/introduction/index.html)
2. [图示逻辑](https://my-note-drawing-bed-1322822796.cos.ap-shanghai.myqcloud.com/picture/202405192337199.png)
3. [bilibili教程](https://www.bilibili.com/video/BV1Vh1PBmEEk/?spm_id_from=333.1007.top_right_bar_window_history.content.click&vd_source=fa477bfbb6c95eecbe18a26a8bebf61e)
