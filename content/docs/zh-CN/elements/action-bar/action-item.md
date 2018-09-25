---
title: ActionItem
apiRef: https://docs.nativescript.org/api-reference/classes/_ui_action_bar_.actionitem
contributors: [yinxiupei]
---

ActionItem 组件被用于 ActionBar 中添加额外的操作按钮。

---

```html
<ActionBar title="My App">
  <ActionItem @tap="onTapShare"
    ios.systemIcon="9" ios.position="left"
    android.systemIcon="ic_menu_share" android.position="actionBar" />
  <ActionItem @tap="onTapDelete"
    ios.systemIcon="16" ios.position="right"
    text="delete" android.position="popup" />
</ActionBar>
```

#### 条件渲染

通过指令 `v-show` 可以设置 ActionItems 显示状态。

```html
<ActionBar title="My App">
  <ActionItem @tap="onTapEdit"
    v-show="!isEditing"
    ios.systemIcon="2" ios.position="right"
    android.systemIcon="ic_menu_edit" />
  <ActionItem @tap="onTapSave"
    v-show="isEditing"
    ios.systemIcon="3" ios.position="right"
    android.systemIcon="ic_menu_save" />
  <ActionItem @tap="onTapCancel"
    v-show="isEditing"
    ios.systemIcon="1"
    android.systemIcon="ic_menu_close_clear_cancel" />
</ActionBar>
```

## 属性（Props）

| 名称 | 类型 | 描述 |
|------|------|-------------|
| `ios.systemIcon` | `String` | iOS 中的图标。
| `android.systemIcon` | `String` | Android 中的图标。
| `ios.position` | `String` | 在 iOS 中的位置。<br>可选值:<br>- `left` (默认): ActionBar 的左侧位置。<br>- `right`: ActionBar 的右侧位置。
| `android.position` | `String` | 在 Android 中的位置。<br>可选值:<br>- `actionBar` (默认): 直接将子项放入 ActionBar 中。<br>- `popup`: 将子项渲染成文本的形式放入对话框的列表栏中。<br>- `actionBarIfRoom`: 如果有空间，即把子项放在 ActionBar 中，否则将子项放入列表栏中。

## 事件

| 名称 | 描述 |
|------|-------------|
| `tap`| ActionItem 被点击时触发。
