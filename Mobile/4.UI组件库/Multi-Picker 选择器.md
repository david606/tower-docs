# [Multi-Picker 选择器](http://mid.chinatowercom.cn:18080/appGuide/ui/multiPicker.html#multi-picker-选择器)

该组件用于多列选择场景。**`(v1.0.12+支持)`**

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/multiPicker.html#基本使用)

- 通过`title`参数定义标题
- 通过`value`参数定义默认选中的值
- 通过`closeable`参数定义是否显示关闭图标按钮
- 通过`options`参数定义选择项列表，**支持一维数组/二维数组**
- 通过`labelKey`参数定义显示的 key 值 **二维数组起效**
- 通过`valueKey`参数定义选中的 value 值 **二维数组起效**

```vue
<template>
  <view class="demo-page">
    <ct-ui-picker
      title="选择区"
      :options="options"
      :value="defaultValue"
      label-key="text"
      value-key="id"
      confirmButtonWidth="65"
      cancelButtonWidth="35"
      @change="change"
      @confirm="confirm"
      closeable
    >
      <view>选择地区</view>
    </ct-ui-picker>
  </view>
</template>

<script>
export default {
  name: 'picker',
  data() {
    return {
      defaultValue: '',
      options: [
        {
          id: 1001,
          text: '北京'
        },
        {
          id: 1002,
          text: '广东'
        },
        {
          id: 1003,
          text: '四川'
        },
        {
          id: 1004,
          text: '江西'
        },
        {
          id: 1005,
          text: '武汉'
        }
      ]
    }
  },
  methods: {
    change(value) {
      console.log('change value::', value)
    },
    confirm(value) {
      console.log('confirm value::', value)
    }
  }
}
</script>

<style scoped lang="scss">
.box {
  width: 50px;
  height: 50px;
  border-radius: 10px;
  background-color: #999999;
  margin-left: 25px;
}
</style>
```

### [options 一维数组](http://mid.chinatowercom.cn:18080/appGuide/ui/multiPicker.html#options-一维数组)

```vue
<template>
  <view class="demo-page">
    <ct-ui-picker
      title="选择数字"
      :options="options"
      :value="defaultValue"
      label-key="text"
      value-key="id"
      confirmButtonWidth="65"
      cancelButtonWidth="35"
      @change="change"
      @confirm="confirm"
      closeIconPos="top-left"
      closeable
    >
      <view>选择数字</view>
    </ct-ui-picker>
  </view>
</template>

<script>
export default {
  name: 'picker',
  data() {
    return {
      defaultValue: '3',
      options: [0, 1, 2, 3, 4, 5]
    }
  },
  methods: {
    change(value) {
      console.log('change value::', value)
    },
    confirm(value) {
      console.log('confirm value::', value)
    }
  }
}
</script>

<style scoped lang="scss">
.box {
  width: 50px;
  height: 50px;
  border-radius: 10px;
  background-color: #999999;
  margin-left: 25px;
}
</style>
```

### [打开/关闭 picker 选择器](http://mid.chinatowercom.cn:18080/appGuide/ui/multiPicker.html#打开-关闭-picker-选择器)

通过`openPoup`、`close`方法进行打开/关闭 picker 选择器

```vue
<template>
  <view class="demo-page">
    <ct-ui-picker
      ref="picker"
      title="选择区2"
      :options="options"
      :value="defaultValue"
      label-key="text"
      value-key="id"
      confirmButtonWidth="65"
      cancelButtonWidth="35"
      @change="change"
      @confirm="confirm"
      closeable
    >
    </ct-ui-picker>

    <ct-ui-button
      @click="$refs['picker'].openPoup()"
      type="error"
      style="margin-top: 20px"
      :customStyle="{height: '35px'}"
      >选择数字</ct-ui-button
    >
  </view>
</template>

<script>
export default {
  name: 'picker',
  data() {
    return {
      defaultValue: '3',
      options: [0, 1, 2, 3, 4, 5]
    }
  },
  methods: {
    change(value) {
      console.log('change value::', value)
    },
    confirm(value) {
      console.log('confirm value::', value)
    }
  }
}
</script>

<style scoped lang="scss">
.box {
  width: 50px;
  height: 50px;
  border-radius: 10px;
  background-color: #999999;
  margin-left: 25px;
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/multiPicker.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/multiPicker.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| title                | 中间/左上角的标题                                            | String                 | 选择      | -                                               | v1.0.12+ |
| -------------------- | ------------------------------------------------------------ | ---------------------- | --------- | ----------------------------------------------- | -------- |
| titleSize            | 标题文字大小，单位rpx                                        | Number ｜ String       | 32        | -                                               | v1.0.20+ |
| titleColor           | 标题文字颜色                                                 | String                 | #262F40   | -                                               | v1.0.20+ |
| value                | 默认选中                                                     | Number｜String｜Object | -         | -                                               | v1.0.12+ |
| immediateChange      | 是否在手指松开时立即触发 change 事件。若不开启则会在滚动动画结束后触发 change 事件。 | Boolean                | false     | true\|false                                     | v1.0.12+ |
| options              | 选择项                                                       | Array                  | []        | -                                               | v1.0.12+ |
| optionFontSize       | 字体大小，单位rpx                                            | Number ｜ String       | 32        | -                                               | v1.0.12+ |
| activeOptionFontSize | 选中的字体大小，单位rpx                                      | Number ｜ String       | 36        | -                                               | v1.0.20+ |
| color                | 未选中的颜色                                                 | String                 | #262F40   | -                                               | v1.0.20+ |
| activeColor          | 选中的颜色                                                   | String                 | #3860f5   | -                                               | v1.0.20+ |
| labelKey             | label 键名(显示在列表上）                                    | String                 | label     | -                                               | v1.0.12+ |
| valueKey             | value 键名                                                   | String                 | value     | -                                               | v1.0.12+ |
| operatePosition      | 按钮放置的位置                                               | String                 | bottom    | top 顶部 \| bottom 底部                         | v1.0.20+ |
| btnColor             | btn 颜色，只针对confirm有效                                  | String                 | primary   | default｜primary｜info｜warning｜error｜success | v1.0.12+ |
| showConfirmButton    | 是否显示确认按钮                                             | Boolean                | true      | true\|false                                     | v1.0.12+ |
| confirmText          | 确定按钮文字                                                 | String                 | 确定      | -                                               | v1.0.12+ |
| confirmTextSize      | 确定按钮文字大小(单位：operatePosition=top 为rpx，其他为px)  | Number\|String         | 14        | -                                               | v1.0.12+ |
| confirmTextColor     | 確定按钮文字颜色(operatePosition=top)                        | String                 | #3860f5   | -                                               | v1.0.20+ |
| confirmButtonWidth   | 确定按钮的宽度(单位：%)                                      | Number\|String         | 50        | -                                               | v1.0.12+ |
| showCancelButton     | 是否显示取消按钮                                             | Boolean                | true      | true\|false                                     | v1.0.12+ |
| cancelText           | 取消按钮文字                                                 | String                 | 取消      | -                                               | v1.0.12+ |
| cancelTextSize       | 取消按钮文字大小(单位：operatePosition=top 为rpx，其他为px)  | Number\|String         | 14        | -                                               | v1.0.12+ |
| cancelTextColor      | 取消按钮文字颜色(operatePosition=top)                        | String                 | #3860f5   | -                                               | v1.0.20+ |
| cancelButtonWidth    | 取消按钮的宽度(单位：%)                                      | Number\|String         | 50        | -                                               | v1.0.12+ |
| btnHeight            | 按钮高度(单位：px)                                           | Number\|String         | 44        | -                                               | v1.0.12+ |
| btnShape             | 按钮形状(见按钮组件)                                         | Number\|String         | 8         | -                                               | v1.0.12+ |
| btnReverse           | 按钮反转                                                     | Boolean                | false     | true\|false                                     | v1.0.12+ |
| itemHeight           | 项目的高度(单位：px)                                         | Number\|String         | 44        | -                                               | v1.0.12+ |
| visibleItemCount     | 每列中可见选项的数量                                         | Number\|String         | 5         | -                                               | v1.0.12+ |
| closeable            | 是否显示关闭图标                                             | Boolean                | false     | true\|false                                     | v1.0.12+ |
| closeIconPos         | 自定义关闭图标位置，top-left为左上角，top-right为右上角，    | String                 | top-right | top-left\|top-right                             | v1.0.12+ |
| disabled             | 是否禁用                                                     | Boolean                | false     | true\|false                                     | v1.0.12+ |
| safeAreaInsetBottom  | 是否为留出底部安全距离                                       | Boolean                | true      | true\|false                                     | v1.0.12+ |
| customStyle          | 自定义样式                                                   | Object                 | {}        |                                                 | v1.0.12+ |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/multiPicker.html#events)

| 事件名 | 说明 | 回调参数 | 版本 |
| ------ | ---- | -------- | ---- |
|        |      |          |      |

| open     | 打开弹窗后返回事件监听                                       | -                                                            | v1.0.12+ |
| -------- | ------------------------------------------------------------ | ------------------------------------------------------------ | -------- |
| close    | 关闭弹窗后返回事件监听/手动关闭弹窗方法（会触发关闭弹窗监听） | -                                                            | v1.0.12+ |
| change   | 选择                                                         | {picker: 实例, value: 选中的值, index: 选中的索引, indexs: 选中的数组返回值} | v1.0.12+ |
| confirm  | 点击确定按钮                                                 | {picker: 实例, value: 选中的值, index: 选中的索引, indexs: 选中的数组返回值} | v1.0.12+ |
| openPoup | 手动打开弹窗（会触发open监听）                               | -                                                            | v1.0.12+ |