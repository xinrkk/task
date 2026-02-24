# README
> —康思晟

## 简介

本项目包含两个最简单的客户端/服务器（C/S）通信示例，分别基于 TCP Socket和 HTTP实现。目的是帮助初学者理解 Go 语言中网络编程的基本用法。

------

## 功能

1. TCP Socket 示例
   - 客户端发送消息给服务器
   - 服务器接收消息并打印，同时回复客户端
   - 客户端接收服务器回复并打印
2. HTTP 示例
   - 客户端通过 HTTP GET 请求服务器
   - 服务器返回文本响应
   - 客户端接收响应并打印

------

## 操作方法

### 1. TCP Socket 示例

1. 启动服务器：

```
go run server.go
```

1. 启动客户端（可在另一终端）：

```
go run client.go
```

1. 客户端发送消息给服务器，服务器打印收到的消息并回复，客户端接收回复并打印。

------

### 2. HTTP 示例

1. 启动 HTTP 服务器：

```
go run http_server.go
```

1. 启动客户端：

```
go run http_client.go
```

1. 客户端访问服务器，服务器打印请求信息并返回响应，客户端打印服务器返回内容。

------

## 使用的 Go 知识点

1. TCP Socket 示例
   - `net.Listen` 创建 TCP 服务器监听
   - `listener.Accept` 接收客户端连接
   - `conn.Read` / `conn.Write` 进行数据传输
   - `goroutine` 实现多连接处理
   - `defer` 确保资源关闭
2. HTTP 示例
   - `net/http` 包基础使用
   - `http.HandleFunc` 定义路由处理函数
   - `http.ListenAndServe` 启动 HTTP 服务器
   - `http.Get` 发送 GET 请求
   - `io.ReadAll` 读取响应内容