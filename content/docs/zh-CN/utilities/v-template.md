---
title: v-template 组件
contributors: [smilecc]
---

使用 `<v-template>` 可以让你定义可重用的模板。

## 属性（Props）

| 名称 | 类型 | 描述 |
|------|------|-------------|
| `if` | `String` | 使用该模板的条件。
| `name` | `String` | 模板的名称，当忽略时则自动生成。

## 基础用法

`<v-template>` 组件常在 [ListView 组件](/zh-CN/docs/elements/components/list-view) 内部作为列表项使用。

## 进阶用法

你可以使用 `v-template` 来实现需要模板的单个或多个自定义组件。

`v-template` 当模板中没有内容时不会渲染任何内容，但是，它会向父组件添加一个 `$templates` 属性，该属性是一个 [`TemplateBag` 实例](https://github.com/nativescript-vue/nativescript-vue/blob/master/platform/nativescript/runtime/components/v-template.js#L36)。

接下来，`v-template` 会在各自的父元素中注册为 `TemplateBag` 实例的可用模板，所有父元素上已存在的 `TemplateBag` 实例都将会被重用。

### `TemplateBag` 类

`TemplateBag` 类使得你可以注册多个模板，并基于项目（item）选择正确的模板，以及为每个模板提供条件选项。

模板所存储的对象基于 [`KeyedTemplate`](https://docs.nativescript.org/api-reference/interfaces/_ui_core_view_.keyedtemplate) 接口。

#### `selectorFn` 属性

`selectorFn` 属性返回一个接受单个参数的函数，此参数用于选择符合条件的模板。

该函数通会遍历 `TemplateBag` 实例中所有已经注册的模板，并且会返回第一个符合 `if` 条件的模板，如果没有符合条件的模板，则返回 `default`。

#### 可用的方法

| 方法 | 描述 |
|---|---|
| `registerTemplate(name: String, condition: String?, scopedFn: Function): void` | _主要用于内部。_<br/>在 `TemplateBag` 实例中注册模板。<br/>该 `scopedFn` 必须是一个 [scoped slot](https://vuejs.org/v2/guide/components.html#Scoped-Slots) 渲染函数 |
| `getConditionFn(condition: String): Function` | _内部使用。_<br/>创建一个给定条件的处理函数。 |
| `getAvailable(): Array<String>` | 返回一个包含所有可用的 [`KeyedTemplates`](https://docs.nativescript.org/api-reference/interfaces/_ui_core_view_.keyedtemplate) 的数组。 (返回的是模板名称的数组) |
| `getKeyedTemplate(name: String): KeyedTemplate` | 返回 [`KeyedTemplate`](https://docs.nativescript.org/api-reference/interfaces/_ui_core_view_.keyedtemplate) 的具体名称。 |
| `getKeyedTemplates(): Array<KeyedTemplate>` | 返回一个所有已在 `TemplateBag` 中注册的 [`KeyedTemplates`](https://docs.nativescript.org/api-reference/interfaces/_ui_core_view_.keyedtemplate) 的数组。 |
| `patchTemplate(name: String, context: any, oldVnode: VNode?): View` | 使一个已经存在的 [`VNode`](https://vuejs.org/v2/guide/render-function.html#The-Virtual-DOM) 使用参数所提供的 `context`。如果未提供 `oldVnode` 参数，则为制定的模板创建一个新的 View 示例。 |
