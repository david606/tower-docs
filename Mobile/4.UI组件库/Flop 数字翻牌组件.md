# [Flop 数字翻牌组件](http://mid.chinatowercom.cn:18080/appGuide/ui/flop.html#flop-数字翻牌组件)

该组件通常用于数字的动态展示

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/flop.html#基本使用)

- 通过`targetValue`参数设置数据*(必填)

```vue
<template>
  <view>
    <ct-demo-card title="基本使用">
      <ct-ui-flop :targetValue="targetValue"></ct-ui-flop>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      targetValue: 1192.9509
    }
  }
}
</script>

<style></style>
```

### [自定义数字框及文字样式](http://mid.chinatowercom.cn:18080/appGuide/ui/flop.html#自定义数字框及文字样式)

- 通过`bgColor`参数设置数字框的背景颜色。
- 通过`color`参数设置数字的文字颜色。
- 通过`size`参数设置数字的文字大小。
- 通过`borderLineSize`参数设置数字框的边框粗细。
- 通过`borderColor`参数设置数字框的边框颜色。
- 通过`radius`参数设置数字框的边框圆角。
- 通过`width`参数设置数字框的宽度。
- 通过`height`参数设置数字框的高度。
- 通过`bold`参数设置数字是否为粗体。

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义样式">
      <ct-ui-flop
        targetValue="1192.9509"
        bgColor="red"
        color="#ccc"
        size="20"
        borderLineSize="10"
        borderColor="#000"
        radius="10"
        width="40"
        height="70"
        bold="true"
      ></ct-ui-flop>
    </ct-demo-card>
  </view>
</template>

<script>
export default {}
</script>

<style></style>
```

### [自定义动画效果以及非数字符号的样式显示](http://mid.chinatowercom.cn:18080/appGuide/ui/flop.html#自定义动画效果以及非数字符号的样式显示)

- 通过`duration`参数自定义动画的持续时间（默认单位为秒）
- 通过`symbolBorder`参数自定义非数字的任何符号是否显示在数字框中
- 通过`toFixed`参数自定义最终展示数据显示的小数位数(传入数据必须可转为数字)
- 通过`suffixRight`参数自定义数字框后显示的单位
- 通过`suffixLeft`参数自定义数字框前显示的单位
- 通过`border`参数自定义数字框是否显示边框
- 通过`numberSplit`参数自定义是否开启数字分符（最终显示的目标数字必须可转为数字形式）
- 通过`numberSplitSymbol`参数自定义数字分隔符号

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="动画时长(默认单位为秒)">
      <ct-ui-flop targetValue="1192.9509" duration="10"></ct-ui-flop>
    </ct-demo-card>
    <ct-demo-card title="非数字的任何符号是否显示在数字框中">
      <ct-ui-flop targetValue="1192.9509" symbolBorder="false"></ct-ui-flop>
      <ct-ui-flop targetValue="1192.9509" symbolBorder="true"></ct-ui-flop>
    </ct-demo-card>
    <ct-demo-card title="小数位数, 数字框前后显示数据">
      <ct-ui-flop targetValue="1192.9509" toFixed="2"></ct-ui-flop>
      <ct-ui-flop
        targetValue="1192.9509"
        suffixLeft="前"
        suffixRight="后"
      ></ct-ui-flop>
    </ct-demo-card>
    <ct-demo-card title="是否显示数字框">
      <ct-ui-flop targetValue="1192.9509" border="false"></ct-ui-flop>
      <ct-ui-flop targetValue="1192.9509" border="true"></ct-ui-flop>
    </ct-demo-card>
    <ct-demo-card title="是否开启数字分隔">
      <ct-ui-flop targetValue="1192.9509" numberSplit="false"></ct-ui-flop>
      <ct-ui-flop
        targetValue="1192.9509"
        numberSplit="true"
        numberSplitSymbol="*"
      ></ct-ui-flop>
    </ct-demo-card>
  </view>
</template>

<script>
export default {}
</script>

<style></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/flop.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/flop.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 支持版本 |
| ---- | ---- | ---- | ------ | ------ | -------- |
|      |      |      |        |        |          |

| targetValue       | 最终显示的目标数字                                       | Number \| String  |             | —    | 1.0.27+ |
| ----------------- | -------------------------------------------------------- | ----------------- | ----------- | ---- | ------- |
| bgColor           | 数字框的背景色                                           | String            | transparent | —    | 1.0.27+ |
| color             | 数字的颜色                                               | String            | #EB4B4B     | —    | 1.0.27+ |
| color             | 数字的字体大小                                           | String            | #EB4B4B     | —    | 1.0.27+ |
| borderLineSize    | 数字框的边框粗细                                         | Number \| String  | 2rpx        | —    | 1.0.27+ |
| borderColor       | 数字框的边框颜色                                         | String            | #EB4B4B     | —    | 1.0.27+ |
| radius            | 数字框的圆角                                             | Number \| String  | 6rpx        | —    | 1.0.27+ |
| width             | 数字框的宽度                                             | Number \| String  | 36          | —    | 1.0.27+ |
| height            | 数字框的高度                                             | Number \| String  | 50rpx       | —    | 1.0.27+ |
| bold              | 数字是否为粗体                                           | Boolean \| String | false       | —    | 1.0.27+ |
| duration          | 动画的持续时间（默认单位为秒）                           | Number \| String  | 3           | —    | 1.0.27+ |
| symbolBorder      | 非数字的任何符号是否显示在数字框中                       | Boolean \| String | true        | —    | 1.0.27+ |
| toFixed           | 最终展示数据显示的小数位数(传入数据必须可转为数字)       | Number \| String  |             | —    | 1.0.27+ |
| gutter            | 数字框的间隙                                             | Number \| String  | 5rpx        | —    | 1.0.27+ |
| suffixRight       | 数字框后显示的单位                                       | String            |             | —    | 1.0.27+ |
| suffixLeft        | 数字框前显示的单位                                       | String            |             | —    | 1.0.27+ |
| border            | 数字框是否显示边框                                       | Boolean \| String | true        | —    | 1.0.27+ |
| numberSplit       | 是否开启数字分符（最终显示的目标数字必须可转为数字形式） | Boolean \| String | false       | —    | 1.0.27+ |
| numberSplitSymbol | 数字分隔符号                                             | String            | ,           | —    | 1.0.27+ |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/flop.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |