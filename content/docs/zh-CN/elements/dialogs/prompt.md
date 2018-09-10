---
title: Prompt 对话框
apiRef: https://docs.nativescript.org/api-reference/modules/_ui_dialogs_#prompt
contributors: [yinxiupei]
---

 `prompt()` 方法用于显示一个具有单行输入框的对话框。

该方法是 [`dialogs` 模块](https://docs.nativescript.org/api-reference/modules/_ui_dialogs_) 的一部分。

---

## 基本用法

 `prompt()` 是全局方法，可以在应用的任意地方调用。

```JavaScript
prompt('Your message to the user', 'Suggested user input')
.then(result => {
  console.log(`Dialog result: ${result.result}, text: ${result.text}`)
})
```

## 对话框选项设置

```JavaScript
prompt({
  title: "Your dialog title",
  message: "Your message",
  okButtonText: "Your OK button text",
  cancelButtonText: "Your Cancel button text",
  defaultText: "Suggested user input",
}).then(result => {
  console.log(`Dialog result: ${result.result}, text: ${result.text}`)
});
```

## 输入框类型设置

你可以使用 `inputType` 设置输入框类型。可以根据需求选择纯文本输入框（文本）或启用电子邮件输入框（电子邮件）或密码隐藏输入框（密码）。

```JavaScript
inputType: dialogs.inputType.text
inputType: dialogs.inputType.email
inputType: dialogs.inputType.password
```

**注意:** 该选项不是全局变量，应用程序在使用 `inputType` 之前按需引入 `dialogs` 模块。

```JavaScript
const dialogs = require('tns-core-modules/ui/dialogs')
```

### 例子

```JavaScript
const dialogs = require('tns-core-modules/ui/dialogs')

prompt({
  title: "Email Prompt",
  message: "Provide your email address:",
  okButtonText: "OK",
  cancelButtonText: "Cancel",
  defaultText: "name@domain.com",
  inputType: dialogs.inputType.email
}).then(result => {
  console.log(`Dialog result: ${result.result}, text: ${result.text}`)
});
```

[> screenshots for=PromptDialog <]
