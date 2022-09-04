# Go十大常见错误第8篇：Context管理

## 前言

这是Go十大常见错误系列的第8篇：Context管理。素材来源于Go布道者，现Docker公司资深工程师[Teiva Harsanyi](https://teivah.medium.com/)。

本文涉及的源代码全部开源在：[Go十大常见错误源代码](https://github.com/jincheng9/go-tutorial/tree/main/workspace/senior/p28)，欢迎大家关注公众号，及时获取本系列最新更新。



## Context是什么

Go语言里的[context.Context](https://pkg.go.dev/context)包非常有用，但是也经常被开发者误解。

官方对Context的表述是：

> Package context defines the Context type, which carries deadlines, cancellation signals, and other request-scoped values across API boundaries and between processes.

光看这段描述，还是很容易让人迷糊的，我们接下来具体看看Context到底是什么以及可以帮助我们做什么事情。

```go
// A Context carries a deadline, cancellation signal, and request-scoped values
// across API boundaries. Its methods are safe for simultaneous use by multiple
// goroutines.
type Context interface {
    // Done returns a channel that is closed when this Context is canceled
    // or times out.
    Done() <-chan struct{}

    // Err indicates why this context was canceled, after the Done channel
    // is closed.
    Err() error

    // Deadline returns the time when this Context will be canceled, if any.
    Deadline() (deadline time.Time, ok bool)

    // Value returns the value associated with key or nil if none.
    Value(key interface{}) interface{}
}
```



总结起来，Context有3个能力，

- 超时控制。 通过`context.WithTimeout`函数和`context.WithDeadline`函数可以创建一个有超时时间的Context。

  ```go
  func WithTimeout(parent Context, timeout time.Duration) (Context, CancelFunc)
  func WithDeadline(parent Context, d time.Time) (Context, CancelFunc)
  ```

  

- 取消信号。通过`context.WithCancel`函数可以创建一个可以发出主动cancel信号的Context。

  ```go
  func WithCancel(parent Context) (ctx Context, cancel CancelFunc)
  ```

  

- 附加值。通过Context的`WithValue`函数可以给Context添加附加值。其中key和value都是空接口类型(`interface{}`)。

  ```go
  func WithValue(parent Context, key, val any) Context
  ```

  通过Context的

有2点要补充：

* 第一，Context是可以组合的。比如，我们可以通过`context.WithTimeout`创建一个有超时时间的Context，同时调用Context里的`WithValue`给这个`Context`添加一些附加值。
* 第二，多个goroutine可以共享同一个Context，因此一个取消信号可以停止多个goroutine。



## 常见错误

Coming back to our topic, here is a concrete mistake I’ve seen.

A Go application was based on [*urfave/cli*](https://github.com/urfave/cli) (if you don’t know it, that’s a nice library to create command-line applications in Go). Once started, the developer *inherits* from a sort of application context. It means when the application is stopped, the library will use this context to send a cancellation signal.

What I experienced is that this very context was directly passed while calling a gRPC endpoint for example. This is **not** what we want to do.

Instead, we want to indicate to the gRPC library: *Please cancel the request either when the application is being stopped or after 100 ms for example.*

To achieve this, we can simply create a composed context. If `parent` is the name of the application context (created by *urfave/cli*), then we can simply do this:

```go
ctx, cancel := context.WithTimeout(parent, 100 * time.Millisecond)
response, err := grpcClient.Send(ctx, request)
```

Contexts are not that complex to understand and it is one of the best feature of the language in my opinion.



## 推荐阅读

* [Go十大常见错误第1篇：未知枚举值](https://mp.weixin.qq.com/s?__biz=Mzg2MTcwNjc1Mg==&mid=2247484146&idx=1&sn=10fb12b643a2e37c090e5aa3bc583152&chksm=ce124d9df965c48bb954aeddabdff3db12738ded3875542250c5d0ef6cfd4417fc56580288b1&token=1912894792&lang=zh_CN#rd)

* [Go十大常见错误第2篇：benchmark性能测试的坑](https://mp.weixin.qq.com/s?__biz=Mzg2MTcwNjc1Mg==&mid=2247484163&idx=1&sn=b28d61c1f3ec9d914e698dce105ba5d1&chksm=ce124c6cf965c57a90bc85a5295ed9375103de20607b509f845583ff6686385df0ed96653d00&token=1912894792&lang=zh_CN#rd)

* [Go十大常见错误第3篇：go指针的性能问题和内存逃逸](https://mp.weixin.qq.com/s?__biz=Mzg2MTcwNjc1Mg==&mid=2247484247&idx=1&sn=faf716627afb00df646cecff023fb63c&chksm=ce124c38f965c52efd009a4c98691d56b5765dc7dce98aa49b226ad9274bd062d8d01e702e91&token=1899277735&lang=zh_CN#rd)

* [Go十大常见错误第4篇：break操作的注意事项](https://mp.weixin.qq.com/s?__biz=Mzg2MTcwNjc1Mg==&mid=2247484262&idx=1&sn=c1bea8af60444a4ef73c4d4d7a09d16d&chksm=ce124c09f965c51f3663ac9089a792d36c3685850e12695dd26d15a1a50f393b2d7c92b9983a&token=461369035&lang=zh_CN#rd)

* [Go十大常见错误第5篇：Go语言Error管理](https://mp.weixin.qq.com/s?__biz=Mzg2MTcwNjc1Mg==&mid=2247484274&idx=1&sn=711abea3c6fd5d15341ee1b34da8a160&chksm=ce124c1df965c50b3af84965f7ed30b574cd0b247ea6f77b944ec858bd43ee37f4c1554a5bce&token=1846351524&lang=zh_CN#rd)

* [Go十大常见错误第6篇：slice初始化常犯的错误](https://mp.weixin.qq.com/s?__biz=Mzg2MTcwNjc1Mg==&mid=2247484289&idx=1&sn=2b8171458cde4425b28fdf8f51df8d7c&chksm=ce124ceef965c5f8a14f5951457ce2ac0ecc4612cf2013957f1d818b6e74da7c803b9df1d394&token=1477304797&lang=zh_CN#rd)

* [Go十大常见错误第7篇：不使用-race选项做并发竞争检测](https://mp.weixin.qq.com/s?__biz=Mzg2MTcwNjc1Mg==&mid=2247484299&idx=1&sn=583c3470a76e93b0af0d5fc04fe29b55&chksm=ce124ce4f965c5f20de5887b113eab91f7c2654a941491a789e4ac53c298fbadb4367acee9bb&token=1918756920&lang=zh_CN#rd)

* [Go面试题系列，看看你会几题？](https://mp.weixin.qq.com/mp/appmsgalbum?__biz=Mzg2MTcwNjc1Mg==&action=getalbum&album_id=2199553588283179010#wechat_redirect)

  

## 开源地址

文章和示例代码开源在GitHub: [Go语言初级、中级和高级教程](https://github.com/jincheng9/go-tutorial)。

公众号：coding进阶。关注公众号可以获取最新Go面试题和技术栈。

个人网站：[Jincheng's Blog](https://jincheng9.github.io/)。

知乎：[无忌](https://www.zhihu.com/people/thucuhkwuji)。



## 福利

我为大家整理了一份后端开发学习资料礼包，包含编程语言入门到进阶知识(Go、C++、Python)、后端开发技术栈、面试题等。

关注公众号「coding进阶」，发送消息 **backend** 领取资料礼包，这份资料会不定期更新，加入我觉得有价值的资料。还可以发送消息「**进群**」，和同行一起交流学习，答疑解惑。



## References

* https://itnext.io/the-top-10-most-common-mistakes-ive-seen-in-go-projects-4b79d4f6cd65
* https://pkg.go.dev/context
* https://go.dev/blog/context
* https://mp.weixin.qq.com/s/PoXSEDHRyKCyjibFGS0wHw
* https://www.digitalocean.com/community/tutorials/how-to-use-contexts-in-go