# [Switch 选择器](http://mid.chinatowercom.cn:18080/appGuide/ui/switch.html#switch-选择器)

该组件主要用于在打开以及关闭之间经行切换

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/switch.html#基本使用)

- 通过`v-model`进行双向数据绑定

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-switch v-model="swit" />
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      swit: false
    }
  }
}
</script>

<style lang="scss"></style>
```

### [类型](http://mid.chinatowercom.cn:18080/appGuide/ui/switch.html#类型)

- 通过`type`参数设置选择器类型，可选值为`default`、`primary`、`info`、`warning`、`error`、`success`

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="类型">
              <ct-ui-switch v-model="swit" type="default" />
      <ct-ui-switch v-model="swit" type="primary" />
      <ct-ui-switch v-model="swit" type="info" />
      <ct-ui-switch v-model="swit" type="warning" />
      <ct-ui-switch v-model="swit" type="error" />
      <ct-ui-switch v-model="swit" type="success" />
             
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      swit: true
    }
  }
}
</script>

<style lang="scss"></style>
```

### [大小、颜色](http://mid.chinatowercom.cn:18080/appGuide/ui/switch.html#大小、颜色)

- 通过`size`参数设置选择器大小，可选值为`big`、`middle`、`small` 及数字默认单位 px(表示高度，开关宽度为高度的 1.7 倍取整)， 数组（[宽度， 高度]默认单位为 px）
- 通过`color`参数设置选择器打开时的颜色
- 通过`closeColor`参数设置选择器关闭时的颜色，在 v1.0.19+后使用 inactiveColor 设置选择器关闭颜色

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="大小、颜色">
              <ct-ui-switch v-model="swit" size="default" />
      <ct-ui-switch v-model="swit" size="medium" />
      <ct-ui-switch v-model="swit" size="small" />
      <ct-ui-switch v-model="swit" size="mini" />
      <ct-ui-switch v-model="swit2" color="#3c9cff" />
      <ct-ui-switch v-model="swit3" color="#3c9cff" />
      <ct-ui-switch v-model="swit4" inactiveColor="#cacbd0" />
             
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      swit: false,
      swit2: false,
      swit3: false,
      swit4: false
    }
  }
}
</script>

<style lang="scss"></style>
```

### [自定义样式](http://mid.chinatowercom.cn:18080/appGuide/ui/switch.html#自定义样式)

- 通过`customStyle`参数自定义选择器样式

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义样式">
      <ct-ui-switch v-model="swit" :customStyle="customStyle" />
             
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      swit: false,
      customStyle: {
        height: '30px',
        width: '60px',
        borderRadius: '10px'
      }
    }
  }
}
</script>

<style lang="scss"></style>
```

### [状态](http://mid.chinatowercom.cn:18080/appGuide/ui/switch.html#状态)

- 通过`state`参数设置选择器状态，可选值为`default`、`loading`、`disable`

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="状态">
              <ct-ui-switch v-model="swit" state="default" />
      <ct-ui-switch v-model="swit2" state="loading" />
      <ct-ui-switch v-model="swit3" state="disable" />
             
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      swit: true,
      swit2: true,
      swit3: true
    }
  }
}
</script>

<style lang="scss"></style>
```

### [提示内容](http://mid.chinatowercom.cn:18080/appGuide/ui/switch.html#提示内容)

- 通过`switchContent`参数设置选择器的提示内容
- 通过`switchContent`参数的**type**属性设置提示内容的类型，可选值为`icon`、`text`
- 通过`switchContent`参数的**position**属性设置提示内容的位置，可选值为`sides`、`centre`
- 通过`switchContent`参数的**active**属性设置提示内容打开时的内容，*type*为`icon`时则为`icon`的*name*属性
- 通过`switchContent`参数的**inactive**属性设置提示内容关闭时的内容，*type*为`icon`时则为`icon`的*name*属性
- 通过`switchContent`参数的**color**属性设置提示内容的打开时的颜色
- 通过`switchContent`参数的**closeColor**属性设置提示内容的关闭时的颜色

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="提示内容">
              <ct-ui-switch v-model="swit1" :switchContent="switchContent1" />
      <ct-ui-switch v-model="swit2" :switchContent="switchContent2" />
      <ct-ui-switch v-model="swit3" :switchContent="switchContent3" />
      <ct-ui-switch v-model="swit4" :switchContent="switchContent4" />
             
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      swit1: true,
      swit2: true,
      swit3: true,
      swit4: true,
      switchContent1: {
        type: 'icon',
        position: 'sides',
        active: 'home',
        inactive: 'home-fill',
        color: '#3c9cff',
        closeColor: '#000'
      },
      switchContent2: {
        type: 'icon',
        position: 'centre',
        active: 'home',
        inactive: 'home-fill',
        color: '#3c9cff',
        closeColor: '#000'
      },
      switchContent3: {
        type: 'text',
        position: 'centre',
        active: '开',
        inactive: '关',
        color: '#3c9cff',
        closeColor: '#000'
      },
      switchContent4: {
        type: 'text',
        position: 'sides',
        active: '开',
        inactive: '关',
        color: '#3c9cff',
        closeColor: '#000'
      }
    }
  }
}
</script>

<style lang="scss"></style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/switch.html#事件监听)

- 通过`change`事件监听选择器改变时触发

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="事件监听">
      <ct-ui-switch v-model="swit" @change="change" />
             
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      swit: false
    }
  },
  methods: {
    change(value) {
      console.log(value, this.swit)
    }
  }
}
</script>

<style lang="scss"></style>
```

### [异步更变](http://mid.chinatowercom.cn:18080/appGuide/ui/switch.html#异步更变)

- 通过`asyncChange`参数设置是否开启异步更变

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="异步更变">
      <ct-ui-switch v-model="swit" :asyncChange="true" @change="change" />
             
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      swit: false
    }
  },
  methods: {
    change(value) {
      let self = this
      let content = `确定${value ? '关闭' : '打开'}吗?`
      uni.showModal({
        title: '温馨提示',
        content,
        icon: 'none',
        complete(res) {
          self.swit = res.confirm ? !self.swit : self.swit
        }
      })
    }
  }
}
</script>

<style lang="scss"></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/switch.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/switch.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| value         | 输入值                                                       | Boolean               | —       | —                                                         |         |
| ------------- | ------------------------------------------------------------ | --------------------- | ------- | --------------------------------------------------------- | ------- |
| type          | 类型                                                         | String                | default | default \| primary \| info \| warning \| error \| success |         |
| state         | 状态                                                         | String                | normal  | normal \| loading \| disable                              |         |
| activeColor   | 打开时的背景颜色                                             | String                | #EB4B4B | -                                                         |         |
| inactiveColor | 关闭时的背景颜色                                             | String                | #dcdee0 | -                                                         |         |
| size          | 大小（字符串可选用enums中数据， 数组[宽度， 高度]，单位默认为px，数字格式已经在1.0.32+更新，表示高度，宽度为高度1.7倍取整，单位px） | String｜Array｜Number | small   | default \| medium \| small \| mini                        | 1.0.32+ |
| fontSize      | 字体大小                                                     | Number                | 18      | -                                                         |         |
| color         | 打开颜色                                                     | String                |         | -                                                         |         |
| closeColor    | 关闭颜色                                                     | String                | #FFF    | -                                                         |         |
| customStyle   | 自定义样式                                                   | Object                | {}      | -                                                         |         |
| switchContent | 提示内容                                                     | Object                | {}      | —                                                         |         |
| asyncChange   | 异步更变                                                     | Boolean               | false   | —                                                         |         |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/switch.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| change | 点击选择器时触发 | -    |
| ------ | ---------------- | ---- |
|        |                  |      |