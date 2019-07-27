本人也是初学go语言，作为一个后端工程师，Beego作为公司go项目主要使用的后端框架，肯定也需要进行一番研究。



# Go配置🕐

### Go的安装🍕

win下：[Golang官网](https://golang.google.cn/) ，可能需要翻墙。

然后狂点下一步就ok了，默认安在c盘根目录



### Go编译器推荐🍔

推荐使用jetbrains家的Goland，[下载地址](https://www.jetbrains.com/go/)



### 三种环境变量的配置🍟

可以通过`go env`来查看go环境

```
set GOARCH=amd64
set GOBIN=
set GOCACHE=C:\Users\hexu0\AppData\Local\go-build
set GOEXE=.exe
set GOFLAGS=
set GOHOSTARCH=amd64
set GOHOSTOS=windows
set GOOS=windows
set GOPATH=E:\workspace\kbqa\go-path
set GOPROXY=
set GORACE=
set GOROOT=C:\Go
set GOTMPDIR=
set GOTOOLDIR=C:\Go\pkg\tool\windows_amd64
set GCCGO=gccgo
set CC=gcc
set CXX=g++
set CGO_ENABLED=1
set GOMOD=
set CGO_CFLAGS=-g -O2
set CGO_CPPFLAGS=
set CGO_CXXFLAGS=-g -O2
set CGO_FFLAGS=-g -O2
set CGO_LDFLAGS=-g -O2
set PKG_CONFIG=pkg-config
```

其中GOROOT、GOPATH、GOBIN这三种变量需要初学者手动配置。



#### `$GOROOT`

`go`的安装路径
当你安装好`go`之后其实这个就已经有了



#### `$path`

将`go`安装目录下的bin文件夹配置在path中
![](https://github.com/hexu0614/beego-induction/blob/master/img_resources/%E5%BE%AE%E4%BF%A1%E6%88%AA%E5%9B%BE_20190727114148.png)



#### `$GOPATH`

`GOPATH`：也就是项目所在目录。允许多个目录，当有多个目录时，请注意分隔符（win下为`;`）
`GOPATH`目录约定有三个子目录：

```
projectpath(GOPATH)
  |-- bin // golang编译可执行文件存放路径
  |-- pkg // golang编译包时，生成的.a文件存放路径
  └-- src // 源码路径。按照golang默认约定，go run，go install等命令的当前工作路径（即在 此路径下执行上述命令）。
```

<br />

<br />



# Beego框架安装🕑

以项目中`example`为例，新建`example`目录，将此目录配置到`GOPATH`环境变量下

`GOPATH=E:\workspace\beego-induction\example\;`

### 进入项目目录🌭

`cd E:\workspace\beego-induction\example\`：

### 框架源码下载🥓

其中-u是检查版本并下载，-v是显示下载过程。

执行指令`go get -u -v github.com/astaxie/beego`

### 框架工具包下载🍿

执行指令`go get -u -v github.com/beego/bee`



然后你就会发现在`example`目录下自动生成了`bin`、`pkg`和`src`三个文件夹，这就说明beego安装成功，如果没有生成，检查一下是不是`GOPATH`没有将该项目放在第一位。

<br />

<br />

# 新建Beego项目🕒

### 创建🥚

执行指令` bee new 项目名称`
例如：`bee new mybeego`
这条指令会在`GOPATH`路径下的`src`文件夹中创建go环境的初始配置。这里说明下虽然这条指令在根目录下执行指令也没啥问题，beego会自动寻找`GOPATH`去创建工程项目。但是我们最好在终端中先进入`GOPATH`再创建，这是考虑到可能会路径出错之类的问题

![](https://github.com/hexu0614/beego-induction/blob/master/img_resources/1564198395069.png)

看到上面的输出后，表示项目创建完成，然后你就可以在`src`文件夹下看到你的项目目录了。



### 运行🥞

进入项目目录，也就是刚才创建的`src`下的mybeego文件夹下，文件夹下应有个名为`main.go`的文件，这就是beego的启动文件，当前目录执行指令`bee run`。此时终端会打印日志并提示服务器已经开启。

![1564200542750](C:\Users\hexu0\AppData\Roaming\Typora\typora-user-images\1564200542750.png)

然后在浏览器中输入`127.0.0.1:8080`你就能看到beego的欢迎页了

![1564200626287](E:\workspace\beego-induction\img_resources\1564200626287.png)

