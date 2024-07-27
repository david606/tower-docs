# [DateTimePicker 时间日期选择器](http://mid.chinatowercom.cn:18080/appGuide/ui/dateTimePicker.html#datetimepicker-时间日期选择器)

该组件一般用于时间日期选择。

```text
itemHeight 由于在nvue中存在转换偏差，需要设置以px为单位的值
```

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/dateTimePicker.html#基本使用)

- 通过`title`参数设置顶部标题
- 通过`value`参数设置默认的时间日期
- 通过`radius`参数设置操作面板圆角值，默认 rpx
- 通过`overlay`参数设置是否显示遮罩层
- 通过`closeOnClickOverlay`参数设置是否可以点击遮罩层关闭

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基础使用">
      <ct-ui-datetime-picker
        title="基础使用"
        :value="defaultValue"
        @change="change"
        @confirm="confirm"
      >
        <text class="button"> 基础使用 </text>
      </ct-ui-datetime-picker>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      defaultValue: '2023-03-14 12:22:01'
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

<style lang="scss">
.demo {
  padding: 30rpx;
}
.button {
  height: 70rpx;
  display: block;
  background: #eb4b4b;
  border-radius: 8rpx;
  line-height: 70rpx;
  display: block;
  padding: 0 40rpx;
  color: #fff;
  font-size: 28rpx;
}
</style>
```

### [模式切换](http://mid.chinatowercom.cn:18080/appGuide/ui/dateTimePicker.html#模式切换)

- 通过`mode`参数设置显示的时间模式，支持 date、time、timeS、datetime、datetimeS、year-month 6 种模式
- 通过`maxDate`、`minDate`参数设置最大最小日期
- 通过`maxHour`、`minHour`参数设置最大最小小时
- 通过`maxMinute`、`minMinute`参数设置最大最小分钟
- 通过`maxSecond`、`minSecond`参数设置最大最小秒数

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="完整日期">
      <ct-ui-datetime-picker
        title="完整日期"
        :value="defaultValue"
        mode="datetimeS"
        @change="change"
        @confirm="confirm"
      >
        <text class="button"> 完整日期 datetimeS </text>
      </ct-ui-datetime-picker>
    </ct-demo-card>
    <ct-demo-card title="完整日期(不带秒)">
      <ct-ui-datetime-picker
        title="完整日期(不带秒)"
        :value="defaultValue1"
        mode="datetime"
        @change="change"
        @confirm="confirm"
      >
        <text class="button"> 完整日期(不带秒) datetime </text>
      </ct-ui-datetime-picker>
    </ct-demo-card>
    <ct-demo-card title="日期(年月日)">
      <ct-ui-datetime-picker
        title="日期(年月日)"
        :value="defaultValue2"
        mode="date"
        @change="change"
        @confirm="confirm"
      >
        <text class="button"> 日期(年月日) date </text>
      </ct-ui-datetime-picker>
    </ct-demo-card>
    <ct-demo-card title="时间">
      <ct-ui-datetime-picker
        title="时间"
        :value="defaultValue3"
        mode="time"
        @change="change"
        @confirm="confirm"
      >
        <text class="button"> 时间 time </text>
      </ct-ui-datetime-picker>
    </ct-demo-card>
    <ct-demo-card title="年月">
      <ct-ui-datetime-picker
        title="年月"
        :value="defaultValue4"
        mode="year-month"
        @change="change"
        @confirm="confirm"
      >
        <text class="button"> 年月 year-month </text>
      </ct-ui-datetime-picker>
    </ct-demo-card>
    <ct-demo-card title="区间限制">
      <ct-ui-datetime-picker
        title="年月"
        :value="defaultValue4"
        mode="year-month"
        maxDate="2024-10-01"
        @change="change"
        @confirm="confirm"
      >
        <text class="button"> 区间限制 </text>
      </ct-ui-datetime-picker>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      defaultValue: '2023-03-14 12:22:01',
      defaultValue1: '2023-03-14 12:22',
      defaultValue2: '2023-03-14',
      defaultValue3: '12:22',
      defaultValue4: '2023-03'
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

<style lang="scss">
.demo {
  padding: 30rpx;
}
.button {
  height: 70rpx;
  display: block;
  background: #eb4b4b;
  border-radius: 8rpx;
  line-height: 70rpx;
  display: block;
  padding: 0 40rpx;
  color: #fff;
  font-size: 28rpx;
}
</style>
```

### [格式化日期](http://mid.chinatowercom.cn:18080/appGuide/ui/dateTimePicker.html#格式化日期)

- 通过 `format` 参数设置格式化处理

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="格式化日期">
      <ct-ui-datetime-picker
        title="格式化日期"
        :value="defaultValue"
        mode="date"
        ref="datetimePicker"
        :format="formatter"
        @change="change"
        @confirm="confirm"
      >
        <text class="button"> 格式化日期 </text>
      </ct-ui-datetime-picker>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      defaultValue2: '2023-03-14'
    }
  },
  onReady() {
    // 微信小程序需要用此写法
    // this.$nextTick(() => {
    //     this.$refs.datetimePicker.setFormatter(this.formatter)
    // })
  },
  methods: {
    change(value) {
      console.log('change value::', value)
    },
    confirm(value) {
      console.log('confirm value::', value)
    },
    formatter(type, value) {
      if (type === 'year') {
        return `${value}年`
      }
      if (type === 'month') {
        return `${value}月`
      }
      if (type === 'day') {
        return `${value}日`
      }
      return value
    }
  }
}
</script>

<style lang="scss">
.demo {
  padding: 30rpx;
}
.button {
  height: 70rpx;
  display: block;
  background: #eb4b4b;
  border-radius: 8rpx;
  line-height: 70rpx;
  display: block;
  padding: 0 40rpx;
  color: #fff;
  font-size: 28rpx;
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/dateTimePicker.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/dateTimePicker.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| title                | 标题                                                         | String           | -                  | -                                                            | v1.0.20+ |
| -------------------- | ------------------------------------------------------------ | ---------------- | ------------------ | ------------------------------------------------------------ | -------- |
| titleSize            | 标题文字大小，单位rpx                                        | Number ｜ String | 34                 | -                                                            | v1.0.20+ |
| titleColor           | 标题文字颜色                                                 | String           | #262F40            | -                                                            | v1.0.20+ |
| titleBorder          | 是否标题边框                                                 | Boolean          | true               | true \| false                                                | v1.0.39+ |
| value                | 默认选中                                                     | String           | -                  | -                                                            | v1.0.18+ |
| immediateChange      | 是否在手指松开时立即触发 change 事件                         | Boolean          | false              | true \| false                                                | v1.0.20+ |
| mode                 | 展示格式                                                     | String           | date               | date 日期选择 time 时间选择 timeS 时间选择（时分秒） year-month 年月选择 datetime 日期时间选择 datetimeS 日期时间选择(含秒) | v1.0.20+ |
| optionFontSize       | 字体大小，单位rpx                                            | Number ｜ String | 32                 | -                                                            | v1.0.20+ |
| activeOptionFontSize | 选中的字体大小，单位rpx                                      | Number ｜ String | 36                 | -                                                            | v1.0.20+ |
| activeBold           | 选中是否加粗                                                 | Boolean          | false              | -                                                            | v1.0.33+ |
| indicatorColor       | 选中边框颜色                                                 | String           | #E4E8F0            | -                                                            | v1.0.33+ |
| color                | 未选中的颜色                                                 | String           | #505C73            | -                                                            | v1.0.20+ |
| activeColor          | 选中的颜色                                                   | String           | #3860f5            | -                                                            | v1.0.20+ |
| maxDate              | 可选的最大时间, 时间戳或者时间格式，如2303654400000 / 2023-10-01 | Number ｜ String | 最大默认值为后20年 | -                                                            | v1.0.20+ |
| minDate              | 可选的最小时间, 时间戳或者时间格式，如2303654400000 / 2023-10-01 | Number ｜ String | 最小默认值为前20年 | -                                                            | v1.0.20+ |
| minHour              | 可选的最小小时，仅mode=time有效                              | Number           | 0                  | -                                                            | v1.0.20+ |
| maxHour              | 可选的最大小时，仅mode=time有效                              | Number           | 23                 | -                                                            | v1.0.20+ |
| minMinute            | 可选的最小分钟，仅mode=time有效                              | Number           | 0                  | -                                                            | v1.0.20+ |
| maxMinute            | 可选的最大分钟，仅mode=time有效                              | Number           | 59                 | -                                                            | v1.0.20+ |
| minSecond            | 可选的最小秒钟，仅mode=time有效                              | Number           | 0                  | -                                                            | v1.0.20+ |
| maxSecond            | 可选的最大秒钟，仅mode=time有效                              | Number           | 59                 | -                                                            | v1.0.20+ |
| yearStep             | 年间隔                                                       | Number           | 1                  | -                                                            | v1.0.32+ |
| monthStep            | 月间隔                                                       | Number           | 1                  | -                                                            | v1.0.32+ |
| dayStep              | 日间隔                                                       | Number           | 1                  | -                                                            | v1.0.32+ |
| hourStep             | 时间隔                                                       | Number           | 1                  | -                                                            | v1.0.32+ |
| minuteStep           | 分间隔                                                       | Number           | 1                  | -                                                            | v1.0.32+ |
| secondStep           | 秒间隔                                                       | Number           | 1                  | -                                                            | v1.0.32+ |
| showConfirmButton    | 是否显示确认按钮                                             | Boolean          | true               | true \| false                                                | v1.0.20+ |
| confirmText          | 确定按钮文字                                                 | String           | 确定               | -                                                            | v1.0.20+ |
| confirmTextSize      | 确定按钮文字大小, 单位rpx                                    | Number \| String | 30                 | -                                                            | v1.0.20+ |
| confirmTextColor     | 確定按钮文字颜色                                             | String           | #3860f5            | -                                                            | v1.0.20+ |
| showCancelButton     | 是否显示取消按钮                                             | Boolean          | true               | true \| false                                                | v1.0.20+ |
| cancelText           | 取消按钮文字                                                 | String           | 取消               | -                                                            | v1.0.20+ |
| cancelTextSize       | 取消按钮文字大小, 单位rpx                                    | Number \| String | 30                 | -                                                            | v1.0.20+ |
| cancelTextColor      | 取消按钮文字颜色                                             | String           | #3860f5            | -                                                            | v1.0.20+ |
| reverse              | 取消/确认按钮反转                                            | Boolean          | false              | true ｜ false                                                | v1.0.20+ |
| radius               | 圆角，单位rpx                                                | Number ｜ String | 8                  | -                                                            | v1.0.20+ |
| itemHeight           | 项目的高度，单位rpx，nvue中由于rpx转px有偏差，请设置以px为单位的高度 | Number ｜ String | 112                | -                                                            | v1.0.20+ |
| visibleItemCount     | 每列中可见选项的数量                                         | Number ｜ String | 5                  | -                                                            | v1.0.20+ |
| format               | 针对做个格式化， function(type, value) {return value}        | null ｜ function | null               | -                                                            | v1.0.20+ |
| disabled             | 是否禁用                                                     | Boolean          | false              | true ｜ false                                                | v1.0.20+ |
| overlay              | 是否显示遮罩层                                               | Boolean          | true               | false \| true                                                | v1.0.18+ |
| overlayBgColor       | 蒙版背景色                                                   | String           | rgba(0, 0, 0, .2)  | -                                                            | v1.0.18+ |
| overlayOpacity       | 蒙版背景色透明度                                             | String           | 0.7                | -                                                            | v1.0.33+ |
| closeOnClickOverlay  | 是否可以点击遮罩层关闭                                       | Boolean          | true               | false \| true                                                | v1.0.20+ |
| emptyType            | 空数据类型, 对应的是default组件参数                          | String           | nodata             | -                                                            | v1.0.39+ |
| emptyText            | 空数据文字，对应的是default组件参数                          | String           | -                  | -                                                            | v1.0.39+ |
| emptyImg             | 空数据图片                                                   | String           | -                  | -                                                            | v1.0.39+ |
| emptyImgWidth        | 是否可以点击遮罩层关闭                                       | Number \| String | 240                | -                                                            | v1.0.39+ |
| emptyImgHeight       | 是否可以点击遮罩层关闭                                       | Number \| String | 240                | -                                                            | v1.0.39+ |
| safeAreaInsetBottom  | 是否为留出底部安全距离                                       | Boolean          | true               | true \| false                                                | v1.0.20+ |
| customStyle          | 自定义样式                                                   | Object           | {}                 | -                                                            | v1.0.20+ |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/dateTimePicker.html#events)

| 事件名 | 说明 | 返回值 | 版本 |
| ------ | ---- | ------ | ---- |
|        |      |        |      |

| open    | 打开日期选择器事件     | -                                                        | v1.0.20+ |
| ------- | ---------------------- | -------------------------------------------------------- | -------- |
| close   | 关闭日期选择器事件     | -                                                        | v1.0.20+ |
| confirm | 点击确认按钮事件       | value:返回所选时间，mode:当前模式，indexs:当前选中的索引 | v1.0.20+ |
| change  | 当选择值变化时触发事件 | value:返回所选时间，mode:当前模式，indexs:当前选中的索引 | v1.0.20+ |