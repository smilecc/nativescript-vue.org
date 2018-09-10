---
title: Action 对话框
apiRef: https://docs.nativescript.org/api-reference/modules/_ui_dialogs_#action
contributors: [yinxiupei]
---

 `action()` 方法用于显示一个可供选择的列表与一个取消按钮的对话框，用户可以根据需求选择或是关闭选择。

该方法是 [`dialogs` 模块](https://docs.nativescript.org/api-reference/modules/_ui_dialogs_) 的一部分。

---

## 基本用法

`action()` 是全局方法，可以在应用的任意地方调用。

```JavaScript
action("Your message", "Cancel button text", ["Option1", "Option2"])
  .then(result => {
    console.log(result);
  });
```

[> screenshots for=ActionDialog <]
