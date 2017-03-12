## 模块的几种规范
### 1.<script>标签引入
...这个是最普通的引入，不多说。
### 2.CommonJs
```
require("module");
require("../file_1.js");
exports.func1 = function () {};
module.exports = someThing;
```
通过 require 来加载依赖的其他模块。之后通过 exports 或者 module.exports 导出需要暴露的接口。
### 3.AMD
```
define("module", ["dep1", "dep2"], function (d1,d2) {
	return someExport;
});

require(["module", "../file"], function (module, file) {});
```
声明模块时先指定依赖，之后将依赖模块当做参数传进去。最后将需要用到的模块return出来。
以前用过RequireJS，就是AMD标准的。
### 4.CMD
```
define(function(require, exports, module) {
	var $ = require('jquery');
	var vue = require('./vue');
	exports.doSomething = function () {};
	module.exports = ...;
})
```
Sea.js使用这个标准。