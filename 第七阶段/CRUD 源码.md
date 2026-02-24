## main.go


```
package main

import (
    "net/http"
    "strconv"

    "github.com/gin-gonic/gin"
    "gorm.io/driver/mysql"
    "gorm.io/gorm"
)

// User 模型
type User struct {
    ID    uint   `json:"id"`
    Name  string `json:"name"`
    Email string `json:"email"`
    Age   int    `json:"age"`
}

// 全局DB
var db *gorm.DB

func main() {
    // 连接数据库
    dsn := "root:123456@tcp(127.0.0.1:3306)/test?charset=utf8mb4&parseTime=True&loc=Local"
    var err error
    db, err = gorm.Open(mysql.Open(dsn), &gorm.Config{})
    if err != nil {
        panic("数据库连接失败: " + err.Error())
    }

    // 自动创建表
    db.AutoMigrate(&User{})

    // 创建路由
    r := gin.Default()

    // CRUD接口
    r.POST("/users", createUser)
    r.GET("/users", getUsers)
    r.GET("/users/:id", getUser)
    r.PUT("/users/:id", updateUser)
    r.DELETE("/users/:id", deleteUser)

    r.Run(":8080")
}

// 创建用户
func createUser(c *gin.Context) {
    var user User
    if err := c.ShouldBindJSON(&user); err != nil {
        c.JSON(400, gin.H{"error": err.Error()})
        return
    }
    db.Create(&user)
    c.JSON(200, user)
}

// 获取所有用户
func getUsers(c *gin.Context) {
    var users []User
    db.Find(&users)
    c.JSON(200, users)
}

// 获取单个用户
func getUser(c *gin.Context) {
    id := c.Param("id")
    var user User
    if err := db.First(&user, id).Error; err != nil {
        c.JSON(404, gin.H{"error": "用户不存在"})
        return
    }
    c.JSON(200, user)
}

// 更新用户
func updateUser(c *gin.Context) {
    id := c.Param("id")
    var user User
    if err := db.First(&user, id).Error; err != nil {
        c.JSON(404, gin.H{"error": "用户不存在"})
        return
    }
    
    var updateData User
    if err := c.ShouldBindJSON(&updateData); err != nil {
        c.JSON(400, gin.H{"error": err.Error()})
        return
    }
    
    db.Model(&user).Updates(updateData)
    c.JSON(200, user)
}

// 删除用户
func deleteUser(c *gin.Context) {
    id := c.Param("id")
    db.Delete(&User{}, id)
    c.JSON(200, gin.H{"message": "删除成功"})
}
```



## go.mod


```
module simple-crud

go 1.21

require (
    github.com/gin-gonic/gin v1.9.1
    gorm.io/driver/mysql v1.5.2
    gorm.io/gorm v1.25.5
)
```



## 使用步骤

1. **创建数据库**



```
CREATE DATABASE test;
```



1. **修改数据库密码**（把 `root:123456` 改成你的密码）
2. **运行**



```
go mod tidy
go run main.go
```



## 测试命令



```
# 创建
curl -X POST http://localhost:8080/users -H "Content-Type: application/json" -d '{"name":"张三","email":"zhang@test.com","age":18}'

# 查询所有
curl http://localhost:8080/users

# 查询单个
curl http://localhost:8080/users/1

# 更新
curl -X PUT http://localhost:8080/users/1 -H "Content-Type: application/json" -d '{"name":"李四"}'

# 删除
curl -X DELETE http://localhost:8080/users/1

```
