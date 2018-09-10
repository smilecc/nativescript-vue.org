---
title: 快速开始
contributors: [smilecc]
---

如果你不想安装，使用 [NativeScript Playground](/en/docs/getting-started/playground-tutorial) 可以帮助你在无需安装和配置的情况下尝试 NativeScript-Vue，

但如果你[已经准备好使用本机进行开发](/en/docs/getting-started/installation), 你可以使用模板开始你的项目。

```shell
$ npm install -g @vue/cli @vue/cli-init
$ vue init nativescript-vue/vue-cli-template <project-name>
$ cd <project-name>
$ npm install
```

接下来，使用如下命令运行你的应用：

```shell
$ npm run watch:<platform>
```

其中 `platform` （平台）可选择 `ios` 或 `android` 。

这组命令将在你的系统上执行以下操作：

1. 在你的系统上安装 Vue CLI 并且初始化它的加载项，这使得你可以在你的系统上同时使用 NativeScript CLI 与 Vue CLI。如果你已经安装 Vue CLI，请跳过此命令。
2. 拉取所选的模板（与 Vue CLI 相兼容的 NativeScript-Vue 模板），并在本地创建项目。这个模板依赖于`.vue`组件，并提供开箱即用的路由与 Vuex 状态管理。有关更多可用模板的信息，请参阅[模板](/en/docs/getting-started/templates)。
3. 切换到刚才所新建项目的目录。
4. 在本地安装所有的 npm 依赖项。
5. 为已连接的设备构建并运行项目，当没有已连接的设备时，则会尝试为所选的平台安装模拟器。`watch`选项会检测代码的改动，并会自动应用新改动。
