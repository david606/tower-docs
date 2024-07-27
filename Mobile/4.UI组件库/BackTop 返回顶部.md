# [BackTop 返回顶部](http://mid.chinatowercom.cn:18080/appGuide/ui/backTop.html#backtop-返回顶部)

该组件一个用于长页面，滑动一定距离后，出现返回顶部按钮，方便快速返回顶部的场景。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/backTop.html#基本使用)

- 通过`onPageScroll`生命周期监听页面滚动事件，将*scrollTop*参数传递
- 通过`backTop`参数设置距离顶部多少时显示，单位 px
- 通过`duration`参数设置返回顶部所需时间，单位 ms

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-back-top
        :scrollTop="scrollTop"
        :backTop="0"
        :duration="200"
      ></ct-ui-back-top>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      scrollTop: 0
    }
  },
  onPageScroll(e) {
    this.scrollTop = e.scrollTop
  }
}
</script>

<style lang="scss">
.demo-page {
  height: 2000px;
}
</style>
```

### [自定义样式](http://mid.chinatowercom.cn:18080/appGuide/ui/backTop.html#自定义样式)

- 通过`shape`参数设置按钮形状，分别是`square`(默认方形)、`circle`(圆形)或自定义传入数字，单位 px
- 通过`backTopStyle`参数自定义组件样式
- 通过`right`参数设置组件距离右侧距离
- 通过`bottom`参数设置组件距离底部距离

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义样式">
      <ct-ui-back-top
        :scrollTop="scrollTop"
        shape="square"
        :right="80"
        :bottom="80"
        :backTopStyle="backTopStyle"
      ></ct-ui-back-top>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      scrollTop: 0,
      backTopStyle: {
        width: '100rpx',
        height: '100rpx',
        background: '#3c9cff'
      }
    }
  },
  onPageScroll(e) {
    this.scrollTop = e.scrollTop
  }
}
</script>

<style lang="scss">
.demo-page {
  height: 2000px;
}
</style>
```

### [icon](http://mid.chinatowercom.cn:18080/appGuide/ui/backTop.html#icon)

- 通过`icon`参数设置 icon 对应属性，详细参照**icon**组件

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="icon">
      <ct-ui-back-top
        :scrollTop="scrollTop"
        :backTop="0"
        :icon="icon"
      ></ct-ui-back-top>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      scrollTop: 0,
      icon: {
        name: 'home',
        color: '#fff',
        size: 28
      }
    }
  },
  onPageScroll(e) {
    this.scrollTop = e.scrollTop
  }
}
</script>

<style lang="scss">
.demo-page {
  height: 2000px;
}
</style>
```

### [自定义内容](http://mid.chinatowercom.cn:18080/appGuide/ui/backTop.html#自定义内容)

- 通过*slot*自定义组件内容

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义内容">
      <ct-ui-back-top :scrollTop="scrollTop">
        <view class="slot-back-tap">UP</view>
      </ct-ui-back-top>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      scrollTop: 0
    }
  },
  onPageScroll(e) {
    this.scrollTop = e.scrollTop
  }
}
</script>

<style lang="scss">
.demo-page {
  height: 2000px;
  .slot-back-tap {
    color: #fff;
  }
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/backTop.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/backTop.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| scrollTop    | 通过监听onPageScroll生命周期监听页面滑动事件 | Number           |                                             | -                                          |
| ------------ | -------------------------------------------- | ---------------- | ------------------------------------------- | ------------------------------------------ |
| backTop      | 距离顶部多少时显示，单位px                   | Number           | 0                                           | -                                          |
| duration     | 返回顶部所需时间，单位ms                     | Number           | 200                                         | -                                          |
| backTopStyle | 自定义样式                                   | Object           | {}                                          | -                                          |
| shape        | 形状                                         | [Number, String] | circle                                      | square \| circle \| 自定义传入数字，单位px |
| right        | 距离右侧距离，单位rpx                        | [Number, String] | 40                                          | -                                          |
| bottom       | 距离底部距离，单位rpx                        | [Number, String] | 60                                          | -                                          |
| icon         | 自定义icon设置                               | Object           | {name: "chevron-up",color: "#fff",size: 24} | -                                          |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/backTop.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| click | 点击组件时触发 | -    |
| ----- | -------------- | ---- |
|       |                |      |