# 

该组件一般用于出现在代标题头部操作、底部按钮操作，如弹窗做操作。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/toolbar.html#基本使用)

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-toolbar></ct-ui-toolbar>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'toolbar',
  data() {
    return {}
  }
}
</script>

<style lang="scss" scoped></style>
```

### [设置显示位置](http://mid.chinatowercom.cn:18080/appGuide/ui/toolbar.html#设置显示位置)

通过`position`进行工具条显示的位置，可选值可以为`top`(顶部)，`bottom`(底部)

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置显示位置">
      <ct-ui-text content="头部显示" bold></ct-ui-text>
      <ct-ui-toolbar position="top"></ct-ui-toolbar>
      <ct-ui-text content="底部显示" :margin="[...[20, 0]]" bold></ct-ui-text>
      <ct-ui-toolbar position="bottom"></ct-ui-toolbar>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'toolbar',
  data() {
    return {}
  }
}
</script>

<style lang="scss" scoped></style>
```

### [设置标题（头部展示有效）](http://mid.chinatowercom.cn:18080/appGuide/ui/toolbar.html#设置标题-头部展示有效)

- 通过`title`参数设置标题
- 通过`subTitle`参数设置子标题

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置标题（头部展示有效）">
      <ct-ui-text content="标题，不带子标题" bold></ct-ui-text>
      <ct-ui-toolbar title="设置标题"></ct-ui-toolbar>
      <ct-ui-text
        content="标题&子标题"
        :margin="[...[20, 0]]"
        bold
      ></ct-ui-text>
      <ct-ui-toolbar title="设置标题" subTitle="头部展示有效"></ct-ui-toolbar>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'toolbar',
  data() {
    return {}
  }
}
</script>

<style lang="scss" scoped></style>
```

### [按钮显示位置调转](http://mid.chinatowercom.cn:18080/appGuide/ui/toolbar.html#按钮显示位置调转)

通过 `reverse`参数设置取消、确认按钮调换位置

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="按钮显示位置调转">
      <ct-ui-toolbar
        title="设置标题"
        subTitle="头部展示有效"
        reverse
      ></ct-ui-toolbar>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'toolbar',
  data() {
    return {}
  }
}
</script>

<style lang="scss" scoped></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/toolbar.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/toolbar.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| show               | 是否显示                                                     | Boolean          | true    | true \| false | V1.0.33+ |
| ------------------ | ------------------------------------------------------------ | ---------------- | ------- | ------------- | -------- |
| position           | 工具条显示位置，top 顶部、bottom 底部                        | String           | top     | top \| bottom | V1.0.33+ |
| title              | 标题，position = top 起效                                    | String           | -       | -             | V1.0.33+ |
| titleSize          | 标题文字大小，position = top 起效，单位rpx                   | Number \| String | 36      | -             | V1.0.33+ |
| titleColor         | 标题文字颜色，position = top 起效                            | String           | #EB4B4B | -             | V1.0.33+ |
| subTitle           | 副标题，position = top 起效                                  | String           | -       | -             | V1.0.33+ |
| subTitleSize       | 副标题文字大小，position = top 起效，单位rpx                 | Number \| String | 24      | -             | V1.0.33+ |
| subTitleColor      | 副标题文字颜色，position = top 起效                          | String           | #8590A6 | -             | V1.0.33+ |
| showConfirmButton  | 是否显示确认按钮                                             | Boolean          | true    | true ｜ false | V1.0.33+ |
| confirmText        | 确定按钮文字                                                 | String           | 确定    | -             | V1.0.33+ |
| confirmTextSize    | 确定按钮文字大小                                             | Number ｜ String | -       | -             | V1.0.33+ |
| confirmTextColor   | 確定按钮文字颜色                                             | String           | #3164F6 | -             | V1.0.33+ |
| confirmButtonWidth | 确定按钮的宽度，默认宽度为父级元素50%，position = bottom 起效 | Number \| String | 50      | -             | V1.0.33+ |
| showCancelButton   | 是否显示取消按钮                                             | Boolean          | true    | true \| false | V1.0.33+ |
| cancelText         | 取消按钮文字                                                 | String           | 取消    | -             | V1.0.33+ |
| cancelTextSize     | 取消按钮文字大小                                             | Number \| String | -       | -             | V1.0.33+ |
| cancelTextColor    | 取消按钮文字颜色                                             | String           | #505C73 | -             | V1.0.33+ |
| cancelButtonWidth  | 取消按钮的宽度，默认宽度为父级元素50%，position = bottom 起效 | Number \| String | 50      | -             | V1.0.33+ |
| btnColor           | btn 颜色，只针对confirm有效，position = bottom 起效          | String           | #3164F6 | -             | V1.0.33+ |
| btnSize            | 按钮大小（主要是高度），支持button的size属性，big:大号按钮样式 middle:中号按钮样式 small:小号按钮样式(支持数字及带单位的值，单位：px)，position = bottom 起效 | Number \| String | 40      | -             | V1.0.33+ |
| btnShape           | 按钮形状，position = bottom 起效                             | Number \| String | 4       | -             | V1.0.33+ |
| cancelButtonWidth  | 确定按钮是否禁用，position = bottom 起效                     | Boolean          | false   | true \| false | V1.0.33+ |
| reverse            | 取消/确认按钮反转                                            | Boolean          | false   | true \| false | V1.0.33+ |