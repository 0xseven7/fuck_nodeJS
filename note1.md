深入浅出nodeJS笔记 --- 模块

模块是`nodejs`中最重要的机制. 只要接触过`nodejs`那肯定接触过模块. 模块的引入和定义都非常简单, 
>模块的作用就是将类聚的方法和变量等限定在私有的作用域中, 同时支持引入和导出功能已顺畅的链接上下游以来. 每个模块都有自己独立的空间, 他们互不相互干扰.
## 引入模块
```javascript
var http = require('http');
var math = require('math'); 
```
模块的引入就是使用`require()`方法, 将一个模块的`API`引入到上下文中.
那么为什么通过`require()`方法能引入模块呢
## 模块的定义
上下文提供了`exports`对象用于到处当前模块的方法或者变量, 并且他是唯一的导出出口. 在模块中还存在一个`module`对象, 此对象指向当前模块, `exports`就是`module`的一个属性.
```javascript
// 模块的定义
exports.add = function() {
var sum = 0;
var i = 0;
var args = arguments;
i = args.length;
while(i < l) {
sum += args[i++];
}
return sum;
}
```
```javascript
// 模块的引入
var math = require('math');
console.log(math.add(1, 2)); // 3
```
## 模块的标识
模块的标识就是传递给`require()`方法的参数, 他必须是符合驼峰命名的字符串, 或者以`.` `..`开头的相对路径, 或者是绝对路径.

