---
title: Login 对话框
apiRef: https://docs.nativescript.org/api-reference/modules/_ui_dialogs_#login
contributors: [yinxiupei]
---
 `login()` 方法用于显示一个可为用户提供登录功能的对话框。

该方法是 [`dialogs` 模块](https://docs.nativescript.org/api-reference/modules/_ui_dialogs_) 的一部分。

---

## 基本用法

 `login()` 是全局方法，可以在应用的任意地方调用。

```javascript
login("Your message", "Username field value", "Password field value").then(result => {
  console.log(`Dialog result: ${result.result}, user: ${result.userName}, pwd: ${result.password}`);
});
```

## 对话框选项设置

```JavaScript
login({
  title: "Your login title",
  message: "Your login message",
  okButtonText: "Your OK button text",
  cancelButtonText: "Your Cancel button text",
  userName: "Username field value",
  password: "Password field value"
}).then(result => {
  console.log(`Dialog result: ${result.result}, user: ${result.userName}, pwd: ${result.password}`);
});
```

[> screenshots for=LoginDialog <]
