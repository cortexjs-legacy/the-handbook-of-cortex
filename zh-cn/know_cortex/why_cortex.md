# Cortex 的优势

> 我们做的不是玩具.

## 胜任企业级应用的高要求

作为包管理器的先行者，cortex 已经在生产环境使用了一年半的时间。

目前大众点评所有的移动站点及混合应用都由 cortex 提供动力。Cortex 帮助不同团队，甚至是不同事业部的工程师一起更好地协作，并且消除代码互相冲突的担忧。

Cortex 将不同的 JavaScript 模块在完全隔离的沙箱中运行，从而避免各种不良影响的发生。

另外对于企业级应用，我们有着完整的持续集成方案，适应频繁的发布，多测试环境的部署，灰度发布等疑难问题的考验。

## 精确的版本控制体系

Cortex 有着业界领先的版本控制方案，能够做到：

- 让同一个模块的不同版本在运行时共存（如果你是 Java 工程师，也许能够理解版本仲裁带来的项目升级的各种问题）
- 基于有向图算法，支持几乎一切版本依赖场景。
- 完全的 [语义化版本](http://semver.org/lang/zh-CN/) 和 语义化版本范围 的支持。
- 开发过程中不需要修改代码、升级大量模块来更新依赖
- 线上应用版本及依赖固化，对于要求高可用的业务，一旦测试通过，则能够防止任何第三方更新对线上应用造成不良影响。

## Node 开发者天生会使用的浏览器端包管理器

如果你平时熟悉使用 npm 来进行 nodejs 的包管理，祝贺你，你已经知道如何使用 cortex 来开发浏览器端代码啦。

## 忘记 *MD 吧

> 只做必要的事情
>
> 用 node 的书写风格来写代码吧

完全使用 nodejs 的风格来书写代码, 使用你最熟悉的 `require`, `exports`, `module.exports` 来构建模块。忘记每天需要重复手写的 AMD，CMD，UMD 等等。

Cortex 支持跟 nodejs 一样来引用目录，比如：

```js
var foo = require('./dir/');
```

同时支持 `__dirname`, `__filename`, `require.resolve()`，并且实现了 [nodejs 的模块系统](http://nodejs.org/api/modules.html)。

## Cortex 是包管理器，而不仅仅是脚本加载器

- Not only download files, but also connect them and make them working together.
- Handle assets and you need not to write `<script>` tags for most of time.
- A package is a self-contained unit which is not just javascripts, it also contains css, images, fonts, and .etc.

## 模块云服务

* A registry cloud only for browsers. All the packages work in browsers, no ambiguity.
* Most of time, the intersection of server-side packages and browser-side packages is little and at low level. We need a better ecosystem to make it larger.
* Additional yet useful features are provided: package tagging, watching a project’s updates, and etc.

## 专业、专注的开发团队

> 给老外提个 pull request 几个月才合并？
>
> 提交的问题杳无音讯？

你不用担心这些问题！由于 cortex 是无数工程师每天使用，并且在生产环境运行的项目，我们对任何 Bugs 非常看重，会将其视为非常高的优先级来处理。

另外，Cortex 由一个全职的团队维护，因此我们不用担心某一个开发者 say farewell =。=

它不会受到外界的影响，一直活下去。

