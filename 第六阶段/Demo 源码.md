# 基于 TCP Socket 的 C/S 通信 Demo

## 1️⃣ 服务端（server.go）

```
package main

import (
	"fmt"
	"net"
)

func main() {
	// 监听 TCP 端口
	listener, err := net.Listen("tcp", "localhost:8080")
	if err != nil {
		fmt.Println("监听失败:", err)
		return
	}
	defer listener.Close()

	fmt.Println("服务器已启动，等待客户端连接...")

	for {
		conn, err := listener.Accept()
		if err != nil {
			fmt.Println("连接失败:", err)
			continue
		}

		// 开启 goroutine 处理连接
		go handleConnection(conn)
	}
}

func handleConnection(conn net.Conn) {
	defer conn.Close()

	// 读取客户端数据
	buffer := make([]byte, 1024)
	n, err := conn.Read(buffer)
	if err != nil {
		fmt.Println("读取失败:", err)
		return
	}

	clientMsg := string(buffer[:n])
	fmt.Println("收到客户端消息:", clientMsg)

	// 回复客户端
	response := "你好，客户端！"
	conn.Write([]byte(response))
}
```

------

## 2️⃣ 客户端（client.go）

```
package main

import (
	"fmt"
	"net"
)

func main() {
	// 连接服务器
	conn, err := net.Dial("tcp", "localhost:8080")
	if err != nil {
		fmt.Println("连接服务器失败:", err)
		return
	}
	defer conn.Close()

	// 发送数据
	message := "你好，服务器！"
	conn.Write([]byte(message))

	// 接收服务器响应
	buffer := make([]byte, 1024)
	n, err := conn.Read(buffer)
	if err != nil {
		fmt.Println("读取失败:", err)
		return
	}

	fmt.Println("服务器回复:", string(buffer[:n]))
}
```
# 基于 net/http 的 C/S 通信 Demo

## 1️⃣ HTTP 服务端（http_server.go）

```
package main

import (
	"fmt"
	"net/http"
)

func helloHandler(w http.ResponseWriter, r *http.Request) {
	fmt.Println("收到客户端请求")

	w.Write([]byte("Hello, Client!"))
}

func main() {
	http.HandleFunc("/hello", helloHandler)

	fmt.Println("HTTP 服务器启动，监听 :8081")
	http.ListenAndServe(":8081", nil)
}
```

------

## 2️⃣ HTTP 客户端（http_client.go）

```
package main

import (
	"fmt"
	"io"
	"net/http"
)

func main() {
	resp, err := http.Get("http://localhost:8081/hello")
	if err != nil {
		fmt.Println("请求失败:", err)
		return
	}
	defer resp.Body.Close()

	body, _ := io.ReadAll(resp.Body)
	fmt.Println("服务器返回:", string(body))
```
