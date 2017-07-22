# 如何Debug

浏览器环境下的javascript, 实际上有两个天生缺陷：

1. 不严谨. 不同浏览器的js实现上会略有不同. 这个问题在android, ios上也一样.
2. 不是严格意义上的计算编程语言. 有语法漏洞. 例如 ==

所以, 我们要驾驭好JS语言,就要知道如何有效的Debug.

## developer tools

无论是 chrome, safari 还是firefox, 以及  IE 7+ , 都带有这个工具. 特别好用. 任何时候
页面空白了,都要首先看它, 而不是问别人: "页面怎么不动了?"

## 时刻留意 vue server

我们开发时的命令:

```
$ npm run dev
```

会开启一个"开发服务器", 这个开发服务器的后台,我们要时刻留意输出.
有时候我们把代码写错了, 导致Vuejs无法编译, 前台就会一片空白, 还没有任何出错提示.

## 看developer tools 提出的日志

由于JS代码不是特别严谨, 所以给出的错误提示也都很概括.我们可以做个对比:

- JSP  错误可以精确到某行
- PHP  错误可以精确到某行
- Rails 错误可以精确到某行
- Vuejs, Angular, Titanium 等JS框架: 错误可以精确到 "某个文件".

这是由于, 所有的JS框架的表现层, 都是"框架怪胎", 是一种跟js语言环境妥协的代码.
出了问题很难定位到最底层的根源.

而 JSP, PHP, Rails ERB, 则是 "正常框架", 出了问题可以直接找到最底层.

所以,我们要有一定的经验来Debug. 来理解错误日志.