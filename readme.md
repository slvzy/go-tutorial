# Learning notes for golang

如果发现了本项目里的问题或者想了解本项目里还没涉及到的go语言技术栈，欢迎提交[issue](https://github.com/jincheng9/go-tutorial/issues/new)。

如果觉得本项目不错，欢迎给个**Star**。

## 基础篇

* [lesson0: GitHub最流行的golang-cheat-sheet中文版本](https://github.com/jincheng9/golang-cheat-sheet-cn)

* [lesson1: Go程序结构](./workspace/lesson1)

* [lesson2: 数据类型：数字，字符串，bool](./workspace/lesson2)

* [lesson3: 变量类型定义：全局变量，局部变量，多变量，零值](./workspace/lesson3)

* [lesson4: 常量和枚举](./workspace/lesson4)

* [lesson5: 运算操作符](./workspace/lesson5)

* [lesson6: 控制语句if/switch](./workspace/lesson6)

* [lesson7: 循环语句for/goto/break/continue](./workspace/lesson7)

* [lesson8: 函数，闭包和方法](./workspace/lesson8)

* [lesson9: 变量作用域](./workspace/lesson9)

* [lesson10: 数组：一维数组和多维数组](./workspace/lesson10)

* [lesson11: 指针pointer](./workspace/lesson11)

* [lesson12: 结构体struct](./workspace/lesson12)

* [lesson13: 切片Slice](./workspace/lesson13)

* [lesson14: range迭代](./workspace/lesson14)

* [lesson15: map集合](./workspace/lesson15)

* [lesson16: 递归函数](./workspace/lesson16)

* [lesson17: 类型转换](./workspace/lesson17)

* [lesson18: 接口interface](./workspace/lesson18)

* [lesson19: 协程goroutine和管道channel](./workspace/lesson19)

* [lesson20: defer语义](./workspace/lesson20)

* [lesson21: 并发编程之sync.WaitGroup](./workspace/lesson21)

* [lesson22:  并发编程之sync.Once](./workspace/lesson22)

* [lesson23:  并发编程之sync.Mutex和sync.RWMutex](./workspace/lesson23)

* [lesson24: 并发编程之sync.Cond](./workspace/lesson24)

* [lesson25: 并发编程之sync.Map](./workspace/lesson25)

* [lesson26: 并发编程之原子操作sync/atomic](./workspace/lesson26)

* [lesson27: 包Package和模块Module](./workspace/lesson27)

* [lesson28: panic, recover运行期错误处理](./workspace/lesson28)

* [lesson29: select语义](./workspace/lesson29)

* [lesson30: go单元测试](./workspace/lesson30)

* [lesson31: go性能测试](./workspace/lesson31)

* [lesson32: go模糊测试](./workspace/senior/p22)

  


## 进阶篇

* 常用关键字

  * [被defer的函数一定会执行么？](./workspace/senior/p2)
  * [new和make的使用区别和最佳实践是什么？](./workspace/senior/p4)
  * [receive-only channel和send-only channel的争议](./workspace/senior/p30)
* 语言基础
  * [Go有引用变量和引用传递么？map,channel和slice作为函数参数是引用传递么？](./workspace/senior/p3)
  * [一文读懂Go匿名结构体的使用场景](./workspace/senior/p5)
  * [Go语言中fmt.Println(true)的结果一定是true么？](./workspace/senior/p19)
  * [Go语言中命名函数参数和命名函数返回值的注意事项](./workspace/senior/p21)
* 并发编程
  * [Go语言中Context并发模式](./workspace/senior/p31/01-go-context.md)
* 泛型
  * [泛型：Go泛型入门官方教程](./workspace/senior/p6)
  * [泛型：一文读懂Go泛型设计和使用场景](./workspace/senior/p7)
  * [泛型：Go 1.18正式版本将从标准库中移除constraints包](./workspace/senior/p17)
  * [泛型：什么场景应该使用泛型](./workspace/official-blog/when-to-use-generics.md)
* Fuzzing
  * [Fuzzing: Go Fuzzing入门官方教程](./workspace/senior/p22)
  * [Fuzzing: 一文读懂Go Fuzzing使用和原理](./workspace/senior/p23)
* Workspace mode工作区模式
  * [Go 1.18：工作区模式workspace mode简介](./workspace/senior/p25)
  * [Go 1.18：工作区模式最佳实践](./workspace/official-blog/go1.18-workspace-best-practice.md)
* 语言规范
  * [Practical Go：如何写出更好维护的Go代码](https://github.com/jincheng9/practical-go-cn)
  * [Google的Go语言编码规范](./workspace/style/google.md)
* Go开发中的常见错误
  * [第1篇：go未知枚举值](./workspace/senior/p28/01-unknown-enum-value.md)
  * [第2篇：go benchmark性能测试的坑](./workspace/senior/p28/02-go-benchmark-inline.md)
  * [第3篇：go指针的性能问题和内存逃逸](./workspace/senior/p28/03-go-pointer.md)
  * [第4篇：for/switch和for/select做break操作退出的注意事项](./workspace/senior/p28/04-break-for-switch-select.md)
  * [第5篇：go语言Error管理](./workspace/senior/p28/05-go-error-management.md)
  * [第6篇：slice初始化常犯的错误](./workspace/senior/p28/06-go-slice-init.md)
  * [第7篇：不使用-race选项做并发竞争检测](./workspace/senior/p28/07-go-race-detector.md)
  * [第8篇：并发编程中Context使用常见错误](./workspace/senior/p28/08-go-context-management.md)
  * [第9篇：使用文件名称作为函数输入](./workspace/senior/p28/09-go-use-filename-as-input.md)
  * [第10篇：Goroutine和循环变量一起使用的坑](./workspace/senior/p28/10-go-goroutine-loop-var.md)
  * [第11篇：意外的变量遮蔽(variable shadowing)](./workspace/senior/p28/11-go-unintended-variable-shadowing.md)
  * [第12篇：冗余的嵌套代码](./workspace/senior/p28/12-go-unnecessary-nested-code.md)
  * [第13篇：init函数的常见错误和最佳实践](./workspace/senior/p28/13-go-package-init-function.md)
  * [第14篇：过度使用getter和setter方法](./workspace/senior/p28/14-go-overuse-getter-setter.md)
  * [第15篇：interface使用的常见错误和最佳实践](./workspace/senior/p28/15-go-interface-pollution.md)
  * [第16篇：any的常见错误和最佳实践](./workspace/senior/p28/16-any-keyword.md)
* 高性能Go
  * [一文读懂Go 1.20引入的PGO性能优化](./workspace/senior/p35)
  * [high performance go workshop](https://dave.cheney.net/high-performance-go-workshop/dotgo-paris.html)
  
* Go安全
  * [Go的全新安全漏洞检测工具govulncheck来了](./workspace/senior/p32/01-go-vulnerability-management.md)
* Go版本演进
  * [Go 1.19要来了，看看都有哪些变化：第1篇](./workspace/senior/p29/readme.md)
  * [Go 1.19要来了，看看都有哪些变化：第2篇](./workspace/senior/p29/readme2.md)
  * [Go 1.19要来了，看看都有哪些变化：第3篇](./workspace/senior/p29/readme3.md)
  * [Go 1.19要来了，看看都有哪些变化：第4篇](./workspace/senior/p29/readme4.md)
  * [Go 1.20要来了，看看都有哪些变化：第1篇](./workspace/senior/p33/readme.md)
  * [Go 1.20要来了，看看都有哪些变化：第2篇](./workspace/senior/p33/readme2.md)
  * [Go 1.20要来了，看看都有哪些变化：第3篇](./workspace/senior/p33/readme3.md)
  * [Go 1.20要来了，看看都有哪些变化：第4篇](./workspace/senior/p33/readme4.md)
  * [Go 1.21的2个语言变化](./workspace/senior/p34)




## Go Quiz

1. [Go Quiz: 从Go面试题看slice的底层原理和注意事项](./workspace/senior/p8)

2. [Go Quiz: 从Go面试题搞懂slice range遍历的坑](./workspace/senior/p13)

3. [Go Quiz: 从Go面试题看channel的注意事项](./workspace/senior/p9)

4. [Go Quiz: 从Go面试题看channel在select场景下的注意事项](./workspace/senior/p14)

5. [Go Quiz: 从Go面试题看分号规则和switch的注意事项](./workspace/senior/p10)

6. [Go Quiz: 从Go面试题看defer语义的底层原理和注意事项第1篇](./workspace/senior/p11)

7. [Go Quiz: 从Go面试题看defer的注意事项第2篇](./workspace/senior/p12)

8. [Go Quiz: 从Go面试题看defer的注意事项第3篇](./workspace/senior/p15)

9. [Go Quiz: Google工程师的Go语言题目](./workspace/senior/p16)

10. [Go Quiz: 从Go面试题看panic注意事项第1篇](./workspace/senior/p18)

10. [Go Quiz: 从Go面试题看recover注意事项第1篇](./workspace/senior/p18/readme2.md)

9. [Go Quiz: 从Go面试题看函数命名返回值的注意事项](./workspace/senior/p20)

9. [Go Quiz: 从Go面试题看锁的注意事项](./workspace/senior/p24)

9. [Go Quiz: 从Go面试题看变量的零值和初始化赋值的注意事项](./workspace/senior/p26)

9. [Go Quiz: 从Go面试题看数值类型的自动推导](./workspace/senior/p27)

12. [Go questions-golang.design](https://golang.design/go-questions/)

    

##  Go标准库

* [Go标准库脑图](./workspace/img/go-std-lib-mindmap.png)

* [Go标准库之log使用详解](./workspace/std/01)

* [Go标准库之cmd命令使用详解](./workspace/std/02)

  

## 实战篇

### 代码规范

* [Google的Go语言编码规范](./workspace/style/google.md)
* [Practical Go中文版本](https://github.com/jincheng9/practical-go-cn)
* [Go谚语 by  Rob Pike](https://go-proverbs.github.io/)

### Web框架

#### Gin

* [当前流行的Go web框架比较以及Gin介绍](./workspace/gin/01/)
* [Gin源码结构解析](./workspace/gin/02)

### RPC

#### gRPC

* [gRPC入门指引](./workspace/rpc/01)
* [gRPC-Go入门教程](./workspace/rpc/02)

### Databases

#### MySQL

* [Tutorial of go-sql-driver/mysql](./workspace/mysql/01/)

#### Redis

* [Tutorial of go-redis/redis](./workspace/redis/01/)

### Docker/K8s

* [Docker入门教程101: 用途，架构，安装和使用](https://github.com/jincheng9/disributed-system-notes/tree/main/docker/01)
* [Docker入门教程101: 基于Docker部署Go项目](https://github.com/jincheng9/disributed-system-notes/tree/main/docker/02)

### Document Tools

#### Swagger

* [gin-swagger常见问题](./workspace/swagger)

## CI/CD

- [Jenkins教程01：安装部署](./workspace/devops/jenkins01.md)

  

## 外文翻译

1. [GitHub最流行的golang-cheat-sheet中文版本](https://github.com/jincheng9/golang-cheat-sheet-cn)

1. [官方博文：Go开源13周年](./workspace/official-blog/13-years-of-go.md)

1. [官方博文：Go开发者调研方式改变了](./workspace/official-blog/survey-change.md)

1. [官方博文：什么场景应该使用泛型](./workspace/official-blog/when-to-use-generics.md)

1. [官方博文：Go工作区模式最佳实践](./workspace/official-blog/go1.18-workspace-best-practice.md)

1. [官方博文：Go 1.18发布啦！](./workspace/official-blog/go118_release.md)

1. [官方教程：Go fuzzing模糊测试](./workspace/senior/p22)

2. [官方教程：Go泛型入门](./workspace/senior/p6)

2. [官方博文：Go 1.18 Beta 2发布](./workspace/official-blog/go118_beta2.md)

2. [官方博文：Go官方推出了Go 1.18的2个新教程](./workspace/official-blog/go118_two_new_tutorial.md)

3. [官方博文：支持泛型的Go 1.18 Beta 1版本正式发布](./workspace/official-blog/go118beta1.md)

4. [官方博文：Go开源12周年](./workspace/official-blog/twelve-years-of-go.md)

   

## Go环境和工具

1. [GitHub上的项目go get连不上怎么办？](./workspace/senior/p1/)

2. [GoLand常用快捷键](./workspace/senior/p1/readme2.md)

2. [Mac的shell切换、环境变量设置以及软件安装问题](./workspace/senior/p1/readme3.md)

2. [Go testing缓存导致测试没执行的问题](./workspace/senior/p1/readme4.md)

2. [go install安装的不同Go版本的可执行程序和源码存放在哪里](./workspace/senior/p1/readme5.md)

2. [Mac系统查看Go开发相关的系统设置](./workspace/senior/p1/readme6.md)

   

## Go Book

* [The Go Programming Language-Go语言圣经](http://www.gopl.io/)
* [Go语言高级编程-chai2010.gitbooks.io](https://chai2010.gitbooks.io/advanced-go-programming-book/content/)
* [Go语言设计与实现-draveness.me](https://draveness.me/golang/)
* [Go设计模式-Tamer Tas@google](https://github.com/tmrts/go-patterns)
* [深入解析Go-tiancaiamao.gitbooks.io](https://tiancaiamao.gitbooks.io/go-internals/content/zh/)
* [码农桃花源-qcrao91.gitbook.io](https://qcrao91.gitbook.io/go/)
* [Go语言高性能编程-geektutu](https://geektutu.com/post/hpg-benchmark.html)
* [Go Under The Hood-golang.design](https://golang.design/under-the-hood/)
* [英文Go书籍list](https://github.com/dariubs/GoBooks)



## Go Blog

* [Jincheng's Blog](https://jincheng9.github.io/)
* [Russ Cox-Go团队负责人](https://research.swtch.com/)
* [Go Documentation](https://go.dev/doc/)
* [Golang GitHub Wiki](https://github.com/golang/go/wiki)
* [Go By Example](https://gobyexample.com/)
* [Golang By Example](https://golangbyexample.com/)
* [CS Professor Nilsson from KTH](https://yourbasic.org/golang/)
* [John Arundel](https://bitfieldconsulting.com/)
* [Dave Cheney](https://dave.cheney.net/)
* [Jaana Dogan-Pricipal Engineer at AWS](https://rakyll.org/about/)
* [go101.org](https://go101.org/article/101.html)
* [Valentin Deleplace-Google Engineer](https://medium.com/@val_deleplace)
* [Jay Conrod-Ex Google Go Team Member](https://jayconrod.com/posts)
* [Medium: A Journey with Go](https://medium.com/a-journey-with-go)
* [Teiva Harsanyi-100 Go Mistakes author](https://teivah.github.io/)
* [Carl M. Johnson.net-Tech Director of Spotlight PA](https://carlmjohnson.net/)
* [Alex Edwards-A full stack Web Developer](https://www.alexedwards.net/blog)
* [golang.design](https://golang.design/)
* [Amit Saha-Atlassian Engineer](https://echorand.me/)
* [Paschalis Tsilias-Grafana Engineer](https://tpaschalis.github.io/)
* [liwenzhou-李文周](https://www.liwenzhou.com/)
* [TalkGo发起人-杨文](https://maiyang.me/)
* [smallest-rpcx作者](https://colobu.com/)
* [ChangkunOu-欧长坤](https://changkun.de/blog/)
* [chai2010-柴树杉](https://chai2010.cn/about/)
* [cch123-曹春晖](https://xargin.com/)
* [halfrost-Dezhi Yu](https://halfrost.com/)
* [draveness-左书祺](https://draveness.me/)
* [unknwon-无闻](https://unknwon.io/)
* [strikefreedom-Andy Pan](https://strikefreedom.top/)
* [qcrao-码农桃花源](https://qcrao.com/)
* [geektutu-极客兔兔](https://geektutu.com/)
* [topgoer.com](https://www.topgoer.com/)
* [topgoer.cn](https://topgoer.cn/)
* [涛叔-taoshu.in](https://taoshu.in/)
* [jianyu chen](https://eddycjy.com/)
* [Zhiyun Luo-Tencent IEG Developer](https://www.luozhiyun.com/)



## Go Video

### YouTube

* [Gopher Academy](https://www.youtube.com/@GopherAcademy)

* [GopherCon Talks Since 2014](https://www.youtube.com/c/GopherAcademy/videos)

* [GoLab Conference Since 2018](https://www.youtube.com/channel/UCMEvzoHTIdZI7IM8LoRbLsQ/featured)

* [Basics, Intermediate, Advanced Go Tutorials-Bitfield Consulting](https://www.youtube.com/c/BitfieldConsulting)

* [TutorialEdge Golang Development](https://www.youtube.com/watch?v=W5b64DXeP0o&list=PLzUGFf4GhXBL4GHXVcMMvzgtO8-WEJIoY)

  

## Go Community

* GoCN： https://github.com/gocn/opentalk
* Go夜读：https://github.com/talkgo/night



## Go News

* https://go.dev/blog/
* https://twitter.com/_rsc
* https://twitter.com/rob_pike
* https://twitter.com/golang
* https://twitter.com/golangweekly
* https://twitter.com/GolangTrends

