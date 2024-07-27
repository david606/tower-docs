# [Toast 轻提示](http://mid.chinatowercom.cn:18080/appGuide/ui/toast.html#toast-轻提示)

该组件一种轻量级反馈/提示，适合用于数据交互、信息提示的等场景中。**`(v1.0.18+支持)`**

### [调用方式](http://mid.chinatowercom.cn:18080/appGuide/ui/toast.html#调用方式)

> 通过 ref 调用`toast`组件内部的`show`方法显示提示
>  通过 ref 调用`toast`组件内部的`hide`方法隐藏提示

#### [快捷调用方式](http://mid.chinatowercom.cn:18080/appGuide/ui/toast.html#快捷调用方式)

> 通过 ref 调用`toast`组件内部的`text`方法显示文字提示 
>  通过 ref 调用`toast`组件内部的`success`方法显示带成功图标提示
>  通过 ref 调用`toast`组件内部的`fail`方法显示带错误图标显示
>  通过 ref 调用`toast`组件内部的`warn`方法显示带警告图标提示
>  通过 ref 调用`toast`组件内部的`loading`方法显示带 loading 图标提示

```javascript
this.$refs['xxx'].show(<title = string /options = {}>, options = {})
this.$refs['xxx'].text(<title = string /options = {}>, options = {})
this.$refs['xxx'].success(<title = string /options = {}>, options = {})
this.$refs['xxx'].fail(<title = string /options = {}>, options = {})
this.$refs['xxx'].warn(<title = string /options = {}>, options = {})
this.$refs['xxx'].loading(<title = string /options = {}>, options = {})

// 第一个参数可以支持String类型，也可以支持Object类型，如果为String类型，则代表标题。
// 第二个参数必须为Object类型。参数见如下说明

options = {
  title: '', // 显示标题/内容
  content: '', // 显示内容
  icon: '', // 图标
  iconSize: '100rpx', // 图标大小
  iconColor: '', // 图标颜色
  duration: 2000, // 显示的时间，毫秒
  position: 'center', // toast出现的位置
  complete: null, // 执行完后的回调函数
  closeOnClickOverLay: true, // 点击遮罩层关闭
}
```

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/toast.html#基本使用)

- 通过`padding`参数定义内容区域的边距
- 通过`background`参数定义遮罩层的背景色

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-button @click="showToast('操作成功')">弹出提示</ct-ui-button>
    </ct-demo-card>
    <ct-ui-toast ref="toast" :animate="false"></ct-ui-toast>
  </view>
</template>

<script>
export default {
  name: 'toast',
  methods: {
    showToast(title) {
      this.$refs.toast.show(title)
    }
  }
}
</script>
```

### [多行弹出提示](http://mid.chinatowercom.cn:18080/appGuide/ui/toast.html#多行弹出提示)

支持多行文字提示展示

```vue
<template>
  <view class="demo-page">
    <ct-ui-button
      @click="
        showToast(
          '设备信息内容多且复杂，欢迎开发者测试更多环境设备并编辑本文档参与贡献。'
        )
      "
    >
      多行弹出提示
    </ct-ui-button>
    <ct-ui-toast ref="toast" :animate="false"></ct-ui-toast>
  </view>
</template>

<script>
export default {
  name: 'toast',
  methods: {
    showToast(title) {
      this.$refs.toast.show(title)
    }
  }
}
</script>
```

### [带回调提示](http://mid.chinatowercom.cn:18080/appGuide/ui/toast.html#带回调提示)

通过参数`complete`设置回调方法

```vue
<template>
  <view class="demo-page">
    <ct-ui-button
      @click="
        showToast(
          '设备信息内容多且复杂，欢迎开发者测试更多环境设备并编辑本文档参与贡献。'
        )
      "
    >
      带回调提示
    </ct-ui-button>
    <ct-ui-toast ref="toast" :animate="false"></ct-ui-toast>
  </view>
</template>

<script>
export default {
  name: 'toast',
  methods: {
    showToast(title) {
      this.$refs.toast.show(title, {
        duration: 2000,
        closeOnClickOverLay: false,
        complete: () => {
          console.log('toast complete')
        }
      })
    }
  }
}
</script>
```

### [title & content 提示](http://mid.chinatowercom.cn:18080/appGuide/ui/toast.html#title-content-提示)

> title 与 content 同时设置，title 则会显示在顶部，content 显示在 title 下面

通过参数`title`设置标题，`content`设置内容

```vue
<template>
  <view class="demo-page">
    <ct-ui-button
      @click="
        showToast(
          '设备信息内容多且复杂，欢迎开发者测试更多环境设备并编辑本文档参与贡献。'
        )
      "
    >
      title & content 提示
    </ct-ui-button>
    <ct-ui-toast ref="toast" :animate="false"></ct-ui-toast>
  </view>
</template>

<script>
export default {
  name: 'toast',
  methods: {
    showToast(title) {
      this.$refs.toast.show('温馨提示', {
        content: content,
        duration: 2000,
        closeOnClickOverLay: false,
        complete: () => {
          console.log('toast complete')
        }
      })
    }
  }
}
</script>
```

### [icon 显示](http://mid.chinatowercom.cn:18080/appGuide/ui/toast.html#icon-显示)

通过参数`icon`设置 icon 图标，见[icon 说明](http://mid.chinatowercom.cn:18080/appGuide/ui/icon.html)、`iconColor`设置图标颜色、`iconSize`设置图标大小

```vue
<template>
  <view class="demo-page">
    <ct-ui-button @click="showToast('操作成功')"> icon 显示 </ct-ui-button>
    <ct-ui-toast ref="toast" :animate="false"></ct-ui-toast>
  </view>
</template>

<script>
export default {
  name: 'toast',
  methods: {
    showToast(title) {
      this.$refs.toast.show(title, {
        icon: 'checkbox-circle-line',
        iconSize: '100rpx',
        closeOnClickOverLay: false,
        duration: 2000
      })
    }
  }
}
</script>
```

### [快捷调用](http://mid.chinatowercom.cn:18080/appGuide/ui/toast.html#快捷调用)

支持**text**、**success**、**fail**、**error**、**loading**快捷调用

```vue
<template>
  <view class="demo-page">
    <ct-ui-button @click="showToast('操作成功', 'success')"
      >成功(success)</ct-ui-button
    >
    <ct-ui-button @click="showToast('操作失败', 'fail')">
      失败(fail)
    </ct-ui-button>
    <ct-ui-button @click="showToast('请选择', 'warn')">
      警告(warn)
    </ct-ui-button>
    <ct-ui-button @click="showToast('请稍后', 'loading')">
      Loading(loading)
    </ct-ui-button>
    <ct-ui-toast ref="toast" :animate="false"></ct-ui-toast>
  </view>
</template>

<script>
export default {
  name: 'toast',
  methods: {
    showToast(title, type) {
      this.$refs.toast[type](title)
    }
  }
}
</script>
```

### [显示位置](http://mid.chinatowercom.cn:18080/appGuide/ui/toast.html#显示位置)

通过`position`参数设置显示的位置，默认为中间 center。支持位置选项：top、center、bottom

```vue
<template>
  <view class="demo-page">
    <ct-ui-button @click="showToast('操作成功', 'top')"> 顶部 </ct-ui-button>
    <ct-ui-button @click="showToast('操作成功', 'center')"> 中间 </ct-ui-button>
    <ct-ui-button @click="showToast('操作成功', 'bottom')"> 底部 </ct-ui-button>
    <ct-ui-toast ref="toast" :animate="false"></ct-ui-toast>
  </view>
</template>

<script>
export default {
  name: 'toast',
  methods: {
    showToast(title, position) {
      this.$refs.toast.show(title, {
        position
      })
    }
  }
}
</script>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/toast.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/toast.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| padding    | 提示框padding值，[上,右,下,左] | Array            | ['18rpx', '20rpx']  | -             | v1.0.18+ |
| ---------- | ------------------------------ | ---------------- | ------------------- | ------------- | -------- |
| background | 提示框背景颜色                 | String           | rgba(88, 88, 88, 1) | -             | v1.0.18+ |
| opacity    | 遮罩层透明度                   | String \| Number | 0.1                 | 0 ~ 1         | v1.0.18+ |
| animate    | 是否开启动画                   | Boolean          | true                | true \| false | v1.0.18+ |

#### [Params](http://mid.chinatowercom.cn:18080/appGuide/ui/toast.html#params)

这些参数为通过 ref 调用`toast`组件内部的`show`方法时，需要传递参数

| 参数名 | 说明 | 版本 |
| ------ | ---- | ---- |
|        |      |      |

| title               | 显示标题/内容                 | v1.0.18+ |
| ------------------- | ----------------------------- | -------- |
| content             | 显示内容                      | v1.0.18+ |
| icon                | 图标                          | v1.0.18+ |
| iconSize            | 图标大小                      | v1.0.18+ |
| iconColor           | 图标颜色                      | v1.0.18+ |
| duration            | 显示的时间，毫秒，默认为2000  | v1.0.18+ |
| position            | toast出现的位置，默认为center | v1.0.18+ |
| complete            | 执行完后的回调函数            | v1.0.18+ |
| closeOnClickOverLay | 点击遮罩层关闭，默认为true    | v1.0.18+ |