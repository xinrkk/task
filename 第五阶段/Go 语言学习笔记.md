# Go 语言学习笔记

---
> —康思晟


# 一、Go 语言初识

## 1. Go 前世今生

Go（又称 Golang）是由 Google 于 2007 年开始设计，2009 年正式开源发布的一门编译型语言。
主要设计者包括 Robert Griesemer、Rob Pike 和 Ken Thompson。

Go 语言目标是：
- 简洁
- 高效
- 原生支持并发
- 适合服务端开发

---

## 2. Go 主要应用场景

- Web 后端开发
- 微服务架构
- 分布式系统
- 云计算与容器生态
- DevOps 工具开发

---

## 3. Go 的执行原理

执行流程：

    main.go → go build → 可执行文件 → 操作系统运行

或直接：

    go run main.go

常用 go 命令：

| 命令        | 说明         |
| ----------- | ------------ |
| go run      | 编译并运行   |
| go build    | 编译生成文件 |
| go mod init | 初始化模块   |
| go mod tidy | 整理依赖     |
| go test     | 执行测试     |
| go env      | 查看环境变量 |

---

# 二、Go 开发环境准备

## 1. 安装 Linux 虚拟机

推荐：
- Ubuntu Server
- CentOS

安装 Go：

    sudo apt update
    sudo apt install golang-go

验证：

    go version

---

## 2. Remote-SSH 连接

### 方案一：内网穿透
- 使用 frp / ngrok
- 映射 SSH 端口
- 远程连接

### 方案二：NAT + 端口转发

    ssh user@127.0.0.1 -p 端口号

推荐在 Linux 环境中直接开发。

---

# 三、Go 基础语法（快速回顾）

## 1. 第一个程序

    package main
    
    import "fmt"
    
    func main() {
        fmt.Println("Hello Go")
    }

---

## 2. 变量

    var a int = 10
    var b = 20
    c := 30

---

## 3. 常量

    const PI = 3.14

---

## 4. 条件语句

    if a > 10 {
        fmt.Println("大于10")
    } else {
        fmt.Println("小于等于10")
    }

---

## 5. 循环

    for i := 0; i < 5; i++ {
        fmt.Println(i)
    }

---

## 6. 函数

    func add(a int, b int) int {
        return a + b
    }

多返回值：

    func divide(a, b int) (int, int) {
        return a / b, a % b
    }

---

## 7. 切片

    s := []int{1,2,3}
    s = append(s, 4)

---

## 8. map

    m := make(map[string]int)
    m["a"] = 1

---

## 9. 结构体

    type Person struct {
        Name string
        Age  int
    }

---

## 10. 并发

    go func() {
        fmt.Println("协程执行")
    }()

---

## 总结

学习重点：

1. 熟练 go 命令
2. 熟悉 Linux 开发环境
3. 理解 goroutine 与 channel
4. 多写服务端小项目