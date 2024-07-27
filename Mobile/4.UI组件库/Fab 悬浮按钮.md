# [Fab 悬浮按钮](http://mid.chinatowercom.cn:18080/appGuide/ui/fab.html#fab-悬浮按钮)

该组件主要提供悬浮收起体验交互，用于快捷操作

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/fab.html#基本使用)

- 通过`left`、`right`、`top`、`bottom`属性设置按钮悬浮位置
- 通过`btns`属性设置弹出按钮组合

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <view style="height:40px;" />
      <ct-ui-fab
        top="180rpx"
        left="40"
        :btns="btns"
        :mask="false"
        text="基本使用"
      ></ct-ui-fab>
         
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      btns: [{text: '1'}, {text: '2'}, {text: '3'}]
    }
  }
}
</script>
<style lang="scss"></style>
```

### [设置方向](http://mid.chinatowercom.cn:18080/appGuide/ui/fab.html#设置方向)

- 通过`direction`属性设置弹出按钮的展开方向

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置方向">
      <view style="height:400px;" />
           
      <ct-ui-fab
        top="220rpx"
        left="40"
        :btns="btns"
        :mask="false"
        text="向右展开"
        direction="right"
      ></ct-ui-fab>
      <ct-ui-fab
        top="220rpx"
        right="40"
        :btns="btns"
        :mask="false"
        text="向左展开"
        direction="left"
      ></ct-ui-fab>
      <ct-ui-fab
        top="390rpx"
        left="40"
        :btns="btns"
        :mask="false"
        text="向上展开"
        direction="top"
      ></ct-ui-fab>
      <ct-ui-fab
        top="540rpx"
        left="40"
        :btns="btns"
        :mask="false"
        text="向下展开"
        direction="bottom"
      ></ct-ui-fab>
         
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      btns: [{text: '1'}, {text: '2'}, {text: '3'}]
    }
  }
}
</script>
<style lang="scss"></style>
```

### [设置样式](http://mid.chinatowercom.cn:18080/appGuide/ui/fab.html#设置样式)

- 通过`borderRadius`属性设置按钮圆角大小
- 通过`background`属性设置按钮背景色
- 通过`btnsBackground`属性设置弹出按钮背景色

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置样式">
      <view style="height:40px;" />
      <ct-ui-fab
        top="220rpx"
        left="40"
        :btns="btns"
        :mask="false"
        text="设置样式"
        borderRadius="100rpx"
        background="#039BE5"
        btnsBackground="transparent"
        color="#000"
      ></ct-ui-fab>
         
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      btns: [{text: '1'}, {text: '2'}, {text: '3'}]
    }
  }
}
</script>
<style lang="scss"></style>
```

### [禁用蒙版](http://mid.chinatowercom.cn:18080/appGuide/ui/fab.html#禁用蒙版)

- 通过`mask`属性设置是否启用蒙版
- 通过`touchMask`属性设置是否启用点击蒙版关闭

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="禁用蒙版">
      <view style="height:40px;" />
         
      <ct-ui-fab
        top="220rpx"
        left="40"
        :btns="btns"
        text="禁用蒙版"
        borderRadius="100rpx"
        background="#039BE5"
        btnsBackground="#ffffff00"
        :mask="false"
        :touchMask="false"
      ></ct-ui-fab>
         
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      btns: [{text: '1'}, {text: '2'}, {text: '3'}]
    }
  }
}
</script>
<style lang="scss"></style>
```

### [自定义插槽](http://mid.chinatowercom.cn:18080/appGuide/ui/fab.html#自定义插槽)

通过设置插槽内容自行进行使用

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义插槽">
      <view style="height:40px;" />
           
      <ct-ui-fab
        top="220rpx"
        :mask="false"
        width="100rpx"
        height="100rpx"
        left="40"
        direction="bottom"
        borderRadius="100rpx"
        btnsBackground="#ffffff00"
      >
        <view class="demo-text"> slot </view>
        <template slot="btns">
          <view class="demo-slot">
            <view class="demo-slot-it" v-for="(it, idx) in icon" :key="idx">
              <view>
                <ct-ui-icon
                  :name="it.name"
                  :size="it.size"
                  :color="it.color"
                ></ct-ui-icon>
              </view>
            </view>
          </view>
        </template>
      </ct-ui-fab>
         
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      icon: [
        {name: 'home', size: 16, color: '#fff'},
        {name: 'home', size: 16, color: '#fff'},
        {name: 'home', size: 16, color: '#fff'}
      ]
    }
  }
}
</script>
<style lang="scss">
.demo-page {
  .demo-row-title {
    padding: 20rpx;
  }
  .demo-slot {
    background-color: transparent;
    .demo-slot-it {
      height: 140rpx;
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: center;
      view {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100rpx;
        width: 100rpx;
        border-radius: 50%;
        background-color: #eb4b4b;
      }
    }
  }
}
</style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/fab.html#事件监听)

-`click`事件监听按钮点击时触发 -`open`事件监听按钮展开时触发 -`close`事件监听按钮收起时触发

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="事件监听">
      <view style="height:40px;" />
      <ct-ui-fab
        top="220rpx"
        left="40"
        :btns="btns"
        text="基本使用"
        @click="click"
        @open="open"
        @close="close"
      ></ct-ui-fab>
         
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      btns: [{text: '1'}, {text: '2'}, {text: '3'}]
    }
  },
  methods: {
    click(item) {
      console.log(item)
    },
    open() {
      console.log('open')
    },
    close() {
      console.log('close')
    }
  }
}
</script>
<style lang="scss"></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/fab.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/fab.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| text           | 按钮文字内容         | String,Number | 按钮  | -          |
| -------------- | -------------------- | ------------- | ----- | ---------- |
| direction      | 展开方向             | String        | right | -          |
| btns           | 弹出按钮组合         | Array         | []    | -          |
| icon           | 按钮icon             | Object        | {}    | -          |
| customStyle    | 自定义样式           | Object        | {}    | -          |
| btnsStyle      | 弹出层自定义样式     | Object        | {}    | -          |
| mask           | 是否启用蒙版         | Boolean       | true  | true/false |
| touchMask      | 是否启用点击蒙版关闭 | Boolean       | true  | true/false |
| left           | -                    | String,Number |       | -          |
| right          | -                    | String,Number |       | -          |
| top            | -                    | String,Number |       | -          |
| bottom         | -                    | String,Number |       | -          |
| width          | -                    | String,Number |       | -          |
| height         | -                    | String,Number |       | -          |
| fontSize       | -                    | String,Number |       | -          |
| color          | -                    | String        |       | -          |
| background     | 悬浮按钮背景色       | String        |       | -          |
| btnsBackground | 弹出按钮背景色       | String        |       | -          |
| borderRadius   | -                    | String,Number |       | -          |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/fab.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| click | 按键被点击时触发   | 点击的按键 |
| ----- | ------------------ | ---------- |
| open  | 组件点击展开时触发 | -          |
| close | 组件点击收起时触发 | -          |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/fab.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

|      | 按钮内容 | -    |
| ---- | -------- | ---- |
| btns | 弹出内容 | -    |

### [BTNS](http://mid.chinatowercom.cn:18080/appGuide/ui/fab.html#btns)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/fab.html#props-1)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| text  | 按钮文字内容 | String,Number |      | -    |
| ----- | ------------ | ------------- | ---- | ---- |
| icon  | 按钮图标     | Object        | {}   | -    |
| style | 按钮样式     | Object        | {}   | -    |