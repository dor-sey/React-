# Hello World
## 1. 设置
> 访问[http://reactjs.com](http://reactjs.com)获取React源代码。

## 2. Hello React World

> 首先编写一个页面
```
<html>
    <body>
        <div id="app">
            <!--应用渲染位置-->
        </div>
        <script src="react/build/react.js"></script>
        <script src="react/build/react-dom.js"></script>
    </body>
</html>
```
> 添加一段输出Hello Word!代码
```
<script>
    ReactDOM.render(
        React.DOM.h1(null, "Hello World!"),
        document.getElementById("app")
    );
</script>
```
> 在chrome开发者工具可以看到会添加```<h1 data-reactid=".0">Hello World!</h1>```

## 3. 发生了什么

> 使用ReactDOM对象的h1组件，可以通过React.DOM.h1()方法调用，然后调用document.getElementById("app")方法访问，告诉React把组件渲染到页面哪个部分。

## 4. React.DOM.*

> 可以通过React.DOM对象把各种HTML元素当做React组件来使用。

> React.DOM.*接收参数：
>> 首个参数接受一个对象，用于指定该组件的任何属性（比如DOM属性）。例如给组件传递id属性：
```
React.DOM.h1(
    {
        id: "my-heading",
    },
    "Hello World!"
)
```
>> 第二个参数定义该组件的子元素，可以传递更多函数进行子元素的组合和套用。
```
React.DOM.h1(
    {
        id: "my-heading"
    },
    React.DOM.span(null,
        React.DOM.em(null, "Hell"),
        " World!"
    )
)
```

> 为了简化组件的嵌套使用，React提供了JSX语法
```
React.DOM.render(
    <h1 id="my-heading">
        <span><em>Hell</em>o</span> World!
    </h1>,
    document.getElementById("app")
)
```
## 5. 特殊DOM属性

> 下列几个DOM属性比较特殊，需要注意：class、for 和 style。
>> class 和 for 不能在React中使用，因为它们是JavaScript的关键字。取而代之的是className 和 htmlFor。
```
React.DOM.h1(
    {
        className: "pretty",
        htmlFor: "me"
    },
    "Hello World!"
)
```
>> style属性，不能像以前在HTML中那样使用字符串赋值，需要使用JavaScript对象取而代之。
```
React.DOM.h1(
    {
        style: {
            background: "black",
            color: "white"
        }
    },
    "Hello World!"
)
```
## 6. React DevTools 浏览器扩展
> 可以安装React DevTools浏览器扩展来调试。