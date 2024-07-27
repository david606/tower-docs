# [Tooltip 长按提示](http://mid.chinatowercom.cn:18080/appGuide/ui/tooltip.html#tooltip-长按提示)

该组件主要是对用户长按文本，可进行的操作进行封装使用

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/tooltip.html#基本使用)

- 通过`text`参数设置文本内容
- 通过`buttons`参数设置按钮数组

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-tooltip ref="tooltip" text="基本使用" :buttons="buttons" />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'tooltip',
  data() {
    return {
      buttons: [
        {
          text: '拓展'
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [隐藏复制按钮](http://mid.chinatowercom.cn:18080/appGuide/ui/tooltip.html#隐藏复制按钮)

- 通过`showCopy`参数设置是否显示复制按钮
- 通过`showToast`参数设置是否显示复制成功提示

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="隐藏复制按钮">
      <ct-ui-tooltip
        ref="tooltip"
        text="隐藏复制按钮"
        :buttons="buttons"
        :showCopy="false"
        :showToast="false"
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'tooltip',
  data() {
    return {
      buttons: [
        {
          text: '拓展'
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [自定义样式](http://mid.chinatowercom.cn:18080/appGuide/ui/tooltip.html#自定义样式)

- 通过`background`参数设置按钮背景色
- 通过`color`参数设置按钮字体颜色
- 通过`size`参数设置按钮字体大小

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义样式">
      <ct-ui-tooltip
        ref="tooltip"
        text="自定义样式"
        :buttons="buttons"
        background="#f56c6c"
        color="#ffffff"
        :size="12"
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'tooltip',
  data() {
    return {
      buttons: [
        {
          text: '拓展'
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [设置弹出位置](http://mid.chinatowercom.cn:18080/appGuide/ui/tooltip.html#设置弹出位置)

- 通过`direction`参数设置按钮弹出的位置

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置弹出位置">
      <ct-ui-tooltip
        ref="tooltip"
        text="上方弹出"
        :buttons="buttons"
        direction="top"
      />
      <ct-ui-tooltip
        ref="tooltip"
        text="下方弹出"
        :buttons="buttons"
        direction="bottom"
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'tooltip',
  data() {
    return {
      buttons: [
        {
          text: '拓展'
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [设置 icon](http://mid.chinatowercom.cn:18080/appGuide/ui/tooltip.html#设置-icon)

- 通过`buttons`中传入 icon 属性来设置图标设置
- 通过`btndirection`参数设置按钮的排列方式

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置icon">
      <ct-ui-tooltip
        ref="tooltip"
        text="竖向排列"
        :buttons="buttons"
        btndirection="column"
      />
      <ct-ui-tooltip
        ref="tooltip"
        text="横向排列"
        :buttons="buttons"
        btndirection="row"
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'tooltip',
  data() {
    return {
      buttons: [
        {
          text: '拓展',
          icon: {
            name: 'home',
            size: 16
          }
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [自动隐藏](http://mid.chinatowercom.cn:18080/appGuide/ui/tooltip.html#自动隐藏)

- 通过`autoHide`参数设置是否过去 1s 未点击自动消失,设置为数字则为几秒后消失

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自动隐藏">
      <ct-ui-tooltip
        ref="tooltip"
        text="自动隐藏"
        :buttons="buttons"
        :autoHide="1000"
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'tooltip',
  data() {
    return {
      buttons: [
        {
          text: '拓展',
          icon: {
            name: 'home',
            size: 16
          }
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/tooltip.html#事件监听)

`click`事件可以监听点击按钮时触发，`copy`事件可以监听复制成功时触发，`copyFail`事件可以监听复制失败时触发

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="事件监听">
      <ct-ui-tooltip
        ref="tooltip"
        text="事件监听"
        :buttons="buttons"
        @click="click"
        @copy="copy"
        @copyFail="copyFail"
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'tooltip',
  data() {
    return {
      buttons: [
        {
          text: '拓展',
          icon: {
            name: 'home',
            size: 16
          }
        }
      ]
    }
  },
  methods: {
    click(e, i) {
      console.log(e, i)
    },
    copy(e) {
      console.log(e)
    },
    copyFail(err) {
      console.log(err)
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/tooltip.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/tooltip.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| text         | 文字内容                                              | [String,Number]  |        | -             |
| ------------ | ----------------------------------------------------- | ---------------- | ------ | ------------- |
| buttons      | 提示按钮                                              | Array            | []     | -             |
| showCopy     | 是否显示复制按钮                                      | Boolean          | true   | true/false    |
| showToast    | 是否显示复制成功提示                                  | Boolean          | true   | true/false    |
| showMask     | 是否显示遮罩层                                        | Boolean          | false  | true/false    |
| autoHide     | 设置是否过去1s未点击自动消失,设置为数字则为几秒后消失 | [Boolean,Number] | false  | true/false    |
| size         | 字体大小                                              | Number           | 14     | -             |
| color        | 字体颜色                                              | String           | #000   | -             |
| background   | 按钮背景色                                            | String           | #FFF   | -             |
| direction    | 提示位置                                              | String           | bottom | top \| bottom |
| btndirection | 按钮图标排列方式                                      | Number           | 14     | row \| column |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/tooltip.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| click    | 点击按钮时触发         | 点击的按钮，下标 |
| -------- | ---------------------- | ---------------- |
| copy     | 点击复制按钮成功时触发 | 成功状态         |
| copyFail | 点击复制按钮失败时触发 | 失败理由         |