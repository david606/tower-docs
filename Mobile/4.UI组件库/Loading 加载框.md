# [Loading 加载框](http://mid.chinatowercom.cn:18080/appGuide/ui/loading.html#loading-加载框)

该组件主要用于展示部分内容在加载时显示的默认样式效果。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/loading.html#基本使用)

- 通过`type`参数设置类型，分别是`default`(默认动画)、`line`(柱状动画)、`circle`(圆形动画)、`custom`(自定义动画)
- 通过`text`参数设置文字内容
- 通过`src`参数设置在类型为 custom 时，图片路径，尺寸 30x30

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="默认loading">
      <ct-ui-button @click="sel('default')">打开</ct-ui-button>
    </ct-demo-card>
    <ct-demo-card title="柱状动画">
      <ct-ui-button @click="sel('line')">打开</ct-ui-button>
    </ct-demo-card>
    <ct-demo-card title="圆形动画">
      <ct-ui-button @click="sel('circle')">打开</ct-ui-button>
    </ct-demo-card>
    <ct-demo-card title="自定义动画">
      <ct-ui-button @click="sel('custom')">打开</ct-ui-button>
    </ct-demo-card>

    <ct-ui-loading ref="loading"></ct-ui-loading>
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {}
  },
  onLoad() {
    _self = this
  },
  methods: {
    sel(e) {
      if (e == 'default') {
        _self.$refs.loading.show({
          type: 'default',
          text: '模拟2秒后关闭'
        })
      } else if (e == 'line') {
        _self.$refs.loading.show({
          type: 'line',
          text: '模拟2秒后关闭'
        })
      } else if (e == 'circle') {
        _self.$refs.loading.show({
          type: 'circle',
          text: '模拟2秒后关闭'
        })
      } else if (e == 'custom') {
        _self.$refs.loading.show({
          type: 'custom',
          text: '模拟2秒后关闭',
          src: require('@/static/images/ct_loading.gif')
        })
      }

      setTimeout(function () {
        _self.$refs.loading.hide()
      }, 2000)
    }
  }
}
</script>

<style lang="scss"></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/loading.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/loading.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| type | 类型                              | string | default | default/line/circle/custom |
| ---- | --------------------------------- | ------ | ------- | -------------------------- |
| text | 文字内容                          | string | —       | —                          |
| src  | custom类型时，图片路径，尺寸30x30 | string | —       | —                          |