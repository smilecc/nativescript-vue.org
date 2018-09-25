---
title: 弹性布局(FlexboxLayout)
apiRef: https://docs.nativescript.org/api-reference/modules/_ui_layouts_flexbox_layout_
contributors: [smilecc]
---

`<FlexboxLayout>` 是一个提供了 [CSS Flexbox 布局](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Flexbox) 的非完全实现的布局容器，此布局允许你水平或垂直排列子组件。

## 示例

### 默认 flex 布局

以下示例创建一行三个大小相等的元素，这些元素的高度与屏幕的高度相同。

```html
<FlexboxLayout backgroundColor="#3c495e">
  <Label text="first" width="70" backgroundColor="#43b883"/>
  <Label text="second" width="70" backgroundColor="#1c6b48"/>
  <Label text="third" width="70" backgroundColor="#289062"/>
</FlexboxLayout>
```
<img class="md:w-1/2 lg:w-1/3" src="https://art.nativescript-vue.org/layouts/flexbox_layout_row_stretch.svg" />

### 列的 flex 布局

以下示例创建一列三个大小相等的元素，这些元素的宽度与屏幕的宽度相同。

```html
<FlexboxLayout flexDirection="column" backgroundColor="#3c495e">
  <Label text="first" height="70" backgroundColor="#43b883"/>
  <Label text="second" height="70" backgroundColor="#1c6b48"/>
  <Label text="third" height="70" backgroundColor="#289062"/>
</FlexboxLayout>
```
<img class="md:w-1/2 lg:w-1/3" src="https://art.nativescript-vue.org/layouts/flexbox_layout_column_stretch.svg" />

### 行 flex 布局，子项以 `flex-start` 对齐

以下示例在屏幕顶部创建了三个元素，以在代码中的顺序排列。

```html
<FlexboxLayout alignItems="flex-start" backgroundColor="#3c495e">
  <Label text="first" width="70" height="70" backgroundColor="#43b883"/>
  <Label text="second" width="70" height="70" backgroundColor="#1c6b48"/>
  <Label text="third" width="70" height="70" backgroundColor="#289062"/>
</FlexboxLayout>
```
<img class="md:w-1/2 lg:w-1/3" src="https://art.nativescript-vue.org/layouts/flexbox_layout_row_flex-start.svg" />

### 行 flex 布局，自定义排列顺序

以下示例在屏幕顶部创建了三个元素，以自定义的顺序排列。

```html
<FlexboxLayout alignItems="flex-start" backgroundColor="#3c495e">
  <Label text="first" order="2" width="70" height="70" backgroundColor="#43b883"/>
  <Label text="second" order="3" width="70" height="70" backgroundColor="#1c6b48"/>
  <Label text="third" order="1" width="70" height="70" backgroundColor="#289062"/>
</FlexboxLayout>
```
<img class="md:w-1/2 lg:w-1/3" src="https://art.nativescript-vue.org/layouts/flexbox_layout_row_custom_order.svg" />

### 启用换行的行 flex 布局

以下示例创建了 4 个启用换行的元素，当前行的空间不足时，该容器会使最后一项换到新的一行。

```html
<FlexboxLayout flexWrap="wrap" backgroundColor="#3c495e">
  <Label text="first" width="30%" backgroundColor="#43b883"/>
  <Label text="second" width="30%" backgroundColor="#1c6b48"/>
  <Label text="third" width="30%" backgroundColor="#289062"/>
  <Label text="fourth" width="30%" backgroundColor="#289062"/>
</FlexboxLayout>
```
<img class="md:w-1/2 lg:w-1/3" src="https://art.nativescript-vue.org/layouts/flexbox_layout_wrap.svg" />

### 逆排列且元素以 `alignSelf` 对齐的列 flex 布局

以下示例演示了如何使用：

* `flexDirection` 让元素在列中自下到上排列。
* `justifyContent` 在纵向排列的元素之间增加相同的间距。
* `alignSelf` 修改元素在主轴上的位置。

```html
<FlexboxLayout flexDirection="column-reverse"
               justifyContent="space-around" backgroundColor="#3c495e">
  <Label text="first" height="70" backgroundColor="#43b883"/>
  <Label text="second" alignSelf="center" width="70" height="70" backgroundColor="#1c6b48"/>
  <Label text="third\nflex-end" alignSelf="flex-end" width="70" height="70" backgroundColor="#289062"/>
  <Label text="fourth" height="70" backgroundColor="#289062"/>
</FlexboxLayout>
```
<img class="md:w-1/2 lg:w-1/3" src="https://art.nativescript-vue.org/layouts/flexbox_layout_column_reverse_space_around_align_self.svg" />

## 属性（Props）

> **译者注：**这部分非常难翻译，也非常难理解。
>
> 在下文的翻译中主轴代表 `main axis`，一般意为水平轴；交叉轴代表 `cross axis`，一般意为垂直轴。
> 
> 如果你不能理解下文，请结合 CSS 中的 flex 布局理解，或参阅 [阮一峰的 Flex 布局教程](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html) 中的说明与图解。

| 名称 | 类型 | 描述 |
|------|------|-------------|
`flexDirection` | `String` | 设置子元素在 flexbox 容器中的方向。<br/>可用的值：<br/>`row` （水平方向，从左到右），<br/>`row-reverse` （水平方向，从右到左），<br/>`column` （垂直方向，从上到下），<br/>`column-reverse` （垂直方向，从下到上）。<br/>默认值： `row`.
`flexWrap` | `String` | 设置子元素是强制在一行中还是允许多行。如果设置为允许多行，则还需要定义新行在主轴上水平堆叠的方向。<br/>可用的值：<br/>`nowrap` （单行，但是可能会导致容器溢出），<br/>`wrap` （多行，方向由 `flexDirection` 定义），<br/>`wrap-reverse` （多行，方向与 `flexDirection` 定义的相反）。<br/>默认值：`nowrap`。
`justifyContent` | `String` |  设置子元素在主轴上的对齐方式，你可以使用它来分配一行上元素的剩余空间，当内容超出当前行时，你也可以用它来定义超出部分的对齐方式。<br/>可用的值：<br/>`flex-start` （左对齐），<br/>`flex-end` （右对齐），<br/>`center` （居中对齐），<br/>`space-between` （两端对齐，项目之间的间隔都相等，第一个元素位于行首，最后一个元素位于行尾），<br/>`space-around` （每个项目两侧的间隔相等）<br/>默认值： `flex-start`。
`alignItems` | `String` | （**仅安卓可用**）设置子元素在当前行上交叉轴的对齐方式，就像是 `justifyContent` 在交叉轴上的作用。<br/>可用的值：<br/>`flex-start` （交叉轴的起点对齐），<br/>`flex-end` （交叉轴的终点对齐），<br/>`center` （交叉轴的中点对齐），<br/>`baseline` （根据项目的基线对齐），<br/>`stretch` （项目会被拉伸至占满整个容器，但任然遵从 `min-width` 和 `max-width`）。<br/>默认值： `stretch`。
`alignContent` | `String` | 设置了行在 flex 容器中的交叉轴上如何对齐，类似于 `justifyContent` 在主轴上对齐元素的方式。<br/>当 flex 容器中只有一行时该属性无效。<br/>可用的值：<br/>`flex-start` （与交叉轴的起点对齐），<br/>`flex-end` （与交叉轴的终点对齐），<br/>`center` （与交叉轴的中点对齐），<br/>`space-between` （与交叉轴两端对齐，轴线之间的间隔平均分布），<br/>`space-around` （每根轴线两侧的间隔都相等），<br/>`stretch` （轴线占满整个交叉轴）。<br/>默认值：`stretch`。

## 子元素附加属性（Props）

当元素直接作为 `<FlexboxLayout>` 的子元素时，你可以使用以下附加属性。

| 名称 | 类型 | 描述 |
|------|------|-------------|
`order` | `Number` | 设置子元素之间彼此的排列顺序。
`flexGrow` | `Number` | 定义项目的放大比例。用于设置子项与 flex 容器中的其他子项的放大比例。
`flexShrink` | `Number` | 定义当空间不足时，子项的缩小比例。用于设置子项与 flex 容器中的其他子项的缩小比例，当没有指定时，默认值为 `1`。
`alignSelf` | `String` | （**仅安卓可用**） 覆盖子项  `alignItems` 的值。<br/>可用的值：<br/>`flex-start` （交叉轴的起点对齐），<br/>`flex-end` （交叉轴的终点对齐），<br/>`center` （交叉轴的中点对齐），<br/>`baseline` （根据项目的基线对齐），<br/>`stretch` （项目会被拉伸至占满整个容器，但任然遵从 `min-width` 和 `max-width`）。<br/>默认值： `stretch`。
`flexWrapBefore` | `Boolean` | 当为 `true` 时，强制项目换行。此属性不属于官方的 Flexbox 规范。<br/>默认值： `false`。
