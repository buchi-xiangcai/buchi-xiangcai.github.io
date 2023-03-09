# 

title: 'vue基础'
subtitle: ''
date: 2023-03-09T13:58:36+08:00
draft: false

tags: [slot][组件]
categories: [vue]

hiddenFromHomePage: false
hiddenFromSearch: false

featuredImage: ''
featuredImagePreview: ''

license: '<a rel="license external nofollow noopener noreffer" href="https://creativecommons.org/licenses/by-nc/4.0/" target="_blank">CC BY-NC 4.0</a>'
---
# 一、插槽Slot的基本使用（测试数据的作用域）

## 1.基本使用：组件的内容全部替换到插槽中

## 2.数据的作用域：父组件的数据也可以显示到子组件中

![img](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/fad5bf78-9fde-11ed-8f2f-5cea1d84200c.png)

# 二、具名插槽Slot的基本使用：

## 1.基本使用：

- 子组件：`<slot name="left"></slot>`
- 父组件：`<template v-slot:left> <button>`左边的按钮`</button> </template>`，
- 可以简写：`<template #left> <button>`左边的按钮`</button> </template>`

## 2.默认插槽名：

- 一个不带 name 的slot，会带有隐含的名字 default

## 3.动态插槽名：

- 目前我们使用的插槽名称都是固定的，比如 v-slot:left等等，我们可以通过 `v-slot:[dynamicSlotName]`方式动态绑定一个名称

![img](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/fb4c3846-9fde-11ed-8689-5cea1d84200c.png)

# 三、渲染作用域（作用域插槽的背景）

## 1.渲染作用域：

- 父级模板里的所有内容都是在父级作用域中编译的
- 子模板里的所有内容都是在子作用域中编译的

![在这里插入图片描述](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/fbaf79db-9fde-11ed-bffc-5cea1d84200c.png)

# 四、作用域插槽（父组件没法直接用子组件的数据，有渲染作用域）

## 1.作用：

父组件可以访问子组件的数据，并按照父组件期望的形式进行数据展示（子组件定义插槽）

## 2.简单理解：

作用域插槽就是子组件用$emit向父组件传递数据的另一种表现

- 父组件访问子组件的数据：
  - 父组件获取组件slot属性：`v-slot="slotProps"`，
  - 子组件将数据绑定到动态属性中：`<slot :item="item"></slot>`
- 按照父组件期望的形式进行数据展示：
  - 子组件中定义slot插槽：`<slot :item="item" :index="index"></slot>`
  - 父组件通过插槽的方式替换子组件的插槽内容

![img](https://blog-1305504063.cos.ap-beijing.myqcloud.com/fc2ec9de-9fde-11ed-91e5-5cea1d84200c.png)

# 五、动态组件

## 1.概念

动态组件是使用 `component` 组件，通过一个特殊的`attribute` `is` 来实现

## 2.基本用法：

## 3.`is`绑定的值是什么内容？

- 可以是通过`component函数注册的组件`
- 在一个组件对象的`components对象中注册的组件（局部组件）`

![在这里插入图片描述](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/fc9f1b3f-9fde-11ed-918d-5cea1d84200c.png)

# 六、动态组件传参

## 1.动态组件传参跟普通组件一样

区别：当前动态组件的 is 绑定哪个组件，参数就在哪个组件上

[![在这里插入图片描述](https://blog-1305504063.cos.ap-beijing.myqcloud.com/fcf58699-9fde-11ed-bdcd-5cea1d84200c.png)](https://blog-1305504063.cos.ap-beijing.myqcloud.com/fcf58699-9fde-11ed-bdcd-5cea1d84200c.png)

# 七、webpack代码（组件）分包

## 1.默认的打包过程

- 默认情况下，在构建整个组件树的过程中，因为组件和组件之间是通过模块化直接依赖的，那么webpack在打包时就会将组 件模块打包到一起（比如一个app.js文件中）
- 这个时候随着项目的不断庞大，app.js文件的内容过大，会造成首屏的渲染速度变慢

## 2.代码的分包

- 所以，对于一些不需要立即使用的组件，我们可以单独对它们进行拆分，拆分成一些小的代码块chunk.js
- 这些chunk.js会在需要时从服务器加载下来，并且运行代码，显示对应的内容
  [![在这里插入图片描述](https://blog-1305504063.cos.ap-beijing.myqcloud.com/fd46bf72-9fde-11ed-b8a2-5cea1d84200c.png)](https://blog-1305504063.cos.ap-beijing.myqcloud.com/fd46bf72-9fde-11ed-b8a2-5cea1d84200c.png)

# 八、异步组件：Vue的代码分包（实际开发用的不多，用路由懒加载比较多）

## 1.背景

- 如果我们的项目过大了，对于某些组件我们希望通过异步的方式来进行加载（目的是可以对其进行分包处理），那 么Vue中给我们提供了一个函数：`defineAsyncComponent`。

## 2.defineAsyncComponent接受两种类型的参数：

- 类型一：工厂函数，该工厂函数需要返回一个Promise对象；
- 类型二：接受一个对象类型，对异步函数进行配置；
  [![在这里插入图片描述](https://blog-1305504063.cos.ap-beijing.myqcloud.com/fdcf9d3a-9fde-11ed-a21f-5cea1d84200c.png)](https://blog-1305504063.cos.ap-beijing.myqcloud.com/fdcf9d3a-9fde-11ed-a21f-5cea1d84200c.png)

# 九、异步组件和Suspense：

## 1.注意：

目前Suspense显示的是一个实验性的特性，API随时可能会修改。

## 2.Suspense是一个内置的全局组件，该组件有两个插槽：

- default：如果default可以显示，那么显示default的内容；
- fallback：如果default无法显示，那么会显示fallback插槽的内容；
  [![在这里插入图片描述](https://blog-1305504063.cos.ap-beijing.myqcloud.com/fe28adc4-9fde-11ed-9a93-5cea1d84200c.png)](https://blog-1305504063.cos.ap-beijing.myqcloud.com/fe28adc4-9fde-11ed-9a93-5cea1d84200c.png)

# 十、组件的ref和$refs

## 1.使用场景：

- 某些情况下，我们在组件中想要直接获取到元素对象或者子组件实例，这个时候，我们可以给元素或者组件绑定一个ref的attribute属性
- 组件实例有一个`$refs`属性，它一个对象Object，持有注册过 ref attribute 的所有 DOM 元素和组件实例。
  [![在这里插入图片描述](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/fe7b501a-9fde-11ed-a287-5cea1d84200c.png)](https://blog-1305504063.cos.ap-beijing.myqcloud.com/fe7b501a-9fde-11ed-a287-5cea1d84200c.png)

# 十一、组件的v-model

## 1.原生input标签的v-model

- v-model默认帮助我们完成了两件事：`v-bind:value`的数据绑定和`@input`的事件监听

## 2.组件的v-model

- v-model默认帮助我们完成了两件事：`v-bind:modelValue`的数据绑定和`@update:model-value`的事件监听

## 3.代码案例

- `<hy-input v-model="message"></hy-input>`
- `<hy-input :modelValue="message" @update:model-value="message = $event"></hy-input>`
  [![在这里插入图片描述](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/fec8c36b-9fde-11ed-9329-5cea1d84200c.png)](https://blog-1305504063.cos.ap-beijing.myqcloud.com/fec8c36b-9fde-11ed-9329-5cea1d84200c.png)

## 4.子组件input标签中:vlaue和@input简写方式

[![在这里插入图片描述](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/ff270f52-9fde-11ed-869d-5cea1d84200c.png)](https://blog-1305504063.cos.ap-beijing.myqcloud.com/ff270f52-9fde-11ed-869d-5cea1d84200c.png)

## 5.组件中绑定两个v-model

[![在这里插入图片描述](https://images-jsh.oss-cn-beijing.aliyuncs.com/ljl/ff90b98f-9fde-11ed-80f7-5cea1d84200c.png)](https://blog-1305504063.cos.ap-beijing.myqcloud.com/ff90b98f-9fde-11ed-80f7-5cea1d84200c.png)


