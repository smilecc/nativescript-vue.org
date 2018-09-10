---
title: Confirm 对话框
apiRef: https://docs.nativescript.org/api-reference/modules/_ui_dialogs_#confirm
contributors: [yinxiupei]
---

 `confirm()` 方法用于显示一个带有指定消息和 OK 及取消按钮的对话框。

该方法是 [`dialogs` 模块](https://docs.nativescript.org/api-reference/modules/_ui_dialogs_) 的一部分。

---

## 基本用法

 `confirm()` 是全局方法，可以在应用的任意地方调用。

```javascript
confirm('Your message')
  .then(result => {
    console.log(result);
  });
```

## 对话框选项设置

```javascript
confirm({
  title: "Your title",
  message: "Your message",
  okButtonText: "Your OK button text",
  cancelButtonText: "Your Cancel text"
}).then(result => {
  console.log(result);
});
```

[> screenshots for=ConfirmDialog <]
