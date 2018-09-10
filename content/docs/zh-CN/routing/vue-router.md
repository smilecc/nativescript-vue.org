---
title: Vue Router
contributors: [smilecc]
---

> 目前，对 Vue Router 的整合还是 **实验性** 的，如果你想使用非实验性的路由，你可以尝试[手动路由](/en/docs/routing/manual-routing)。

在 Vue Router 中，你可以选择[基于组件的路由](https://router.vuejs.org/api/#router-view)或基于页面的路由。但在移动应用中，你可能会更乐意使用基于页面的路由。

## 安装并引入该插件

在命令行中运行：

```Shell
$ npm install --save vue-router
```

在你的应用的入口文件（例如 `app.js` 或 `main.js`），引入 Vue 与 Vue Router，并让他们相结合。

```JavaScript
const Vue = require('nativescript-vue');
const VueRouter = require('vue-router');

Vue.use(VueRouter);
```

## 使用

本节将会向你介绍基于页面的路由的完整示例，我们会将其关键部分分解出来，并在此过程中提供注释。

---
首先，我们定义一个 `Master` 页面，并它的标题为当前路由（`$route.path`）。

创建一个带有 `@tap="$router.push('/detail')"` 的按钮，当该按钮被点击时，一个新的 `Detail` 页面会被压入栈，并且导航到该页面。

随后我们创建第二个按钮，该按钮带有一个查询参数（query param） `user`，当该按钮被点击时，它会将附加信息传递到 `Detail` 页面。

```HTML
const Master = {
  template: `
    <Page>
      <ActionBar :title="$route.path" />
      <StackLayout>
        <Button text="To Details" @tap="$router.push('/detail')" />
        <Button text="To Details (with query param)" @tap="$router.push('/detail?user=John+Appleseed')"></Button>
      </StackLayout>
    </Page>
  `
};
```

---
接下来，定义一个带有 `NavigationButton` 的 `Detail` 页面。在 iOS 上，该按钮会自动返回页面栈中的上一页，但在 Android 上，你需要手动给它添加一个 `tap` 事件处理器（在 iOS 上会被忽略）用于返回上一页：`@tap="$router.back()"`。

使用在 `Master` 定义的查询参数（query param）`user`。例如，我们在 `Detail` 页面中以文本的形式显示它：`<Label :text="$route.query.user">`。

创建一个带有 `$router.go(<number-of-pages>)` 的按钮，当该按钮被点击时，它将会导航到页面栈中的前一页。

```HTML
const Detail = {
  template: `
    <Page>
      <ActionBar :title="$route.path">
        <NavigationButton text="Back!" android.systemIcon="ic_menu_back" @tap="$router.back()" />
      </ActionBar>
      <StackLayout>
        <Label :text="$route.query.user" v-if="$route.query.user" />
        <Button text="Back to Master" @tap="$router.go(-1)" />
      </StackLayout>
    </Page>
  `
};
```

---
实例化一个路由实例，启用页面路由功能（`pageRouting`），并且在此定义你的应用的所有页面。

```JavaScript
const router = new VueRouter({
  pageRouting: true,
  routes: [
    {path: '/master', component: Master},
    {path: '/detail', component: Detail},
    {path: '*', redirect: '/master'}
  ]
});
```

---
在应用启动时加载一个路由。

```JavaScript
router.replace('/master');
```

---
把你定义的路由告知给 `Vue`。

```JavaScript
new Vue({
  router
}).$start();
```

## 其他相关

Vue Router 有非常多的技巧，所以请一定要参阅[官方文档](https://router.vuejs.org/zh/)。

你还可以查看以下 [NativeScript-Vue 示例](https://github.com/nativescript-vue/nativescript-vue/tree/master/samples)：

* [app-with-page-routing](https://github.com/nativescript-vue/nativescript-vue/tree/master/samples/app/app-with-page-routing.js)
* [app-with-router](https://github.com/nativescript-vue/nativescript-vue/tree/master/samples/app/app-with-router.js)
* [app-with-router-pages](https://github.com/nativescript-vue/nativescript-vue/tree/master/samples/app/app-with-router-pages.js)