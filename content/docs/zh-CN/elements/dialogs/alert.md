---
title: Alert 对话框
apiRef: https://docs.nativescript.org/api-reference/modules/_ui_dialogs_#alert
contributors: [yinxiupei]
---

 `alert()` 方法用于显示带有一条指定消息和一个 OK 按钮的对话框，主要用于为用户展示无需操作的消息和通知。

该方法是 [`dialogs` 模块](https://docs.nativescript.org/api-reference/modules/_ui_dialogs_) 的一部分。

---

## 基本用法

 `alert()` 是全局方法，可以在应用的任意地方调用。

```javascript
alert('Your message')
  .then(() => {
    console.log("Alert dialog closed.");
  });
```

## 对话框选项设置

```JavaScript
alert({
  title: "Your title",
  message: "Your message",
  okButtonText: "Your OK button text"
}).then(() => {
  console.log("Alert dialog closed");
});
```

[> screenshots for=AlertDialog <]
