# 和 Node 一样写代码

下面，我们要开始动手做啦。

## 1. 项目初始化

首先，我们创建一个名为`'colorify'` 的目录，并且在该目录中运行 `cortex init`

```sh
mkdir colorify
cd colorify
cortex init
```

Cortex 会询问你一系列的问题，用于创建当前项目必要的内容，大部分的情况下，我们可以使用默认的值。

如果一切顺利，我们会发现 cortex 已经创建好了基本的脚手架:

```
colorify/
|-- test/              // 测试用例目录
|      |-- colorify.js
|-- cortex.json
|-- index.html         // 一个配置好的页面环境
|-- index.js           // 模块的默认主入口
```

cortex.json 与 npm 的 package.json 很类似，用来描述包当前包的所有信息以及依赖的情况。

index.html 是脚手架中我们默认配置好的 html 文件，它是一个最简单示例，包含最基本的配置。

## 2. 安装依赖

我们希望能够去修改某一个元素的背景颜色，我们可以用 jquery 来帮助我们操作 DOM。

实际上，我们这里可以直接写原生的 JavaScript 代码来完成这个工作。但这里我们只是想通过这个示例，来说明如何来安装、声明依赖。

安装 jquery，我们只需要在命令行中输入：

```sh
cortex install jquery --save
```

Cortex 会将所有的依赖，安装到当前项目根目录的 `neurons` 文件夹。如果你安装的依赖还包括更多深层的依赖，cortex 会递归地安装他们。

你可能在命令行中看到类似的输出：

```
installing jquery@*
   GET http://r.ctx.io/jquery 200
   GET http://r.ctx.io/jquery/-/jquery-1.9.1.tgz 200
write /path/to/colorify/neurons/jquery/1.9.1/jquery.js
```

## 3. `require`、`exports` 与 `module`

我们把每个 JavaScript 文件称作一个模块，在每个基于 cortex 编写的模块中，都有三个变量能够被访问，他们是

`require` 是一个方法，它接收一个模块名（类型为 `String`） 作为参数，并且返回这个模块的 API。
  - 若模块名是一个相对路径，则它指代的是相对于当前模块该路径上的某一个模块
  - 若模块名是仅仅有英文字母，短横线，，下划线，点，数字组成的，则它代表的是一个外部模块或者是包，比如我们前面安装的 `'jquery'`

`exports` 是一个对象，向这个对象上添加属性，则会增加当前模块 API 上的属性。

`module` 是一个对象，用来描述当前模块的一些信息。大多数情况下，我们通过给 `module.exports` 赋值，来直接定义当前模块的 API。


更多详细的内容，可以参见 [CommonJS Module/1.0](http://wiki.commonjs.org/wiki/Modules/1.0) 规范。


## 4. 正式动手写代码

现在 `jquery` 已经安装到你的项目中。我们可以在项目中，通过 `require` 方法，来调用安装好的模块。

```js
// 这里的 `$` 就是大家熟悉的 jquery
var $ = require('jquery');

function colorify(selector, color){
  $(selector).css('background-color', color);
}

// 我们通过 `module.exports` 来定义当前模块的 API
module.exports = colorify;
```

这样，我们的 `colorify` 就写好了。






