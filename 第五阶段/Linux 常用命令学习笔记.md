#  Linux 常用命令学习笔记

> —康思晟


## 一、目录与文件操作

### 1. `ls` - 列出目录内容
```bash
ls              # 列出当前目录文件
ls -l           # 以列表形式显示详细信息（权限、大小、修改时间）
ls -a           # 显示所有文件（包括隐藏文件，以.开头的）
```

### 2. `cd` - 切换目录
```bash
cd /home        # 进入 /home 目录
cd ..           # 返回上一级目录
cd ~            # 返回当前用户的家目录
cd -            # 返回刚才所在的目录
```

### 3. `pwd` - 显示当前路径
```bash
pwd             # 显示当前工作目录的绝对路径
```

### 4. `mkdir` - 创建目录
```bash
mkdir test      # 创建名为 test 的目录
mkdir -p a/b/c  # 创建多级目录（如果父目录不存在，自动创建）
```

### 5. `rm` - 删除文件或目录
```bash
rm file.txt     # 删除文件
rm -r test/     # 递归删除目录（删除文件夹时必须加 -r）
rm -f file.txt  # 强制删除（不提示确认）
```

### 6. `touch` - 创建空文件或更新文件时间戳
```bash
touch a.txt     # 创建一个名为 a.txt 的空文件
```

### 7. `cat` - 查看或拼接文件内容
```bash
cat a.txt       # 查看 a.txt 的文件内容
cat a.txt b.txt # 依次显示 a.txt 和 b.txt 的内容
```

---

## 二、权限与执行

### 1. `chmod` - 修改文件权限
```bash
chmod +x script.sh      # 给脚本添加可执行权限
chmod 755 file          # 设置权限：所有者可读写执行，组和其他用户可读执行
```
> 权限数字：7=读写执行(4+2+1)，5=读执行(4+1)

### 2. `sudo` - 以超级管理员身份执行
```bash
sudo apt update         # 以 root 权限执行更新命令
sudo -i                 # 切换到 root 用户
```

---

## 三、网络与端口

### 1. `ping` - 测试网络连通性
```bash
ping baidu.com          # 测试能否访问百度
ping -c 4 8.8.8.8       # 发送 4 个包后停止
```

### 2. `netstat` - 查看网络端口占用
```bash
netstat -tuln           # 查看所有监听的端口
netstat -anp | grep 80  # 查看 80 端口被哪个进程占用
```

---

## 四、进程与服务

### 1. `ps` - 查看进程
```bash
ps aux                  # 查看所有正在运行的进程
ps aux | grep nginx     # 查找 nginx 相关进程
```

### 2. `systemctl` - 管理系统服务
```bash
systemctl status nginx  # 查看 nginx 服务状态
systemctl start nginx   # 启动 nginx 服务
systemctl stop nginx    # 停止 nginx 服务
systemctl restart nginx # 重启 nginx 服务
systemctl enable nginx  # 设置开机自启
```

---
