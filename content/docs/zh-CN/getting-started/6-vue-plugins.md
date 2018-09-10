---
title: 使用 Vue 插件
contributors: [smilecc]
---

此页面提供了目前在 NativeScript-Vue 中可用的 Vue 插件的概述。

* [Vue Router](#vue-router)
* [Vuex](#vuex)

## Vue Router

> 目前，与 Vue Router 的集成是**实验性**的，如要了解更多信息，你可以[参阅 Vue Router 页面](/zh-CN/docs/routing/vue-router/)。

### 安装并引入插件

有关于如何安装和使其在 NativeScript-Vue 应用程序中可用的详细信息，你可以[参阅 Vue Router 页面](/zh-CN/docs/routing/vue-router/)。

### 使用说明

移动设备中的路由策略与在浏览器中的路由策略并不相同，所以我们原本熟悉的 Vue 路由规则并不完全适用于 NativeScript-Vue。

与之不同的是，你**需要使用 `route.push` 方法来切换到新路由**，下面的示例演示了如何使用 `tap` 事件来切换路由。

```HTML
<Button class="btn btn-primary" @tap="$router.push('/counter')">Counter</Button>
``` 

若想了解更多关于如果在 NativeScript-Vue 应用中使用该插件的信息，请[参阅 Vue Router 页面](/zh-CN/docs/routing/vue-router/)。

## Vuex

Vuex 是一个专为 Vue.js 应用程序开发的状态管理模式。它采用集中式存储管理应用的所有组件的状态，并以相应的规则保证状态以一种可预测的方式发生变化。

### 安装该插件

就像在你的 Vue.js 应用中安装 Vuex 一样使用 npm 进行安装，例如：

```shell
$ npm install --save vuex
```

最新版本的 Vuex 将会加入到你的 `package.json`。

### 导入该插件

打开你的应用入口文件（例如 `app.js` 或 `main.js`），然后在顶部添加如下代码：

```js
import Vuex from 'vuex'
Vue.use(Vuex)
```

现在你就可以在你的移动应用程序中使用 Vuex 来进行状态管理了，就像是在标准的 Vue Web 应用中使用它一样。

### 用法: 创建一个 Store（仓库）

你需要创建一个新常量来存储你的状态并用于 Vuex 的 API 调用。当你创建 Vue 实例后，你可以选择在入口文件中进行此操作，也可以在单独的文件夹中进行此操作（例如 `/store`）。

在以下的示例的 store 常量中，包含了一个计数器的状态管理，和可对其进行修改的变更方法（`mutations`）。

```js
const store = new Vuex.Store({
    state: {
      count: 0
    },
    mutations: {
      increment: state => state.count++,
      decrement: state => state.count--
    }
})
```

### 用法: 使用 Store

现在你可以通过调用刚刚创建的 Store 来管理状态。在以下示例中，当你按下 ”+“ 或 ”-“ 按钮时，应用会更新其计数器的数值。注意，在这个例子中你并不会修改状态本身，而是通过调用变更方法（mutations）来实现对计数器值的自增或自减。

```js
new Vue({
  computed: {
    count(){
      return store.state.count
    }
  },

  template: `
    <Page>
      <ScrollView>
        <StackLayout>
          <Button @tap="increment" text="+" />
          <Button @tap="decrement" text="-" />
          <Label :text="count" />
        </StackLayout>
      </ScrollView>
    </Page>
  `,

  methods: {
    increment() {
      store.commit('increment')
    },
    decrement() {
      store.commit('decrement')
    }
  }
}).$start()
```

有关于 Vuex 的更多信息，请[参阅 Vuex 的文档](https://vuex.vuejs.org/en/core-concepts.html)。

若要了解更多关于通过 Vuex 管理元素的例子，你可以浏览 NativeScript-Vue 示例 Groceries 中的 [`/store` 文件夹](https://github.com/tralves/groceries-ns-vue/tree/master/src/store/)。
