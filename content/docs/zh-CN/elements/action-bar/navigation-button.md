---
title: NavigationButton
apiRef: https://docs.nativescript.org/api-reference/classes/_ui_action_bar_.navigationbutton
contributors: [yinxiupei]
---

NavigationButton 组件是 NativeScript 对 Android 中导航按钮以及 iOS 中返回按钮的抽象。

---

```html
<ActionBar title="My App">
  <NavigationButton text="Go back" android.systemIcon="ic_menu_back" @tap="goBack" />
</ActionBar>
```

## 属性（Props）

| 名称 | 类型 | 描述 |
|------|------|-------------|
| `text` | `String` | 设置 iOS 上显示的文本。
| `android.systemIcon` | `String` | 设置 Android 上显示的图标。

*你可以从 <https://developer.android.com/reference/android/R.drawable.html> 中查找 Android 的图标列表，所有的图标是以 `ic_` 前缀开头的。*

## 事件

| 名称 | 描述 |
|------|-------------|
| `tap`| NavigationButton 被点击时触发。
