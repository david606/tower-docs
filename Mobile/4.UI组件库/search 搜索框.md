# [search 搜索框](http://mid.chinatowercom.cn:18080/appGuide/ui/search.html#search-搜索框)

该组件通常用于输入内容实时搜索出内容。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/search.html#基本使用)

- 通过`height`参数设置输入框高度
- 通过`maxlength`参数设置输入框最大输入长度
- 通过`borderColor`参数设置边框颜色
- 通过`borderStyle`参数设置边框样式

```vue
<template>
  <view class="demo-page">
    <ct-demo-card
      title="默认样式、列表在本页面随着输入变、左侧icon、有边框、有清除按钮"
    >
      <ct-ui-search
        style="margin-top: 40rpx;"
        borderStyle="border"
        @clean="clean"
        iconImg="../../static/images/searchGray.png"
        v-model="value1"
        @input="handleInput"
      ></ct-ui-search>
      <view class="list">
        <view v-for="(item, index) in datas" :key="index">{{ item }}</view>
      </view>
    </ct-demo-card>
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {
      value1: '',
      value2: '',
      datas: []
    }
  },
  onLoad() {
    _self = this
  },
  methods: {
    //输入触发
    handleInput(e) {
      this.datas = []
      for (var i = 0; i < 10; i++) {
        this.datas.push(e + i)
      }
    },
    //清除
    clean() {
      this.value1 = ''
    }
  }
}
</script>

<style lang="scss">
.list {
  width: 90vw;
  margin: 0 auto;
  margin-top: 20rpx;
}
.list view {
  height: 60rpx;
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/search.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/search.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| value            | 数据                    | string         | —                   | —                        |
| ---------------- | ----------------------- | -------------- | ------------------- | ------------------------ |
| placeholder      | placeholder值           | string         | 请输入内容          | —                        |
| confirmType      | 键盘右下角文字          | string         | done                | send/search/next/go/done |
| showConfirmbar   | 是否显示二级键盘        | boolean        | true                | true/false               |
| height           | 高度，单位px            | string\|number | 35                  | —                        |
| customStyle      | 输入框的自定义样式      | object         | —                   | —                        |
| iconImg          | 左侧icon图标，尺寸18x18 | string         | —                   | —                        |
| cleanImg         | 右侧清除图标，尺寸16x16 | string         | 默认图标            | —                        |
| showClearIcon    | 是否显示右侧的清除图标  | boolean        | true                | true/false               |
| inputAlign       | 输入框文字的对齐方式    | string         | left                | left/center/right        |
| maxlength        | 输入框的最大可输入长度  | string\|number | 140                 | —                        |
| placeholderStyle | placeholder的样式       | object         | —                   | —                        |
| borderStyle      | 边框样式                | string         | none                | none/border/bottom       |
| borderRadius     | 边框圆角，单位px        | string\|number | 4                   | —                        |
| borderColor      | 边框颜色                | string         | rgba(0, 0, 0, 0.08) | —                        |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/search.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| input   | 当键盘输入时获取值   | -    |
| ------- | -------------------- | ---- |
| blur    | 输入框失去焦点时触发 | -    |
| focus   | 输入框聚焦时触发     | -    |
| confirm | 点击完成按钮时触发   | -    |
| clean   | 清除输入框中内容     | -    |