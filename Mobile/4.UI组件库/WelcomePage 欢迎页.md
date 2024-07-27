# [WelcomePage 欢迎页](http://mid.chinatowercom.cn:18080/appGuide/ui/welcomePage.html#welcomepage-欢迎页)

该组件一般用于 APP 启动欢迎页，可展示图片/视频等。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/welcomePage.html#基本使用)

- 通过`list`参数定义展示素材路径/路径集合，支持图片/视频
- 通过`type`参数定义跳过按钮显示形式
- 通过`text`、`color`、`size`、`bgColor`设置跳过按钮的文字、颜色、背景色及文字大小
- 通过`timer`参数控制倒计时时间

```vue
<template>
  <view class="demo">
    <ct-ui-welcome-page
      :list="list"
      bg-color="#fff"
      color="#EB4B4B"
      :offset="offset"
      random
      type="merge"
      @click="click"
    ></ct-ui-welcome-page>
  </view>
</template>

<script>
export default {
  name: 'welcome-page',
  data() {
    return {
      list: [
        '/images/ct-welcomepage.jpg',
        '/images/ct-welcomepage.jpg',
        'https://vkceyugu.cdn.bspapp.com/VKCEYUGU-learning-vue/52d32740-aecd-11ea-b244-a9f5e5565f30.mp4'
      ],
      offset: [0, 120]
    }
  },
  methods: {
    click() {
      uni.showToast({
        title: '执行业务逻辑',
        duration: 2000
      })
      console.log('执行业务逻辑')
    }
  }
}
</script>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/welcomePage.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/welcomePage.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| *list（必填）    | 素材文件，可以为数组/字符串                                  | String｜Array  | -              | -            |
| ---------------- | ------------------------------------------------------------ | -------------- | -------------- | ------------ |
| random           | 随机显示一个(当list为数组时起效)                             | Boolean        | false          | true\|false  |
| type             | 跳过按钮显示位置，merge 与倒计时显示在一起，alone则单独显示在屏幕底部 | String         | merge          | merge\|alone |
| text             | 跳过按钮文字                                                 | String         | 跳过           | -            |
| color            | 跳过按钮字体颜色（type=alone 起效）                          | String         | #ffffff        | -            |
| size             | 跳过按钮文字字体大小（type=alone 起效）                      | Number｜String | 14px           | -            |
| bgColor          | 跳过按钮文字背景色                                           | String         | #EB4B4B        | -            |
| offset           | 按钮偏移距离 [x,y]                                           | Array          | -              | -            |
| timer            | 倒计时时间（s）                                              | Number         | 3              | -            |
| timerColor       | 倒计时字体颜色                                               | String         | #ffffff        | -            |
| timerBgColor     | 倒计时背景颜色                                               | String         | rgba(0,0,0,.2) | -            |
| timerOffset      | 倒计时偏移距离 [x,y]                                         | Array          | -              | -            |
| autoplay         | 自动播放                                                     | Boolean        | true           | true\|false  |
| customStyle      | 外部自定义样式                                               | Object         | -              | -            |
| customTimerStyle | 自定义倒计时样式                                             | Object         | -              | -            |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/welcomePage.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| change | 倒计时变化时触发   | 剩余时间 |
| ------ | ------------------ | -------- |
| click  | 点击跳过按钮时触发 | -        |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/welcomePage.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

| button | 跳过按钮自定义内容（type=alone 起效） | -    |
| ------ | ------------------------------------- | ---- |
| timer  | 倒计时自定义内容                      | -    |