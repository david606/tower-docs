# [Card 个人信息卡](http://mid.chinatowercom.cn:18080/appGuide/ui/card.html#card-个人信息卡)

该组件主要用于展示用户个人头像、姓名等信息。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/card.html#基本使用)

- 通过`logo`参数设置头像路径
- 通过`name`参数设置姓名
- 通过`section`参数设置部门信息

```vue
<template>
  <view class="demo">
    <view class="card">
      <ct-ui-card
        :name="cardObj.name"
        :section="cardObj.section"
        :minorUrl="cardObj.minorUrl"
        :minor="cardObj.minor"
        @click="ctCardClick"
        @ctHeaderClick="ctHeaderClick"
      >
      </ct-ui-card>
    </view>
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {
      cardObj: {}
    }
  },
  onLoad() {
    _self = this
    _self.setDatas()
  },
  methods: {
    setDatas() {
      _self.cardObj = {
        name: '王大锤',
        section: '运维',
        minorUrl: '../../static/images/ct_card_phone.png',
        minor: '15012345678'
      }
    },
    ctCardClick() {
      _self.$ctmobile.dialog.alertConfirm({
        title: '个人信息卡',
        content: '点击了个人信息卡'
      })
    },
    ctHeaderClick() {
      _self.$ctmobile.dialog.alertConfirm({
        title: '个人信息卡',
        content: '点击了头像'
      })
    }
  }
}
</script>

<style lang="scss">
.demo {
  width: 100vw;

  .card {
    margin-top: 60rpx;
    // width: 100vw;
  }
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/card.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/card.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| radius          | 圆角，单位rpx         | Number ｜ String | 12      | —             | v1.0.20+ |
| --------------- | --------------------- | ---------------- | ------- | ------------- | -------- |
| background      | 背景，默认为#ffffff   | String           | —       | —             | v1.0.20+ |
| logo            | 头像路径              | String           | —       | —             | v1.0.20+ |
| logoSize        | 头像的大小，单位rpx   | Number \| String | 80      | —             | v1.0.20+ |
| logoBorder      | 头像路径              | String           | —       | —             | v1.0.20+ |
| logoBorderColor | 头像边框颜色          | String           | —       | —             | v1.0.20+ |
| logoRadius      | 头像圆角              | String ｜ Number | 40      | —             | v1.0.20+ |
| name            | 姓名                  | String           | —       | —             |          |
| nameColor       | 姓名字体颜色          | String           | #262F40 | —             | v1.0.20+ |
| nameSize        | 姓名字体大小，单位rpx | String ｜ Number | 28      | —             | v1.0.20+ |
| section         | 部门                  | String           | —       | —             |          |
| icon            | 图标名称              | String           | —       | —             | v1.0.20+ |
| iconSize        | 图标大小，单位rpx     | String ｜ Number | 28      | —             | v1.0.20+ |
| iconColor       | 图标颜色              | String           | #8590A6 | —             | v1.0.20+ |
| minor           | 下方文字              | String           | —       | —             |          |
| showArrows      | 是否显示右侧箭头      | Boolean          | true    | true ｜ false |          |
| customStyle     | 自定义样式            | Object           | {}      | -             | v1.0.21+ |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/card.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| headerClick | 头像点击事件     | -    |
| ----------- | ---------------- | ---- |
| click       | 个人卡片点击事件 | -    |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/card.html#slots)

| name | 说明 | 作用域 | 版本 |
| ---- | ---- | ------ | ---- |
|      |      |        |      |

| default | 中间内容区域 | -    |      |
| ------- | ------------ | ---- | ---- |
|         |              |      |      |