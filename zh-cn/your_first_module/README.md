这是一个入门章节，如果你已经对 node.js 或者 cortex 有一定的熟悉，可以跳过它。

# 你的第一个模块

接下来，我们来一起创造一个名为 `'colorify'` 的模块。它的作用很简单：

> 给特定的元素设置指定的颜色

在我们写代码之前，我们还有一些准备工作需要完成：

### 安装 Node.js

访问 [nodejs 的官方网站](http://nodejs.org/), 下载并安装最新版本。我们最少需要安装 node 0.10.0.

### 安装 Cortex

借助 npm（node package manager，大多数情况，它会由 node 自带），安装 cortex 很简单，只需要在你的命令行终端中运行（不要包含 `$`）：

```sh
# 根据实际情况，有可能你需要使用 sudo
$ npm install -g cortex
```

当安装完成后，运行如下命令：

```sh
$ cortex
```

如果能够看到 cortex 的帮助信息，则表示安装成功了 ~


