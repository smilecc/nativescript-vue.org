---
title: 停靠式布局(DockLayout)
apiRef: https://docs.nativescript.org/api-reference/modules/_ui_layouts_dock_layout_
contributors: [smilecc]
---

`<DockLayout>` 是一个可以让你使子元素停靠在布局边缘或中间的布局容器。

`<DockLayout>` 具有以下行为：

* 使用 `dock` 属性可以使它的子元素停靠在布局的左（`left`）、右（`right`）、上（`top`）、下（`bottom`）或中间。<br/>如果需要使某个子元素停靠在布局中间，那么该子元素必须是容器的 **最后一个子元素**，而且你必须将父元素的 `stretchLastChild` 属性设为 `true`。
* 会强制约束其子元素的布局。
* 当其大小在运行中被改变时，会影响其子项的大小。

## 示例

### 停靠子元素，并使最后一个子元素不被拉伸

下面的例子构建了一个像是画框一样的布局，使 4 个元素分别位于屏幕的四个边缘。

```html
<DockLayout stretchLastChild="false" backgroundColor="#3c495e">
  <Label text="left" dock="left" width="40" backgroundColor="#43b883"/>
  <Label text="top" dock="top" height="40" backgroundColor="#289062"/>
  <Label text="right" dock="right" width="40" backgroundColor="#43b883"/>
  <Label text="bottom" dock="bottom" height="40" backgroundColor="#289062"/>
</DockLayout>
```
<img class="md:w-1/2 lg:w-1/3" src="https://art.nativescript-vue.org/layouts/dock_layout_no_stretch.svg" />

### 停靠子元素，并拉伸最后一个子元素

下面的实例展示了 `stretchLastChild` 是如何影响子元素在 `DockLayout` 容器中的位置的，最后一个元素（`bottom`）将占据所有的剩余空间。

```html
<DockLayout stretchLastChild="true" backgroundColor="#3c495e">
  <Label text="left" dock="left" width="40" backgroundColor="#43b883"/>
  <Label text="top" dock="top" height="40" backgroundColor="#289062"/>
  <Label text="right" dock="right" width="40" backgroundColor="#43b883"/>
  <Label text="bottom" dock="bottom" backgroundColor="#1c6b48"/>
</DockLayout>
```
<img class="md:w-1/2 lg:w-1/3" src="https://art.nativescript-vue.org/layouts/dock_layout_stretch.svg" />

### 停靠在中心与每一侧

在下面的示例中，我们在 `<DockLayout>` 中创建了 5 个元素，最后一个元素被前 4 个元素包裹在中心。

```html
<DockLayout stretchLastChild="true" backgroundColor="#3c495e">
  <Label text="left" dock="left" width="40" backgroundColor="#43b883"/>
  <Label text="top" dock="top" height="40" backgroundColor="#289062"/>
  <Label text="right" dock="right" width="40" backgroundColor="#43b883"/>
  <Label text="bottom" dock="bottom" height="40" backgroundColor="#289062"/>
  <Label text="center" backgroundColor="#1c6b48" />
</DockLayout>
```
<img class="md:w-1/2 lg:w-1/3" src="https://art.nativescript-vue.org/layouts/dock_layout_all_sides_and_stretch.svg" />

### 在同一侧停靠多个元素

在下面的示例中，我们创建了一个包含 4 个元素的行，这些元素将会伸展至整个屏幕的宽高。
 
```html
<DockLayout stretchLastChild="true" backgroundColor="#3c495e">
  <Label text="left 1" dock="left" width="40" backgroundColor="#43b883"/>
  <Label text="left 2" dock="left" width="40" backgroundColor="#289062"/>
  <Label text="left 3" dock="left" width="40" backgroundColor="#1c6b48"/>
  <Label text="last child" backgroundColor="#43b883"/>
</DockLayout>
```
<img class="md:w-1/2 lg:w-1/3" src="https://art.nativescript-vue.org/layouts/dock_layout_multiple_on_same_side.svg" />

## 属性（Props）

| 名称 | 类型 | 描述 |
|------|------|-------------|
| `stretchLastChild` | `Boolean` | 允许或禁止最后一个元素在剩余可用空间上进行伸展。

## 子元素附加属性（Props）

当元素直接作为 `<DockLayout>` 的子元素时，你可以使用以下附加属性。

| 名称 | 类型 | 描述 |
|------|------|-------------|
| `dock` | `String` | 指定元素停靠在哪一侧边。<br/>可使用的值： `top`、`right`、`bottom` 或 `left`。
