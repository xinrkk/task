# Go 程序源码（main.go）

```
package main

import (
	"fmt"
)

func main() {
	var choice int
	var a, b float64

	for {
		fmt.Println("====== 简易计算器 ======")
		fmt.Println("1. 加法")
		fmt.Println("2. 减法")
		fmt.Println("3. 乘法")
		fmt.Println("4. 除法")
		fmt.Println("5. 退出")
		fmt.Print("请选择操作：")
		fmt.Scanln(&choice)

		if choice == 5 {
			fmt.Println("程序已退出。")
			break
		}

		if choice < 1 || choice > 5 {
			fmt.Println("输入无效，请重新选择。")
			fmt.Println()
			continue
		}

		fmt.Print("请输入第一个数字：")
		fmt.Scanln(&a)
		fmt.Print("请输入第二个数字：")
		fmt.Scanln(&b)

		switch choice {
		case 1:
			fmt.Printf("结果：%.2f\n", a+b)
		case 2:
			fmt.Printf("结果：%.2f\n", a-b)
		case 3:
			fmt.Printf("结果：%.2f\n", a*b)
		case 4:
			if b == 0 {
				fmt.Println("错误：除数不能为 0！")
			} else {
				fmt.Printf("结果：%.2f\n", a/b)
			}
		}

		fmt.Println()
	}
}
```