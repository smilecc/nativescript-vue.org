---
title: v-view 指令
contributors: [smilecc]
---

`v-view` 指令允许你将当前元素的 `View` 作为父组件的一个属性。

> **译者注：**它的本质应是个语法糖，你可以在本文底部查看到它所起到的实际作用。

---

```HTML
<Child v-view:parentPropertyName />
<!-- 等同于： -->
<Child ~parentPropertyName />
```

```HTML
<Child v-view:parentArrayPropertyName.array />
<!-- 等同于： -->
<Child ~parentArrayPropertyName.array />
```

---

### 示例: `<RadSideDrawer>`

`<RadSideDrawer>` 组件是 [Progress NativeScript UI](http://docs.telerik.com/devtools/nativescript-ui/Controls/Angular/SideDrawer/getting-started) 包的一部分。

`<RadSideDrawer>` 组件的 `drawerContent` 和 `mainContent` 各需要设置一个 `View` 示例，通过使用 `v-view` 指令，你仅需使用几行代码就可以实现此操作。

```HTML
<RadSideDrawer>
  <StackLayout ~drawerContent />
  <StackLayout ~mainContent />
</RadSideDrawer>
```

如果没有 `v-view` 指令，你需要以更枯燥以及更容易出错的方式去实现它。

> **译者注：**也代表了该指令所起到的实际作用。

```HTML
<RadSideDrawer ref="drawer">
  <StackLayout ref="drawerContent" />
  <StackLayout ref="mainContent" />
</RadSideDrawer>
```

```JavaScript
{
  mounted() {
    this.$refs.drawer.nativeView.drawerContent = this.$refs.drawerContent.nativeView
    this.$refs.drawer.nativeView.mainContent = this.$refs.mainContent.nativeView
  }
}
```