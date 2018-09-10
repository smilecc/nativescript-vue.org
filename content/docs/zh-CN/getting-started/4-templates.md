---
title: 模板
contributors: [smilecc]
outdated: false
---

此页面提供了可用于 NativeScript-Vue 开发应用程序的模板的概述。当有新的模板或旧模板被弃用的时候，列表会得到相应的更新。

> **注意：** 为了使用以下模板，你应该先[在系统上安装 NativeScript 开发环境](/en/docs/getting-started/installation)。

**当前可供选择的模板:**

* [nativescript-vue/vue-cli-template](#nativescript-vuevue-cli-template) 
* [nativescript-vue/nativescript-vue-template](#nativescript-vuenativescript-vue-template) 

**已经废弃的模板:**

* [tralves/nativescript-vue-webpack-template](https://github.com/tralves/nativescript-vue-webpack-template/)

## nativescript-vue/vue-cli-template

**项目链接:** [https://github.com/nativescript-vue/vue-cli-template](https://github.com/nativescript-vue/vue-cli-template)

**特性**

* `.vue` 单文件组件
* Vuex &mdash; 状态管理 (可选)
* Vue Router &mdash; 路由 (可选) &mdash; **实验性**
* NativeScript 主题

使用该模板。你可以使用 [Vue CLI](https://github.com/vuejs/vue-cli) 开始开发你的应用程序，并围绕`.vue`文件进行组件设计。该模板开箱即用，还提供了 Vue 的高级功能（[Vuex](https://vuex.vuejs.org/en/) 和 [Vue Router](https://github.com/vuejs/vue-router)），以及对 [NativeScript 主题](https://docs.nativescript.org/ui/theme) 的支持。

功能方面，该模板是 NativeScript 基础模板的衍生品，并实现了一个简单的由按钮控制的计数器。

这个模板最初是由 [Pascal Martineau](https://github.com/lewebsimple/) 所构建的，而现在这个模板已经正式支持 NativeScript-Vue。

**使用方法**

```shell
$ npm install -g @vue/cli @vue/cli-init
$ vue init nativescript-vue/vue-cli-template <project-name>
$ cd <project-name>
$ npm install
$ npm run watch:android
$ # or
$ npm run watch:ios
```

## nativescript-vue/nativescript-vue-template

**项目链接:** [https://github.com/nativescript-vue/nativescript-vue-template](https://github.com/nativescript-vue/nativescript-vue-template)

**特性**

* 纯 JavaScript &mdash; 没有 `.vue` 文件
* NativeScript 主题

从 [NativeScript CLI](https://github.com/NativeScript/nativescript-cli) 中使用该模板开始构建你的应用程序，它仅使用 JavaScript。

功能方面，该模板是 NativeScript 基础模板的衍生品，并实现了一个简单的由按钮控制的计数器。

**使用方法**

```shell
$ tns create <project-name> --template nativescript-vue-template
$ cd <project-name>
$ tns run android
$ # or
$ tns run ios
```
