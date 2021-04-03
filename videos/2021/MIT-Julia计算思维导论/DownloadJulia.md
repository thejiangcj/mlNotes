## 下载Julia

简介：本文描述如何下载安装Julia和配置课程环境

---

### Step 1: 下载安装 Julia 1.6.0

到网站 [https://julialang.org/downloads](https://julialang.org/downloads) ，下载当前最新版本的Julia 1.6.0

---

### Step 2: 运行 Julia

打开Julia终端，运行 1+1 即可

---

### Step 3: 下载 `Pluto` 笔记本

为了运行课程中的代码，因此需要下载相应软件进行运行

首先，我们打开 Julia 终端，首先输入  `]`，从 Julia 模式转换到 PKG 模式，以便下载安装相应的包，这个模式运行你运行 **packages**，也叫 **libraries**。

运行以下命令：

```julia
(@v1.6) pkg> add Pluto
```

### Step 4: 运行 `Pluto`

运行以下命令：

```julia
julia> using Pluto 
julia> Pluto.run()
```

---

### Q 1: 端口配置问题

由于个人之前配置过 Git 端口号，并用 Trojan 梯子，因此发生如下报错

![Git配置问题](imgs/Pasted%20image%2020210402183003.png)

最后参考 [Q1](https://stackoverflow.com/questions/62772802/julia-1-4-cant-install-any-packages-due-to-unrecognized-url-prefix) 用以下方式解决：

1. 在 Git 处配置 http 端口为：

```python
git config --global http.proxy http://127.0.0.1:http_port_number
git config --global https.proxy http://127.0.0.1:http_port_number
```

2. 以上若不能解决再在 Julia 安装路径下找到 `/julia-1.6.0/etc/julia/startup.jl`，添加即可解决:

```shell
ENV["HTTP_PROXY"] = "http://127.0.0.1:http_port_number"
ENV["HTTPS_PROXY"] = "http://127.0.0.1:http_port_number"
```






