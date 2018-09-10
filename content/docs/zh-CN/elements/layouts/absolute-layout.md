---
title: 绝对布局(AbsoluteLayout)
apiRef: https://docs.nativescript.org/api-reference/modules/_ui_layouts_absolute_layout_
docRef: https://docs.nativescript.org/ui/layouts/layout-containers#absolutelayout
contributors: [smilecc]
---

`<AbsoluteLayout>` 容器是 NativeScript 中最简单的布局容器，

`<AbsoluteLayout>` 具有以下行为：

* 使用一对绝对坐标（左和上）来定位其子项。
* 不会对其子项强制执行任何布局约束。
* 当其大小在运行中被改变时，不会调整其子项的大小。

## 示例

### 一个网格状（grid-like）布局

以下的示例中创建了一个简单的网格，如要了解更多关于如何创建网格布局的信息，请参阅[网格布局(GridLayout)](/zh-CN/docs/elements/layouts/grid-layout).

```html
<AbsoluteLayout backgroundColor="#3c495e">
  <Label text="10,10" left="10" top="10" width="100" height="100" backgroundColor="#43b883"/>
  <Label text="120,10" left="120" top="10" width="100" height="100" backgroundColor="#43b883"/>
  <Label text="10,120" left="10" top="120" width="100" height="100" backgroundColor="#43b883"/>
  <Label text="120,120" left="120" top="120" width="100" height="100" backgroundColor="#43b883"/>
</AbsoluteLayout>
```
<img class="md:w-1/2 lg:w-1/3" src="https://art.nativescript-vue.org/layouts/absolute_layout_grid.svg" />

### 元素可重叠

下面的示例中创建了一组相互重叠的元素。

```html
<AbsoluteLayout backgroundColor="#3c495e">
  <Label text="10,10" left="10" top="10" width="100" height="100" backgroundColor="#289062"/>
  <Label text="30,40" left="30" top="40" width="100" height="100" backgroundColor="#43b883"/>
</AbsoluteLayout>
```
<img class="md:w-1/2 lg:w-1/3" src="https://art.nativescript-vue.org/layouts/absolute_layout_overlap.svg" />

## 属性（Props）

无。

## 子元素附加属性（Props）

当元素直接作为 `<AbsoluteLayout>` 的子元素时，你可以使用以下附加属性。

| 名称 | 类型 | 描述 |
|------|------|-------------|
| `top` | `Number` | 获取或设置子项顶部边缘到其父项顶部边缘的距离（以像素为单位）
| `left` | `Number` | 获取或设置子项左侧边缘到其父项左侧边缘的距离（以像素为单位）
