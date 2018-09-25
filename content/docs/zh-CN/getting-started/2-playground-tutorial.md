---
title: Playground 教程
contributors: [yinxiupei]
---
[NativeScript Playground](https://play.nativescript.org?template=play-vue) 一个可以在浏览器中使用 NativeScript 以及 Vue.js 的在线工具。点击链接，拖拽工具栏的组件开始你的应用。

你可以随心所欲的使用 Playground 开发你的应用。你可以使用它来体验 NativeScript 的开发，又或者使用它开发完整的项目。 然而，当你决定准备将使用 Playground 开发时，如果需要更多高级功能，你需要在本地 [安装 NativeScript 工具](/zh-CN/docs/getting-started/installation) 染后 [选择一个模板立即开始](/zh-CN/docs/getting-started/templates)

**本页会介绍以下两部分内容：**
* [第一部分: 了解 Playground](#part-1-getting-familiar-with-the-playground)
    * [使用之前](#before-you-start)
    * [布局](#the-lay-of-the-land)
    * [拖放代码](#drag-and-drop-to-code)
    * [实时检查](#check-it-out-real-time)
    * [代码配置](#configure-your-code)
* [第二部分: 构建一个应用](#part-2-building-an-app)
    * [一个 Vue.js 模板](#the-bare-vuejs-template)
    * [基础设计](#basic-design)
    * [基础功能: 添加功能任务](#basic-functionality-add-tasks)
    * [基础功能: 视图, 布局以及代办应用的删除功能](#basic-functionality-view-complete-and-delete-tasks-from-the-to-do-tab)
    * [基础功能: view, return to active tasks, and delete tasks from the Completed tab](#basic-functionality-view-return-to-active-tasks-and-delete-tasks-from-the-completed-tab)
    * [进阶功能: 自定义输入框和按钮样式](#advanced-design-styled-input-field-and-button)
    * [进阶功能: 自定义导航栏样式](#advanced-design-styled-tab-navigation)
    * [进阶功能: 自定义活动任务样式](#advanced-design-styled-active-tasks)
    * [进阶功能: 自定义已完成任务样式](#advanced-design-styled-completed-tasks)


# 第一部分: 了解 Playground
点击 [链接](https://play.nativescript.org/?template=play-vue) 呈现在你面前的一个在线代码编辑器并为你预加载了一个基础的 NativeScript + Vue.js 模板。

> **提示:** 点击 [Playground 示例](/zh-CN/docs/getting-started/playground-tutorial) 了解如何在 Playground 中快速开始。

### 使用之前

![playground welcome screen](/screenshots/ns-playground/playground-home.png)
如果这是你第一次进入该页面， Playground 会尝试提示你安装 NativeScript Playground 以及 NativeScript Preview 两个应用。两者结合可以让你在设备上实时查看到页面改动。不需要代码编译以及打包代码。

你可以忽略以上步骤，但是没有它，你可能会错过很多关于 Vue.js 和 NativeScript 的乐趣

在修改代码时保持应用程序正常运行。

### 布局

![](/screenshots/ns-playground/playground-layout.png)

界面左侧是文件管理器与 **组件** 面板。你在应用程序上的大部分工作都将在 `components` 文件下的 `HelloWorld.vue` 中进行，之后你也会为其创建用户接口以及其背后的业务逻辑。对于其他文件暂时不需要过深入研究任何。

**组件** 面板为用户提供了一部分预先配置的可用的 NativeScript UI 组件代码。

在界面的顶部导航栏中，你可以在设备上预览提交的修改、保存到云端、或是下载代码。

界面底部的控制台会很友好的给你提供实时错误报告与设备日志。

### 拖放代码

![](/screenshots/ns-playground/playground-drag-and-drop.gif)

只需要点击 **组件** 面板里的组件并将其拖放到编辑器上，那里立即会插入一个 `<template>` 块在 `components` 里的 `HelloWorld.vue` 中。松开鼠标，文件中会插入一段当前组件预先编辑好的代码块。与它一起使用的任何方法（例如：有关于按钮点击或是项目点击的事件）也会自动添加到 `<script>` 块中。

> **提示：** 使用 **组件** 面板的搜索功能可以快速找到想要的组件。但搜索功能只能根据组件标题而不是实际代码中使用的名称进行查询。举个例子：你可以根据 *text field* 搜索目标组件但是搜索不到关于 *textfield* 的组件。
>
> ![](/screenshots/ns-playground/playground-component-search.gif)

对于大部分 UI 组件，你需要将该组件拖拽至 `<Page>` 代码块中，将组件置于布局组件中更佳。应用程序中 UI 组件在屏幕上的位置由你选择的布局决定。

> **注意:** 此时, 如果你将代码置于编辑器中从而引起你的应用崩溃或是无法加载。这种情况下，可以通过界面底部 **Errors** 栏以及 **Device Logs** 栏获取一些信息。

### 实时检查

![](/screenshots/ns-playground/playground-preview.gif)

在你觉得当前代码为有效代码时，可以点击 **Preview** （或 `Ctrl+S` 或是 `Cmd+S`）进行预览，此时在设备上可以立即查看应用刷新情况。

当你在设备上进行测试时，应用有可能会出现意外终止被关闭的情况。这时你只需要重新启动然后仔细查看崩溃报告。

如果你发现你的设备在有代码更改的情况却没有任何反应，点开 **QR code**，然后使用 *Playground* 应用重新扫描二维码即可。

### 代码配置

所以，当组件运行并且展示在你的眼前时，你会觉得很有意思并且想把当前应用占为己有。这时候需要处理一些 Playground 提供的默认代码，修改布局尺寸以及标签，删除或是增加一些新的元素。

将滚动条滚动至 `<style scoped>` 块中，可以对样式进行修改。你可以根据自己习惯配置颜色和字体大小。

# 第二部分: 构建一个应用

如果你想探索 [NativeScript Playground](https://play.nativescript.org?template=play-vue)更多功能，你可以从创建一个简单待办应用程序开始，需求如下：

* 基础设计
  * 两栏式布局
  * 一栏展示当前待办任务以及添加新的待办任务功能
  * 第二栏为完成任务列表
* 基础功能
  * 添加待办：用户添加文本任务
  * 查看详情：最新添加的任务被列为活动任务并且可以被点击
  * 完成任务：点击活动任务显示一个带有选项的操作对话框
  * 删除任务：点击一个活动任务或者已完成的任务显示一个带有选项的操作对话框
* 进阶功能
  * 自定义输入框和按钮样式
  * 自定义导航栏样式
  * 自定义活动任务样式
  * 已完成任务是自定义的样式

> **提示:** 以上的所有教程包含一些 *NativeScript* 以及 *Requirement* 基础部分。你可以跳过这些基础教程直接了解自定义方法的实现。

## 一个 Vue.js 模板

![](/screenshots/ns-playground/playground-home.png)

围绕本教程的所有开发都是在 `components` 中的 `HelloWorld.vue` 文件中，包括前端，后端逻辑以及几乎所有的样式内容。

`HelloWorld.vue` 最开始只有一个内容只有几个标签的 `<template>` 块。当你拖拽用户界面组件到改文件时， Playground 会将相应的方法添加至 `<script>` 块中。

你可以在 `<template>` 块中设计用户界面、可以在 `<script>` 块中构建应用的逻辑功能。 `<template>` 块中要求必须时兼容 NativeScript 的XML。而 `<script>` 块可以接受 Vue.js 以及 NativeScript JavaScript 的任何代码。

## 基础设计

### 分段进行

在本节中将介绍应用功能开始和最终的实现。
Here's how your app will look at the start and at the end of this section.

| 界面初始化 | 第一栏 | 第二栏 |
|-------|-----|-----|
| ![Vue.js 模板](/screenshots/ns-playground/two-tabs-start.jpg) | ![第一栏](/screenshots/ns-playground/two-tabs-tab-1.jpg) | ![第二栏](/screenshots/ns-playground/two-tabs-tab-2.jpg) |

### NativeScript 基础

`<Page>` 是每一个 NativeScript-Vue 应用程序的最外层的 UI 元素。所有的其他 UI 元素都要嵌套在 `<Page>` 元素里。

`<ActionBar>` 元素可为 `<Page>` 提供一个工具栏，一个 `<Page>` 里有且仅可包含一个 `<ActionBar>`。

通常，在`<ActionBar>` 组件之后，你需要添加一个导航组件（例如：抽屉式或栏式视图）或是布局组件。这些组件控制应用程序的基本布局，你只需要决定如何放置其它 UI 元素

### 需求实现

使用 `<TabView>` 创建一个两栏式应用程序。

1. 根据应用需求修改 `<ActionBar>` 组件的标题属性。
2. 移除 `<ScrollView>` 组件块以及模板里所有内容。<br/>`<ScrollView>` 组件是滚动内容的最外层布局。
3. 将 `<TabView>` 组件拖放至内容里。<br/> Playground 会提供代码的格式化功能，包括代码缩进。但是，代码格式化功能只在代码插入之后，浏览器的撤消功能仅能恢复格式化而不是插入的代码。
4. 将 `<TabView>` 的高度设置满屏（即设置为 100%）
5. 根据当前内容修改 `<TabViewItem>` 组将的标题属性。<br/>此时，你会看到在 `<Label>` 组件里显示的是没有样式和格式化的文本内容，为每个 `<Label>` 组件设置各自的 `textWrap="true"` 属性可改进文本的可视化。

以上操作全部完成，那么你的 `<HelloWorld.vue>` 内容与如下内容大致类似：

```HTML
<template>
  <Page class="page">
    <ActionBar title="My Tasks" class="action-bar" />
    
    <TabView height="100%">
      <TabViewItem title="To Do">
        <Label text="This tab will list active tasks and will let users add new tasks." textWrap="true" />
      </TabViewItem>
      
      <TabViewItem title="Completed">
        <Label text="This tab will list completed tasks for tracking." textWrap="true" />
      </TabViewItem>
    
    </TabView>
  </Page>
</template>

<script>
export default {
  data () {
    return {
    };
  },
}
</script>

<style scoped>
.home-panel {
  vertical-align: center;
  font-size: 20;
  margin: 15;
}

.description-label {
  margin-bottom: 15;
}
</style>
```

## 基本功能：添加任务

### 分段进行

在本节中将介绍应用功能开始和最终的实现。

| 初始化界面 | Tab 1 - 无任务 | Tab 1 - 添加任务 |
|-------|-----|-------------|
| ![修改前的 Tab](/screenshots/ns-playground/two-tabs-tab-1.jpg) | ![无任务的 Tab](/screenshots/ns-playground/input-field.jpg) | ![添加任务的 Tab](/screenshots/ns-playground/added-tasks.jpg)

### NativeScript 部分

布局组件主要用于整理应用程序的各种 UI 组件。当你想要在当前页面添加其他的 UI 组件，可以选择一个可用的布局选项。`<StackLayout>` 以及 `<GridLayout>` 是最基础以及通用的布局选项。它能让你的元素居中定位或是类表格式布局。当 `<StackLayout>` 组件按默认状态显示元素，`<GridLayout>` 组件会让你在格子中选择一个准确的定位。

### 需求实现

使用 `<GridLayout>` 将页面分成一个 `<TextField>` 和一个 `<Button>`，后两者构成应用程序的输入功能。
Use a `<GridLayout>` to arrange a `<TextField>` and a `<Button>` on the page. The latter two form the input functionality of the app.

在文本输入区域的下方使用 `<ListView>` 组件展示任务列表。

1. 在第一栏的第一个 `<TabViewItem>` 块中删除 `<Label>` 组件。
2. 在第一栏中拖放一个没有 `<TabViewItem>` 块的 `<StackLayout>`组件。<br/> 组件的默认代码创建的是一个彩色的垂直堆栈。
3. 删除 `<StackLayout>` 块的所有 `<Label>` 组件。
4. 然后在第一栏里拖放一个没有 `<StackLayout>` 块的 `<GridLayout>` 组件。<br/> 组件的默认代码创建的是一个彩色的显示元素定位以及合并网格单元的格的表格。
5. 删除 `<GridLayout>` 块的所有 `<Label>` 组件。
6. 配置 `<StackLayout>`：
    * 删除背景颜色
    * 设置长框
7. 配置 `<GridLayout>`：
    * 将网格设置为两列和一行.
    * 将单元格的宽度为 100% 占满整屏的宽度。
    * 将单元格的高度设置为 25%。另外，稍后要添加的 `<ListView>` 可能与 `<GridLayout>` 重叠。
    * 删除单元格的额外的设置。
8. 拖放一个 `<TextField>` 组件和一个 `<Button>` 组件。<br/> Playground 第一次将 JavaScript 代码添加到代码中。在 `<script>` 块内增加 `data()` 和 `methods` 两部份内容。在下一步的操作中，你需要为实现应用程序的功能添加新的代码。
9. 在单元格内拖放一个 `<ListView>` 组件。<br/> 组件的默认代码会创建一个使用 `<FlexboxLayout>` 组件放置国旗图标的国家列表。
10. 配置单元格里元素的位置：
    * 将 `<TextField>` 放置于第一列第一行。
    * 将 `<Button>` 放置于第二列第一行
11. 配置 `<TextField>`：
    * 将 editable 属性设置为可编辑。
    * 可用 `Return` 键添加任务。
12. 处理以及配置 `<ListView>`：
    * 移除组件里除 `<Label>` 组件外的所有嵌套的块。
    * 将其高度设置为 75%。另外 `<ListView>` 可能会与 `<GridLayout>` 重叠。
    * 将绑定与国家有关的数组替换为绑定你的活动任务数组。
    * 在 `<script>` 块中，删除 countries 数组，然后创建一个关于活动任务的空数组。
13. `<scripts>` 块中有关按钮逻辑的开发：
    * 在控制台中记录新添加的任务。
    * 将最新添加的任务添加到活动任务数组中， 使用 `unshift` 将新添加的任务放置在数组的第一个。 
    * 输入完成后清除文本框内容。
14. 使用 `<ListView>` 中的 `<Label>` 列出屏幕上新添加的任务。

以上操作全部完成，那么你的 `<HelloWorld.vue>` 内容与如下内容大致类似：

```HTML
<template>
  <Page class="page">
    <ActionBar title="My Tasks" class="action-bar" />

    <TabView height="100%">
      <TabViewItem title="To Do">
        <!-- Positions an input field, a button, and the list of tasks in a vertical stack. -->
        <StackLayout orientation="vertical" width="100%" height="100%">

          <GridLayout columns="2*,*" rows="*" width="100%" height="25%">
            <!-- Configures the text field and ensures that pressing Return on the keyboard produces the same result as tapping the button. -->
            <TextField col="0" row="0" v-model="textFieldValue" hint="Type new task..." editable="true" @returnPress="onButtonTap" /> 

            <Button col="1" row="0" text="Add task" @tap="onButtonTap" />
          </GridLayout>

          <ListView class="list-group" for="todo in todos" @itemTap="onItemTap" style="height:75%">
            <v-template>
              <Label :text="todo.name" class="list-group-item-heading" />
            </v-template>
          </ListView>
        </StackLayout>
      </TabViewItem>
      <TabViewItem title="Completed">
        <Label text="This tab will list completed tasks for tracking." textWrap="true" />
      </TabViewItem>
    </TabView>
  </Page>
</template>

<script>
export default {
  methods: {
    onItemTap: function(args) {
      console.log('Item with index: ' + args.index + ' tapped');
    },

    onButtonTap() {
      console.log("New task added: " + this.textFieldValue + "."); // Logs the newly added task in the console for debugging.
      this.todos.unshift({ name: this.textFieldValue }); // Adds tasks in the ToDo array. Newly added tasks are immediately shown on the screen.
      this.textFieldValue = ""; // Clears the text field so that users can start adding new tasks immediately.
    },
  },

  data() {
    return {
      todos: [],

      textFieldValue: "",

    };
  },
}
</script>

<style scoped>
.home-panel {
  vertical-align: center;
  font-size: 20;
  margin: 15;
}

.description-label {
  margin-bottom: 15;
}
</style>
```

## 基本功能：选项卡中查看、完成和删除任务

### 分段进行

在本节中将介绍应用功能开始和最终的实现。

| 第一栏 - 添加任务 | 第一栏 - 已添加的任务 | 第二栏 - 完成的任务
|-----|-------------|-------|
| ![First tab with added tasks](/screenshots/ns-playground/added-tasks.jpg) | ![Action dialog toggled](/screenshots/ns-playground/active-task-dialog.jpg) | ![Second tab with completed tasks](/screenshots/ns-playground/completed-tasks.jpg) |

### NativeScript部分

`<ListView>` 组件可以检测到每个子项的点击手势，并为抛出其一个事件。当前事件带有关于当前点击的数组的索引以及当前数组本身的信息。你可以绑定一个弹框事件，为其配置点击事件结果以及扩展应用程序的功能。

[`dialogs`](https://docs.nativescript.org/api-reference/modules/_ui_dialogs_) 是一个全局的可用模块，为应用程序提供多个可配置的弹框类型，例如： 警告、操作、提示、登录、确认。当前需求实现依赖于 [`action()`](/en/docs/elements/dialogs/action) 弹框让用户选择标记完成任务或是从当前的活动任务删除某一项内容。

### 需求实现

1. 在第二个 `<TabViewItem>` 块，删除 `<Label>` 元素。拖放一个 `<ListView>` 元素，处理其内容并为其设置高度。
2. 在新添加的 `<ListView>` 元素中展示任务数组中已完成的任务 (即：`dones`) 的内容。

  ```HTML
  <ListView class="list-group" for="done in dones" @itemTap="onDoneTap" style="height:75%">
    <v-template>
      <Label :text="done.name" class="list-group-item-heading" />
    </v-template>
  </ListView>
  ```
1. 修改 `onItemTap` 事件：
  * 显示一个 `action()`弹框。
  * 在控制台中记录用户选择的内容以进行调试。
  * 基于用户的选择，此方法将 `todos` 数组的元素移到 `dones` 数组中，然后删除 `todos` 数组中的元素或是关闭弹框。使用 `splice()` 方法避免出现空数组、使用 `unshift()` 方法确保最近完成的任务显示在最前面。

  ```JavaScript
  onItemTap: function(args) {
    action('What do you want to do with this task?', 'Cancel', ['Mark completed', 'Delete forever']) 
      .then(result => { 
        console.log(result); // Logs the selected option for debugging.
        switch (result) {
          case 'Mark completed': 
            this.dones.unshift(args.item); // Places the tapped active task at the top of the completed tasks.
            this.todos.splice(args.index, 1); // Removes the tapped active  task.
            break;
          case 'Delete forever':
            this.todos.splice(args.index, 1); // Removes the tapped active task.
            break; 
          case 'Cancel' || undefined: // Dismisses the dialog
            break; 
        }
      })
  },
  ```

以上操作全部完成，那么你的 `<HelloWorld.vue>` 内容与如下内容大致类似：

```HTML
<template>
  <Page class="page">
    <ActionBar title="My Tasks" class="action-bar" />

    <TabView height="100%">
      <TabViewItem title="To Do">
        <!-- Positions an input field, a button, and the list of tasks in a vertical stack. -->
        <StackLayout orientation="vertical" width="100%" height="100%">

          <GridLayout columns="2*,*" rows="*" width="100%" height="25%">
            <!-- Configures the text field and ensures that pressing Return on the keyboard produces the same result as tapping the button. -->
            <TextField col="0" row="0" v-model="textFieldValue" hint="Type new task..." editable="true" @returnPress="onButtonTap" />
            <Button col="1" row="0" text="Add task" @tap="onButtonTap" />
          </GridLayout>

          <ListView class="list-group" for="todo in todos" @itemTap="onItemTap" style="height:75%">
            <v-template>
              <Label :text="todo.name" class="list-group-item-heading" />
            </v-template>
          </ListView>
        </StackLayout>
      </TabViewItem>
      <TabViewItem title="Completed">
        <ListView class="list-group" for="done in dones" @itemTap="onItemTap" style="height:75%">
          <v-template>
            <Label :text="done.name" class="list-group-item-heading" />
          </v-template>
        </ListView>
      </TabViewItem>
    </TabView>
  </Page>
</template>

<script>
export default {
  methods: {
    onItemTap: function(args) {
      action('What do you want to do with this task?', 'Cancel', ['Mark completed', 'Delete forever']) 
        .then(result => { 
          console.log(result); // Logs the selected option for debugging.
          switch (result) {
            case 'Mark completed': 
              this.dones.unshift(args.item); // Places the tapped active task at the top of the completed tasks.
              this.todos.splice(args.index, 1); // Removes the tapped active  task.
              break;
            case 'Delete forever':
              this.todos.splice(args.index, 1); // Removes the tapped active task.
              break; 
            case 'Cancel' || undefined: // Dismisses the dialog.
              break; 
          }
        })
    },

    onButtonTap() {
      console.log("New task added: " + this.textFieldValue + "."); // Logs the newly added task in the console for debugging.
      this.todos.unshift({
          name: this.textFieldValue
      }); // Adds tasks in the ToDo array. Newly added tasks are immediately shown on the screen.
      this.textFieldValue = ""; // Clears the text field so that users can start adding new tasks immediately.
    },
  },

  data() {
    return {
      dones: [],
      todos: [],
      textFieldValue: "",
    };
  },
}
</script>

<style scoped>
.home-panel {
  vertical-align: center;
  font-size: 20;
  margin: 15;
}

.description-label {
  margin-bottom: 15;
}
</style>
```

## 基本功能： 返回活动任务，并从“已完成”选项卡中删除任务

### 分段进行

在本节中将介绍应用功能开始和最终的实现。

| 第二栏 - 已完成的任务 | 第二栏 - 已添加的任务 | 第一栏 - 活动任务
|-----|-------------|-----|
| ![Second tab with completed tasks](/screenshots/ns-playground/completed-tasks-2.jpg) | ![Action dialog toggled](/screenshots/ns-playground/completed-tasks-dialog.jpg) | ![First tab with active tasks](/screenshots/ns-playground/completed-tasks-moved-to-active.jpg)

### NativeScript 部分

当前实现步骤不需要任何额外的知识。

### 需求实现

创建和修改第二栏的 `onDoneTap` 方法：

* 显示一个 `action()` 弹框。
* 在控制台中记录用户选择的内容以进行调试。
* 基于用户的选择，此方法将 `todos` 数组的元素移到 `dones` 数组中，然后删除 `todos` 数组中的元素或是关闭弹框。使用 `splice()` 方法避免出现空数组、使用 `unshift()` 方法确保最近完成的任务显示在最前面。

  ```JavaScript
  onDoneTap: function(args) { 
    action('What do you want to do with this task?', 'Cancel', ['Mark to do', 'Delete forever'])
      .then(result => { 
        console.log(result); // Logs the selected option for debugging. 
        switch (result) { 
          case 'Mark to do':
            this.todos.unshift(args.item); // Places the tapped completed task at the top of the to do tasks. 
            this.dones.splice(args.index,1); // Removes the tapped completed task. 
            break; 
          case 'Delete forever': 
            this.dones.splice(args.index, 1); // Removes the tapped completed task. 
            break; 
          case 'Cancel' || undefined: // Dismisses the dialog 
            break; 
        } 
      }) 
  },
  ```

以上操作全部完成，那么你的 `<HelloWorld.vue>` 内容与如下内容大致类似：

```HTML
<template>
  <Page class="page">
    <ActionBar title="My Tasks" class="action-bar" />

    <TabView height="100%">
      <TabViewItem title="To Do">
        <!-- Positions an input field, a button, and the list of tasks in a vertical stack. -->
        <StackLayout orientation="vertical" width="100%" height="100%">

          <GridLayout columns="2*,*" rows="*" width="100%" height="25%">
            <TextField col="0" row="0" v-model="textFieldValue" hint="Type new task..." editable="true" @returnPress="onButtonTap" />
            <!-- Configures the text field and ensures that pressing Return on the keyboard produces the same result as tapping the button. -->
            <Button col="1" row="0" text="Add task" @tap="onButtonTap" />
          </GridLayout>

          <ListView class="list-group" for="todo in todos" @itemTap="onItemTap" style="height:75%">
            <v-template>
              <Label :text="todo.name" class="list-group-item-heading" />
            </v-template>
          </ListView>
        </StackLayout>
      </TabViewItem>
      <TabViewItem title="Completed">
        <ListView class="list-group" for="done in dones" @itemTap="onDoneTap" style="height:75%">
          <v-template>
            <Label :text="done.name" class="list-group-item-heading" />
          </v-template>
        </ListView>
      </TabViewItem>
    </TabView>
  </Page>
</template>

<script>
export default {
  methods: {
    onItemTap: function(args) {
     action('What do you want to do with this task?', 'Cancel', ['Mark completed', 'Delete forever']) 
      .then(result => { 
        console.log(result); // Logs the selected option for debugging.
        switch (result) {
          case 'Mark completed': 
            this.dones.unshift(args.item); // Places the tapped active task at the top of the completed tasks.
            this.todos.splice(args.index, 1); // Removes the tapped active  task.
            break;
          case 'Delete forever':
            this.todos.splice(args.index, 1); // Removes the tapped active task.
            break; 
          case 'Cancel' || undefined: // Dismisses the dialog
            break; 
        }
      })
    },

   onDoneTap: function(args) { 
    action('What do you want to do with this task?', 'Cancel', ['Mark to do', 'Delete forever'])
      .then(result => { 
        console.log(result); // Logs the selected option for debugging. 
        switch (result) { 
          case 'Mark to do':
            this.todos.unshift(args.item); // Places the tapped completed task at the top of the to do tasks. 
            this.dones.splice(args.index,1); // Removes the tapped completed task. 
            break; 
          case 'Delete forever': 
            this.dones.splice(args.index, 1); // Removes the tapped completed task. 
            break; 
          case 'Cancel' || undefined: // Dismisses the dialog 
            break; 
        } 
      }) 
    },

    onButtonTap() {
      console.log("New task added: " + this.textFieldValue + "."); // Logs the newly added task in the console for debugging.
      this.todos.unshift({
        name: this.textFieldValue
      }); // Adds tasks in the ToDo array. Newly added tasks are immediately shown on the screen.
      this.textFieldValue = ""; // Clears the text field so that users can start adding new tasks immediately.
    },
  },

  data() {
    return {
      dones: [],
      todos: [],
      textFieldValue: "",
    };
  },
}
</script>

<style scoped>
.home-panel {
  vertical-align: center;
  font-size: 20;
  margin: 15;
}

.description-label {
  margin-bottom: 15;
}
</style>
```

## 进阶功能: 自定义输入框和按钮样式

### 分段进行

在本节中将介绍应用功能开始和最终的实现。

| Tab 1 - No style | Tab 1 - Styled | Tab 1 - Styled |
|-----|-------------|----|
| ![Unstyled input](/screenshots/ns-playground/input-field.jpg) | ![Styled button](/screenshots/ns-playground/styled-button.jpg) | ![Styled input](/screenshots/ns-playground/styled-input.jpg) |

### NativeScript 部分

当你使用 NativeScript 以及 Vue.js 开发应用时，你可以在应用程序中使用应用程序范围的 CSS、局部 CSS、行内 CSS。Application-wide CSS 是最先引入的，由项目的根路径的 `app.css` 控制的。具体的教程可以查看 [Styling](https://docs.nativescript.org/ui/styling)。

局部 CSS只作用于当前的组件，仅由 `HelloWorld.vue` 内的 `<style scoped>` 块控制。当前教程只是就局部样式和行内样式说明，详情查看 [Scoped CSS](https://vue-loader.vuejs.org/guide/scoped-css.html)。

带类型的选择器，你可以选择一个 UI 组件并将样式应用于在当前选择器。选择一种类型，可以使用代码中提供的组件名称。举个例子，若需要选择一个 Tab 视图，可以使用 `TabView`。

### 需求实现

#### 文本输入框样式

在 `HelloWorld.vue` 下的 `<style scoped>`，改变文字大小、颜色、以及 `<TextField>` 周围的边距。

```CSS
TextField {
  font-size: 20;
  color: #53ba82;
  margin-top: 10;
  margin-bottom: 10;
  margin-right: 5;
  margin-left: 20;
}
```

#### 按钮样式

在 `<style scoped>` 块中，为按钮创建一个样式。设置按钮的背景颜色和圆角。

  ```CSS
  Button { 
    font-size: 20; 
    font-weight: bold; 
    color: white; 
    background-color: #53ba82; 
    height: 40;
    margin-top: 10; 
    margin-bottom: 10; 
    margin-right: 10; 
    margin-left: 10; 
    border-radius: 20px; 
  }
  ```
  
## 进阶功能: 自定义导航栏样式

### 分段进行

在本节中将介绍应用功能开始和最终的实现。

| Tabs - No style | Tabs Styled 
|-----|-------------|
| ![Unstyled tabs](/screenshots/ns-playground/styled-button.jpg) | ![Styled tabs](/screenshots/ns-playground/styled-tabs.jpg) |

### NativeScript 部分

`<TabView>` 组件提供一些现成的样式属性。你可以通过 `textTransform` 属性修改选项栏的标题、通过 `tabTextFontSize`、 `tabTextColor`、 `selectedTabTextColor` 修改全局的字体大小和颜色，通过 `tabBackgroundColor` 修改选项卡背景颜色。

### 需求实现

#### 修改选中选项卡的字体颜色和大小。

在 `HelloWorld.vue` 组件中，为 `<TabView>` 添加 `selectedTabTextColor` 以及 `tabTextFontSize` 属性。

```HTML
<TabView height="100%" selectedTabTextColor="#53ba82" tabTextFontSize="15" >
```

#### 修改文本内容

`textTransform` 属性仅能应用于 `<TabViewItem>` 选项卡中。

```HTML
<TabViewItem title="To Do" textTransform="uppercase" >
```

```HTML
<TabViewItem title="Completed" textTransform="uppercase">
```

## 进阶功能: 自定义活动任务样式

在本节中将介绍应用功能开始和最终的实现。

| Active tasks - No style | Active tasks - no separator | Active tasks - styled active tasks |
|-----|-------------|---|
| ![Unstyled active tasks](/screenshots/ns-playground/styled-tabs.jpg) | ![No separator](/screenshots/ns-playground/styled-list-view-no-separator.jpg) | ![Styled list](/screenshots/ns-playground/styled-list-view-added-tasks.jpg) |

### NativeScript 部分

`<ListView>` 和 `<Label>` 有一些自带的样式属性，你可以在 `<template>` 块中用这些属性控制元素的列表分隔或是文本换行。另外需要在 `<style scoped>` 块中设置 CSS 改变字体样式、颜色、以及文本定位。

想要实现活动任务有特别的样式，可以为 `<Label>` 元素设置 `id` 属性。

### 需求实现

1. 为 `<Label>` 设置 `id` 属性表示活动任务以及文本换行。设置文本换行可以保证过长的文本也能够恰当的显示在列表中。

  ```HTML
  <Label id="active-task" :text="todo.name" class="list-group-item-heading" />
  ```
2. 为 `<ListView>` 设置 `separatorColor` 属性为 `transparent` 显示活动任务。通过这种方式可以让分隔符将不再出现在列表中。

  ```HTML
  <ListView class="list-group" for="todo in todos" @itemTap="onItemTap" style="height:75%" separatorColor="transparent" >
  ```
3. 在 `<style scoped>` 块中为活动任务创建一个样式，设置字体大小、颜色以及填充尺寸。调整边距和填充直至得到一个满意的结果。

  ```CSS
  #active-task {
    font-size: 20;
    font-weight: bold;
    color: #53ba82;
    margin-left: 20;
    padding-top: 5;
    padding-bottom: 10;
  }
  ```

## 进阶功能: 自定义已完成任务样式

在本节中将介绍应用功能开始和最终的实现。

| Completed tasks - No style | Completed tasks - Styled | 
|-----|-------------|
| ![Unstyled completed tasks](/screenshots/ns-playground/completed-tasks-unstyled.jpg) | ![Styled completed tasks](/screenshots/ns-playground/completed-tasks-styled.jpg) |

### NativeScript 部分

本节应用一些 NativeScript 的知识主要来自 [进阶功能: 自定义活动任务样式](#advanced-design-styled-active-tasks)。

### 需求实现

1. Set an `id` for the `<Label>` that represents completed tasks and enable text wrapping. Enabling text wrapping ensures that longer text shows properly in your list

1. 为 `<Label>` 设置 `id` 属性表示已完成的任务以及文本换行。设置文本换行可以保证过长的文本也能够恰当的显示在列表中。

  ```HTML
  <Label id="completed-task" :text="done.name" class="list-group-item-heading" />
  ```
2. 为 `<ListView>` 设置 `separatorColor` 属性为 `transparent` 显示已完成的任务。通过这种方式可以让分隔符将不再出现在列表中。

  ```HTML
  <ListView id="completed-list" class="list-group" for="done in dones" @itemTap="onDoneTap" style="height:75%" separatorColor="transparent">
  ```

3. 在 `<style scoped>` 块中为已完成的任务创建一个样式，设置字体大小、颜色以及填充尺寸。调整边距和填充直至得到一个满意的结果。

  ```CSS
  #completed-task {
    font-size: 20;
    color: #d3d3d3;
    margin-left: 20;
    padding-top: 5;
    padding-bottom: 10;
    text-decoration: line-through;
  }
  ```