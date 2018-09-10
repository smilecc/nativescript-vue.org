---
title: 使用 NativeScript 插件
contributors: [smilecc]
---

插件在 NativeScript-Vue 中的使用方式与在 [其他任意 NativeScript 应用](https://docs.nativescript.org/plugins/plugins) 中一样，但你可能会想知道 UI 插件如何与 Vue 一起使用。

UI 插件的使用方式几乎和你在 Angular 应用程序中使用 NativeScript UI 插件的方式一样。

## 使用示例: nativescript-gradient

让我们来看看该如何使用 [nativescript-gradient](https://github.com/EddyVerbruggen/nativescript-gradient)，你也可以在 [listview 示例中](https://github.com/rigor789/nativescript-vue/tree/master/samples/app/app-with-list-view.js) 查看其用法.

### 通过 NativeScript CLI 安装插件

在此之前，你应该先[在系统上安装 NativeScript 开发环境](/zh-CN/docs/getting-started/installation)，然后运行以下命令：

```shell
$ npm install --save nativescript-gradient
```

> **注意:** 如果你使用的是 [vue-cli-template](/zh-CN/docs/getting-started/templates/#nativescript-vuevue-cli-template)，你可能需要运行以下命令：

```shell
$ npm run clean
```

### 在你的应用中注册该插件

打开你的入口文件 (例如 `app.js` 或 `main.js`)，并且在顶部增加以下代码：

```JavaScript
Vue.registerElement('Gradient', () => require('nativescript-gradient').Gradient)
```

这需要你在你的 `Vue` 示例中注册该插件。而 `registerElement` 函数需要 `<Element>` 的名称作为第一个参数，并且需要一个返回该插件的函数作为第二个参数。

- **参数1** 提供一个元素名称用于在你的代码中调用。
- **参数2** 提供该插件的 npm 包名。

### 在你的应用中使用该插件

```HTML
<Gradient direction="to right" colors="#FF0077, red, #FF00FF">
  <Label text="Best gradient." horizontalAlignment="center"
         style="color: white; padding: 20" />
</Gradient>
```
