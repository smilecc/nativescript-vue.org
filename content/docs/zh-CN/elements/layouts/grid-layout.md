---
title: 网格布局(GridLayout)
apiRef: https://docs.nativescript.org/api-reference/modules/_ui_layouts_grid_layout_
contributors: [smilecc]
---

`<GridLayout>` 是一个可以让你以表格形式来排列子元素的布局容器。

网格以行、列以及单元格组成。一个单元格可以横跨多行或多列，它可以包含多个子元素，这些子元素可以横跨多行或列，甚至可以互相重叠。

默认情况下，`<GridLayout>` 拥有一行和一列，你可以通过配置 `rows` 和 `columns` 属性来设置他们的行数和列数以及它们的宽高。

使用逗号分隔的方式列出宽度可以设置列出列的宽度和列的数量，例如 `columns="100, 100, 100"`，则设置列数为 3，每列宽度为 100。`rows` 的使用方式同理。

你可以给列或行的宽高设置一个固定值，也可以使用响应式：

* **数字：** 设置一个固定值。
* **auto：** 使列与其最宽的列一样宽，或使其行与其最高的行一样高。
* **\*：** 在其他所有自动或固定值的列或行填充之后，会占据尽可能大的空间。

详情请参阅 [属性（props）](#属性（props）)。

## 示例

### 固定大小的网格布局

下面的示例创建了一个 2 * 2 的具有固定列宽和行高的网格。

```html
<GridLayout columns="115, 115" rows="115, 115">
  <Label text="0,0" row="0" col="0" backgroundColor="#43b883"/>
  <Label text="0,1" row="0" col="1" backgroundColor="#1c6b48"/>
  <Label text="1,0" row="1" col="0" backgroundColor="#289062"/>
  <Label text="1,1" row="1" col="1" backgroundColor="#43b883"/>
</GridLayout>
```
<img class="md:w-1/2 lg:w-1/3" src="https://art.nativescript-vue.org/layouts/grid_layout.svg" />

### 使用星号(*)的网格布局

下面的示例创建了一个具有响应式设计的网格，它的子元素大小根据所提供的比例布局。

```html
<GridLayout columns="*, 2*" rows="2*, 3*" backgroundColor="#3c495e">
  <Label text="0,0" row="0" col="0" backgroundColor="#43b883"/>
  <Label text="0,1" row="0" col="1" backgroundColor="#1c6b48"/>
  <Label text="1,0" row="1" col="0" backgroundColor="#289062"/>
  <Label text="1,1" row="1" col="1" backgroundColor="#43b883"/>
</GridLayout>
```
<img class="md:w-1/2 lg:w-1/3" src="https://art.nativescript-vue.org/layouts/grid_layout_star_sizing.svg" />

### 具有固定和自动大小的网格布局

以下示例使用一个自动调整大小的列和一个具有固定大小的列创建了一个网格，它的行具有固定高度。

```html
<GridLayout columns="80, auto" rows="80, 80" backgroundColor="#3c495e">
  <Label text="0,0" row="0" col="0" backgroundColor="#43b883"/>
  <Label text="0,1" row="0" col="1" backgroundColor="#1c6b48"/>
  <Label text="1,0" row="1" col="0" backgroundColor="#289062"/>
  <Label text="1,1" row="1" col="1" backgroundColor="#43b883"/>
</GridLayout>
```
<img class="md:w-1/2 lg:w-1/3" src="https://art.nativescript-vue.org/layouts/grid_layout_fixed_auto.svg" />

### 具有混合大小和合并单元格的网格布局

以下示例创建了一个具有响应式设计、混合宽高设置以及一些合并单元格的复杂网格。

```html
<GridLayout columns="40, auto, *" rows="40, auto, *" backgroundColor="#3c495e">
  <Label text="0,0" row="0" col="0" backgroundColor="#43b883"/>
  <Label text="0,1" row="0" col="1" colSpan="2" backgroundColor="#1c6b48"/>
  <Label text="1,0" row="1" col="0" rowSpan="2" backgroundColor="#289062"/>
  <Label text="1,1" row="1" col="1" backgroundColor="#43b883"/>
  <Label text="1,2" row="1" col="2" backgroundColor="#289062"/>
  <Label text="2,1" row="2" col="1" backgroundColor="#1c6b48"/>
  <Label text="2,2" row="2" col="2" backgroundColor="#43b883"/>
</GridLayout>
```
<img class="md:w-1/2 lg:w-1/3" src="https://art.nativescript-vue.org/layouts/grid_layout_complex.svg" />

## 属性（Props）

| 名称 | 类型 | 描述 |
|------|------|-------------|
`columns` | `String` | 一个以逗号分隔的列宽的字符串。<br/>可用的值：数字、`auto` 或 `*`。<br/>数字表示一个固定的列宽，`auto` 可使其和水平方向最宽的子项一样宽，而 `*` 可使其占据所有可用的空间。可用的空间将会被具有星号的列按比例占据，例如 `3*` 和 `5*` 代表其尺寸的比例为 3:5。
`rows` | `String` | 一个以逗号分隔的行高的字符串。<br/>可用的值：数字、`auto` 或 `*`。<br/>数字表示一个固定的行高，`auto` 可使其和垂直方向最高的子项一样高，而 `*` 可使其占据所有可用的空间。可用的空间将会被具有星号的行按比例占据，例如 `3*` 和 `5*` 代表其尺寸的比例为 3:5。

## 子元素附加属性（Props）

当元素直接作为 `<GridLayout>` 的子元素时，你可以使用以下附加属性。

| 名称 | 类型 | 描述 |
|------|------|-------------|
`row` | `Number` | 指定当前元素所在的行，需要与 `col` 属性结合使用，用于指定元素的单元格坐标。<br/>第一行以 `0` 开始。
`col` | `Number` | 指定当前元素所在的列，需要与 `row` 属性结合使用，用于指定元素的单元格坐标。<br/>第一列以 `0` 开始。
`rowSpan` | `Number` | 指定此元素跨越的行数。
`colSpan` | `Number` | 指定此元素跨越的列数。