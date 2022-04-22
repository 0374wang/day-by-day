# requireJS #



https://juejin.cn/post/6844903592378236941









```
require(['moduleA', 'moduleB', 'moduleC'], function (moduleA, moduleB, moduleC){
　　　　// some code here
　　});
```

**require()函数接受两个参数。第一个参数是一个数组，表示所依赖的模块，**上例就是['moduleA', 'moduleB', 'moduleC']，即主模块依赖这三个模块；**第二个参数是一个回调函数，当前面指定的模块都加载成功后，它将被调用。**加载的模块会以参数形式传入该函数，从而在回调函数内部就可以使用这些模块。


require()异步加载moduleA，moduleB和moduleC，浏览器不会失去响应；它指定的回调函数，只有前面的模块都加载成功后，才会运行，解决了依赖性的问题。

假定主模块依赖jquery、underscore和backbone这三个模块，main.js就可以这样写：

```
require(['jquery', 'underscore', 'backbone'], function ($, _, Backbone){
　　　　// some code here
});
```

require.js会先加载jQuery、underscore和backbone，然后再运行回调函数。主模块的代码就写在回调函数中。

