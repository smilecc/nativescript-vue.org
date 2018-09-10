---
title: 手动路由
contributors: [smilecc]
---

在 NativeScript-Vue 中使用路由最简单的方式是使用以下函数：

* [`$navigateTo`](#navigateto)
* [`$navigateBack`](#navigateback)
* [`$showModal`](#showmodal)

> 本页面上所有的示例都是在讨论移动应用程序如何处理 `Master`（主页） 与 `Detail`（详情）之间的路由。

### `$navigateTo`

你可以在视图中或方法中调用  `$navigateTo`。

#### 在视图中

在 `Master` 组件中，使用 `data` 属性来公开 `Detail` 组件。随后可以在视图中直接通过 `$navigateTo(<propertyName>)` 来调用该方法。

```Vue
const Vue = require('nativescript-vue');

const Master = {
  template: `
    <Page>
      <ActionBar title="Master" />
      <StackLayout>
        <Button text="To Details directly" @tap="$navigateTo(detailPage)" />
      </StackLayout>
    </Page>
  `,

  data() {
    return {
      detailPage: Detail
    }
  }
};

const Detail = {
  template: `
    <Page>
      <ActionBar title="Detail"/>
      <StackLayout>
        <Label text="Details.." />
      </StackLayout>
    </Page>
  `
};

new Vue({
  render: h => h(Master)
}).$start()
```

#### 在方法中

将方法绑定到一个按钮的 `tap` 事件上，并使用 `this.$navigateTo(Detail)` 跳转到 `Detail` 组件。

```Vue
const Master = {
  template: `
    <Page>
      <ActionBar title="Master" />
      <StackLayout>
        <Button text="To Details via method" @tap="goToDetailPage" />
      </StackLayout>
    </Page>
  `,

  methods: {
    goToDetailPage() {
      this.$navigateTo(Detail);
    }
  }
};

const Detail = {
  template: `
    <Page>
      <ActionBar title="Detail"/>
      <StackLayout>
        <Label text="Details.." />
      </StackLayout>
    </Page>
  `
};
```

#### 向目标组件传递 Props

`$navigateTo` 接受第二个参数选项，你可以使用使用该参数实现如下功能:

* 设置过渡
* 传递一个带有 props 的 `context` 对象，以便在实例化目标组件时使用

例如: 

```JavaScript
this.$navigateTo(Detail, {
  transition: {},
  transitionIOS: {},
  transitionAndroid: {},
  
  context: {
    propsData: {
      foo: 'bar',
    }
  }
});
```

若要了解关于这个选项的更多信息，请参阅 [`NavigationEntry`](https://docs.nativescript.org/api-reference/interfaces/_ui_frame_.navigationentry)。

### `$navigateBack`

接下来，在 `Detail` 组件中，增加一个用来触发全局函数 `$navigateBack` 的按钮。

```Vue
const Detail = {
  template: `
    <Page>
      <ActionBar title="Detail"/>
      <StackLayout>
        <Button text="Back to Master" @tap="$navigateBack" />
      </StackLayout>
    </Page>
  `
};
```

### `$showModal`

通过使用 `$showModal` 可以让 `Detail` 以模态方式显示，这个函数的行为类似于 `$navigateTo`。

你可以在视图或方法中调用  `$showModal`。接下来，调用 `$modal.close` 则可以关闭这个模态框。

#### 在视图中

在 `Master` 组件中，使用 `data` 属性来公开 `Detail` 组件，随后可以在视图中直接通过 `$showModal(<propertyName>)` 来调用该方法。

```Vue
const Vue = require('nativescript-vue');

const Master = {
  template: `
    <Page>
      <ActionBar title="Master" />
      <StackLayout>
        <Button text="To Details directly" @tap="$showModal(detailPage)" />
      </StackLayout>
    </Page>
  `,

  data() {
    return {
      detailPage: Detail
    }
  }
};

const Detail = {
  template: `
    <Page>
      <ActionBar title="Detail"/>
      <StackLayout>
        <Button @tap="$modal.close" text="Close" />                    
      </StackLayout>
    </Page>
  `
};

new Vue({
  render: h => h(Master)
}).$start()
```

#### 在方法中

将方法绑定到一个按钮的 `tap` 事件上，并使用 `this.$showModal(Detail)` 浏览 `Detail` 组件。

```Vue
const Master = {
  template: `
    <Page>
      <ActionBar title="Master" />
      <StackLayout>
        <Button text="Show Details modally" @tap="showDetailPageModally" />
      </StackLayout>
    </Page>
  `,

  methods: {
    showDetailPageModally() {
      this.$showModal(Detail);
    }
  }
};

const Detail = {
  template: `
    <Page>
      <ActionBar title="Detail"/>
      <StackLayout>
        <Button @tap="$modal.close" text="Close" />                    
      </StackLayout>
    </Page>
  `
};
```

#### 向模态框传递 Props

`$showModal` 接受第二个参数选项，你可以使用该参数向目标组件传递一个包含 `propsData` 的 `context` 对象，例如：

```JavaScript
this.$showModal(Detail, { context: { propsData: { id: 14 }}});
```

你还需要修改 `Detail` 使之可以接收 `id` prop，你可以通过在组件中定义 `props` 来实现此操作：

```vue
const Detail = {
  props: ['id'],
  template: `
    <Page>
      <ActionBar title="Detail"/>
      <StackLayout>
        <Label :text="id" />
        <Button @tap="$modal.close" text="Close" />                    
      </StackLayout>
    </Page>
  `,
};
```
现在你可以在该组件中通过 `this.id` 访问这个 prop 了

若要了解更多关于 Props 的信息，请参阅 [Vue 官方文档](https://vuejs.org/v2/guide/components-props.html)。

#### 从模态框（modal）中返回数据

当你调用 `$showModal` 时，该方法会返回一个 promise，所有调用 `$modal.close` 时所传递的数据都会被该 promise `resolve`。

在如下示例中，关闭该模态框会使得 console 中输出 'Foo'。

```JavaScript
// ... 在 Master 中
this.$showModal(Detail).then(data => console.log(data));
```

```HTML
<!-- 在 Detail 中 -->
<Button @tap="$modal.close('Foo')" text="Close" />    
```
