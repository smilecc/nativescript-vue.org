---
title: ActionBar
apiRef: https://docs.nativescript.org/api-reference/classes/_ui_action_bar_.actionbar
contributors: [yinxiupei]
---

ActionBar 组件是 NativeScript 对 Android 中 ActionBar 以及 iOS 中 NavigationBar 的抽象。

---

#### 使用标题属性

```html
<ActionBar title="MyApp" />
```

#### 自定义视图作为标题

```html
<ActionBar>
  <StackLayout orientation="horizontal">
    <Image src="res://icon" width="40" height="40" verticalAlignment="center" />
    <Label text="ativeScript" fontSize="24" verticalAlignment="center" />
  </StackLayout>
</ActionBar>
```

#### 设置 Android 应用图标

```html
<ActionBar title="My App" android.icon="res://icon" android.iconVisibility="always" />
```

#### 清除边框
iOS 以及 Android 的 ActionBar 组件底部会有边框。此外，因为 iOS 的应用过滤器导致 ActionBar 背景颜色稍微不一样，将 `flat` 属性设置为 `true` 可以避免这样的情况。

```html
<ActionBar title="My App" flat="true" />
```

## 属性（Props）

| 名称 | 类型 | 描述 |
|------|------|-------------|
| `title` | `String` | 显示在 ActionBar 上的标题。
| `android.icon` | `String` | Android 上的图标。
| `android.iconVisibility` | `String` | 设置图标何时显示。
| `flat` | `boolean` | 消除组件边框以及 iOS 颜色过滤器。 默认 `false`。
