# [Dialog 对话框](http://mid.chinatowercom.cn:18080/appGuide/ui/dialog.html#dialog-对话框)

该组件主要用于对用户进行弹出提示框进行确认用户操作。

### [调用方式](http://mid.chinatowercom.cn:18080/appGuide/ui/dialog.html#调用方式)

> 通过 ref 调用`dialog`组件内部的`show`方法显示提示对话框

```javascript
this.$refs['xxx'].show((options = {}))

options = {
  title: '', // 显示标题
  content: '', // 显示内容
  showConfirm: true, // 显示确定按钮
  confirmLabel: '确定', // 确定按钮的文字
  showCancel: true, // 显示取消按钮
  cancelLabel: '取消', // 取消按钮的文字
  confirm: null, // 执行确定按钮的回调函数
  cancel: null, //  执行取消按钮的回掉函数
  mode: 'button/text' // 底部按钮显示的模式，button 按钮形式、text 一行文本形式
}
```

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/dialog.html#基本使用)

- 调用内部的`show`方法进行显示

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-button @click="show">点击显示</ct-ui-button>
         
    </ct-demo-card>
    <ct-ui-dialog ref="dialog"></ct-ui-dialog>
  </view>
</template>

<script>
export default {
  data() {
    return {}
  },
  methods: {
    show() {
      this.$refs.dialog.show({
        title: '默认对话框样式',
        content: '提示内容<br/>提示内容2'
      })
    }
  }
}
</script>
```

### [回调函数](http://mid.chinatowercom.cn:18080/appGuide/ui/dialog.html#回调函数)

- 通过参数`confirm`、`cancel` 设置点击后的回调函数

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="回调函数">
      <ct-ui-button @click="show">点击显示</ct-ui-button>
         
    </ct-demo-card>
    <ct-ui-dialog ref="dialog"></ct-ui-dialog>
  </view>
</template>

<script>
export default {
  data() {
    return {}
  },
  methods: {
    show() {
      this.$refs.dialog.show({
        title: '回调函数',
        content: '提示内容<br/>提示内容2',
        confirm: () => {
          console.log('confirm:: 确定')
        },
        cancel: () => {
          console.log('cancel:: 取消')
        }
      })
    }
  }
}
</script>
```

### [显示按钮](http://mid.chinatowercom.cn:18080/appGuide/ui/dialog.html#显示按钮)

- 通过参数`showConfirm`、`showCancel` 设置显示的操作按钮
- 通过参数`confirmLabel`、`cancelLabel` 设置显示按钮的文字内容

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="显示按钮">
      <ct-ui-button @click="show">点击显示</ct-ui-button>
         
    </ct-demo-card>
    <ct-ui-dialog ref="dialog"></ct-ui-dialog>
  </view>
</template>

<script>
export default {
  data() {
    return {}
  },
  methods: {
    show() {
      this.$refs.dialog.show({
        title: '温馨提示',
        content: '只有一个确定按钮',
        showCancel: false
      })
    }
  }
}
</script>
```

### [mode = text 底部行文字](http://mid.chinatowercom.cn:18080/appGuide/ui/dialog.html#mode-text-底部行文字)

- mode = text 底部行文字展示
- mode = button 底部按钮展示

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="mode = text">
      <ct-ui-button @click="show">点击显示</ct-ui-button>
    </ct-demo-card>
    <ct-ui-dialog
      ref="dialog"
      mode="text"
      confirmBgColor="#FFFFFF"
      confirmColor="#3164F6"
      cancelBgColor="#FFFFFF"
      cancelColor="rgba(80,92,115, 0.6)"
      cancelSize="32"
      confirmSize="32"
    >
    </ct-ui-dialog>
  </view>
</template>

<script>
export default {
  data() {
    return {}
  },
  methods: {
    show() {
      let content = `<div style="display:flex; flex-direction: column; align-items: center; text-align: center; justify-content: center;">
								<div>请点击“允许“以授权“铁塔视联“访问您的位置信息，</div>
								<div>以便您能够快速定位至当前的所在位置。</div>
						</div>`
      this.$refs.dialog.show({
        title: 'mode=text',
        content,
        confirm: () => {
          console.log('confirm:: 确定')
        },
        cancel: () => {
          console.log('cancel:: 取消')
        }
      })
    }
  }
}
</script>
<style lang="scss">
.custom {
  font-size: 28rpx;
  font-weight: bold;
  text-align: center;
  color: #dd524d;
}
</style>
```

### [设置插槽](http://mid.chinatowercom.cn:18080/appGuide/ui/dialog.html#设置插槽)

- 在内容区自定义显示的文本内容

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="插槽方式的对话框样式">
      <ct-ui-button @click="show">点击显示</ct-ui-button>
    </ct-demo-card>
    <ct-ui-dialog ref="dialog">
      <view class="custom">我是插槽slot的内容</view>
    </ct-ui-dialog>
  </view>
</template>

<script>
export default {
  data() {
    return {}
  },
  methods: {
    show() {
      this.$refs.dialog.show({
        title: '温馨提示',
        content: '插槽方式的对话框样式',
        showCancel: false
      })
    }
  }
}
</script>
<style lang="scss">
.custom {
  font-size: 28rpx;
  font-weight: bold;
  text-align: center;
  color: #dd524d;
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/dialog.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/dialog.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| titleColor        | title 文字颜色                | String           | #262F40 | —                                | V1.0.18+ |
| ----------------- | ----------------------------- | ---------------- | ------- | -------------------------------- | -------- |
| titleSize         | title 文字大小，默认单位为rpx | String \| Number | 36      | —                                | V1.0.18+ |
| color             | 内容颜色                      | String           | #505C73 | —                                | V1.0.18+ |
| size              | 内容文字大小，默认单位为rpx   | String \| Number | 28      | —                                | V1.0.18+ |
| bgColor           | 背景色                        | String           | #fffff  | —                                | V1.0.18+ |
| confirmSize       | 确定按钮字体大小              | String \| Number | 28      | —                                | V1.0.18+ |
| confirmColor      | 确定按钮字体颜色              | String           | #ffffff | —                                | V1.0.18+ |
| confirmBgColor    | 确定按钮背景色                | String           | #3164F6 | —                                | V1.0.18+ |
| cancelSize        | 取消按钮字体大小              | String \| Number | 28      | —                                | V1.0.18+ |
| cancelColor       | 取消按钮字体颜色              | String           | #505C73 | —                                | V1.0.18+ |
| confirmBgColor    | 取消按钮背景颜色              | String           | #ffffff | —                                | V1.0.18+ |
| cancelBorderColor | 取消按钮边框颜色              | String           | #E4E8F0 | —                                | V2.0.0+  |
| radius            | 圆角                          | Number ｜ String | 16      | 单位rpx                          | V1.0.24+ |
| opacity           | 遮罩层透明度                  | String ｜ Number | 0.1     | —                                | V1.0.18+ |
| zIndex            | 弹出层级                      | Number ｜ String | 999     | —                                | V1.0.21+ |
| mode              | 模式                          | String           | button  | text 一行显示 \| button 按钮形式 | V1.0.24+ |
| splitLineColor    | 分割线颜色                    | String           | E0E0E0  | -                                | V1.0.24+ |
| animate           | 是否开启动画                  | Boolean          | true    | —                                | V1.0.18+ |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/dialog.html#events)

| 事件名 | 说明 | 返回值 | 版本 |
| ------ | ---- | ------ | ---- |
|        |      |        |      |

| ctDialogConfirm | 确定点击事件 | -    | V1.0.17+ 弃用 |
| --------------- | ------------ | ---- | ------------- |
| ctDialogCancle  | 取消点击事件 | -    | V1.0.17+ 弃用 |
| confirm         | 确定点击事件 | -    | V1.0.18+ 弃用 |
| cancel          | 取消点击事件 | -    | V1.0.18+ 弃用 |

#### [Params](http://mid.chinatowercom.cn:18080/appGuide/ui/dialog.html#params)

这些参数为通过 ref 调用`dialog`组件内部的`show`方法时，需要传递参数

| 参数名 | 说明 | 版本 |
| ------ | ---- | ---- |
|        |      |      |

| title        | 显示标题               | v1.0.18+ |
| ------------ | ---------------------- | -------- |
| content      | 显示内容               | v1.0.18+ |
| showConfirm  | 是否显示确定按钮       | v1.0.18+ |
| confirmLabel | 确定按钮的文字         | v1.0.18+ |
| showCancel   | 是否显示取消按钮       | v1.0.18+ |
| cancelLabel  | 取消按钮的文字         | v1.0.18+ |
| confirm      | 执行确定按钮的回调函数 | v1.0.18+ |
| cancel       | 执行取消按钮的回掉函数 | v1.0.18+ |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/dialog.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

| default | 自定义弹出内容   | -    |
| ------- | ---------------- | ---- |
| button  | 底部按钮显示区域 | -    |