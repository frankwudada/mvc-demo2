# 实现思路
1、将代码封装成三个模块，分别为数据模块、视图模块和控制器模块，即 MVC。数据模块将数据放到一个对象里面，视图模块将视图相关放到一个对象里面，
控制器模块主要是对 DOM 进行监听并执行相关操作。MVC 的英文分别 `Models、View、Conttroller`。

2、代码中使用了 `const eventBus = $(window)` ，该方法主要是为了使用 jQuery 的 trigger 方法和 on 方法，从而使两个对象之间可以通信。
trigger 方法的作用是触发一个事件，使得该事件可以被 on 方法监听到。如 `xxx.trigger("eventName")` 中的 eventName 事件可以被 `yyy.on("eventName")` 监听到。

3、MVC 模块使用 `export default c` 导出，然后在 main.js 文件中使用 `import c from "xxx.js"` 方法导入，并初始化 `c.init("#id")`。

4、MVC 三个模块的代码还可以继续简化成一个或者两个，做到极限就类似于 vue 和 reate 框架。

5、整体实现思路：初始渲染 -- 动态监听 DOM -- 对数据进行增删改查，并体现到 HTML 上 -- 再次渲染
