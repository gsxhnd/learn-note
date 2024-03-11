---
title: Golang从Int转换为十六进制
tags:
  - Golang
date: 2022/09/21 09:36
---

在Golang中，将整数转换为十六进制很容易。因为十六进制实际上只是一个Integer字头，你可以使用fmt.Sprintf()和%x或%X格式，向fmt包索取该整数的字符串表示。

```golang
package main

import (
	"fmt"
)

func main() {
	for i := 1; i < 20; i++ {
		h := fmt.Sprintf("0x%x", i)
		fmt.Println(h)
	}
}
```

转换回Int
```golang
package main

import (
	"fmt"
	"strconv"
)
	
var hex = []string{"1", "2", "3", "4", "5", "6", "7", "8", "9", "a", "b", "c", "d", "e", "f", "10", "11", "12", "13"}

func main() {
	for _, h := range hex {
		i, _ := strconv.ParseInt(h, 16, 64)
		fmt.Println(i)
	}
}
```