# [Calendar 日期选择器](http://mid.chinatowercom.cn:18080/appGuide/ui/calendar.html#calendar-日期选择器)

此组件用于选择单个日期，多个日期及选择范围日期等，可展示自定义主题及农历，日期日历会被包裹在底部弹起的容器中。**`(v1.0.15+支持)`**

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/calendar.html#基本使用)

- 通过`visible`参数控制打开或收起日历弹窗。
- 通过`mode`参数指定选择日期模式，包含单选/多选/范围选择。

```vue
<template>
  <view class="demo-page">
    <!-- 日历 -->
    <ct-ui-calendar
      ref="ctCalendar"
      :visible.sync="visible"
      :defaultDate="['2023-01-12']"
      radius="20"
      @confirm="confirm"
      @close="close"
    >
    </ct-ui-calendar>

    <ct-ui-button @click="visible = true" type="primary">选择日期</ct-ui-button>
  </view>
</template>

<script>
export default {
  data() {
    return {
      visible: false
    }
  },
  methods: {
    confirm(e) {
      this.visible = false
      console.log('选择的日期：', e)
    },
    close() {
      this.visible = false
    }
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 24rpx;
}
</style>
```

### [日历模式](http://mid.chinatowercom.cn:18080/appGuide/ui/calendar.html#日历模式)

- mode 为`single`只能选择单个日期
- mode 为`multiple`可以选择多个日期
- mode 为`range`可以选择日期范围

#### [单日期模式](http://mid.chinatowercom.cn:18080/appGuide/ui/calendar.html#单日期模式)

选择日期后，点击底部的确定按钮触发回调事件，回调参数为一个数组，获取数组的第一个元素即可。如下格式：

```javascript
;['2022-12-05']
<template>
  <view class="demo-page">
    <!-- 日历 -->
    <ct-ui-calendar
      ref="ctCalendar"
      mode="single"
      :visible.sync="visible"
      :defaultDate="['2023-01-12']"
      radius="20"
      @confirm="confirm"
      @close="close"
    >
    </ct-ui-calendar>

    <ct-ui-button @click="visible = true" type="primary">选择日期</ct-ui-button>
  </view>
</template>

<script>
export default {
  data() {
    return {
      visible: false
    }
  },
  methods: {
    confirm(e) {
      this.visible = false
      console.log('选择的日期：', e, e[0])
    },
    close() {
      this.visible = false
    }
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 24rpx;
}
</style>
```

#### [多日期模式](http://mid.chinatowercom.cn:18080/appGuide/ui/calendar.html#多日期模式)

选择多个日期后，点击底部的确定按钮触发回调事件，回调参数为一个数组。如下格式：

```javascript
;['2023-01-12', '2023-01-13', '2023-01-14']
<template>
  <view class="demo-page">
    <!-- 日历 -->
    <ct-ui-calendar
      ref="ctCalendar"
      mode="multiple"
      :visible.sync="visible"
      :defaultDate="['2023-01-12']"
      radius="20"
      @confirm="confirm"
      @close="close"
    >
    </ct-ui-calendar>

    <ct-ui-button @click="visible = true" type="primary">选择日期</ct-ui-button>
  </view>
</template>

<script>
export default {
  data() {
    return {
      visible: false
    }
  },
  methods: {
    confirm(e) {
      this.visible = false
      console.log('选择的日期：', e)
    },
    close() {
      this.visible = false
    }
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 24rpx;
}
</style>
```

#### [日期范围模式](http://mid.chinatowercom.cn:18080/appGuide/ui/calendar.html#日期范围模式)

此模式用于选择一个日期范围，比如住酒店的入住到离店的日期范围，格式如下：

```javascript
;['2023-01-12', '2023-01-13', '2023-01-14']
<template>
  <view class="demo-page">
    <!-- 日历 -->
    <ct-ui-calendar
      ref="ctCalendar"
      mode="multiple"
      :visible.sync="visible"
      :defaultDate="['2023-01-12']"
      radius="20"
      @confirm="confirm"
      @close="close"
    >
    </ct-ui-calendar>

    <ct-ui-button @click="visible = true" type="primary">选择日期</ct-ui-button>
  </view>
</template>

<script>
export default {
  data() {
    return {
      visible: false
    }
  },
  methods: {
    confirm(e) {
      this.visible = false
      console.log('选择的日期：', e)
    },
    close() {
      this.visible = false
    }
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 24rpx;
}
</style>
```

### [区间模式（ mode = range 起效）](http://mid.chinatowercom.cn:18080/appGuide/ui/calendar.html#区间模式-mode-range-起效)

- **`v1.0.16+`** 支持
- 通过`rangeMode`可以设置当前时间所在的区间时间段，`week` 周模式（最大日期为当前的日期）、 `month` 月模式、 `year` 年模式
- 优先级高于 defaultDate

```vue
<template>
  <ct-ui-calendar
    ref="ctCalendar"
    mode="range"
    title="区间模式"
    rangeMode="week"
    :visible.sync="visible"
    :defaultDate="['2023-01-12', '2023-01-26']"
    :closeable="false"
    radius="20"
  >
  </ct-ui-calendar>
</template>

<script>
export default {
  data() {
    return {
      visible: true
    }
  }
}
</script>
```

### [快捷选择（ mode = range 起效）](http://mid.chinatowercom.cn:18080/appGuide/ui/calendar.html#快捷选择-mode-range-起效)

- **`v1.0.18+`** 支持
- 通过`options`可以设置快捷选项的选项值，格式[{value: 7, selected: true}, {value: 30, selected: false}, {value: 60}, {value: 90}]

```vue
<template>
  <ct-ui-calendar
    ref="ctCalendar"
    mode="range"
    title="快捷选择"
    :options="options"
    :visible.sync="visible"
    :defaultDate="['2023-01-12', '2023-01-26']"
    :closeable="false"
    radius="20"
  >
  </ct-ui-calendar>
</template>

<script>
export default {
  data() {
    return {
      visible: true,
      options: [
        {value: 7, selected: true},
        {value: 30, selected: false},
        {value: 60},
        {value: 90}
      ]
    }
  }
}
</script>
```

### [自定义颜色](http://mid.chinatowercom.cn:18080/appGuide/ui/calendar.html#自定义颜色)

通过 color 可以更改主题色，用于更新按钮颜色、日期选择色

```vue
<template>
  <view class="demo-page">
    <ct-ui-calendar
      ref="ctCalendar"
      mode="single"
      title="自定义日期选择"
      color="#3E80F8"
      :visible.sync="visible"
      :defaultDate="['2023-01-12']"
      :closeable="false"
      radius="20"
      @confirm="confirm"
      @close="close"
    >
    </ct-ui-calendar>
  </view>
</template>

<script>
export default {
  data() {
    return {
      visible: false
    }
  },
  methods: {
    confirm(e) {
      this.visible = false
      console.log('选择的日期：', e)
    },
    close() {
      this.visible = false
    }
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 24rpx;
}
</style>
```

### [最大日期](http://mid.chinatowercom.cn:18080/appGuide/ui/calendar.html#最大日期)

通过设置 maxDate 进行控制最大的可选日期

```vue
<template>
  <view class="demo-page">
    <!-- 日历 -->
    <ct-ui-calendar
      ref="ctCalendar"
      :visible.sync="visible"
      :maxDate="maxDate"
      :defaultDate="['2023-01-12']"
      radius="20"
      @confirm="confirm"
      @close="close"
    >
    </ct-ui-calendar>

    <ct-ui-button @click="visible = true" type="primary">选择日期</ct-ui-button>
  </view>
</template>

<script>
const d = new Date()
const year = d.getFullYear()
let month = d.getMonth() + 1
month = month < 10 ? `0${month}` : month
const date = d.getDate()
export default {
  data() {
    return {
      visible: false,
      maxDate: `${year}-${month}-${date + 10}`
    }
  },
  methods: {
    confirm(e) {
      this.visible = false
      console.log('选择的日期：', e)
    },
    close() {
      this.visible = false
    }
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 24rpx;
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/calendar.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/calendar.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| visible             | 是否显示日历弹窗                                             | Boolean                   | false                   | true \| false           | v1.0.15+ |
| ------------------- | ------------------------------------------------------------ | ------------------------- | ----------------------- | ----------------------- | -------- |
| title               | 日历顶部标题                                                 | String                    | 日期选择                | -                       | v1.0.15+ |
| showTitle           | 是否显示标题                                                 | Boolean                   | true                    | true \| false           | v1.0.15+ |
| showSubtitle        | 是否显示副标题                                               | Boolean                   | true                    | true \| false           | v1.0.15+ |
| mode                | 日期选择模式，single-单个日期、multiple-多个日期、range-日期范围 | string                    | single                  | single｜multiple｜range | v1.0.15+ |
| startText           | 第一个日期底部的提示文字（mode=range）                       | string                    | 开始                    | —                       | v1.0.15+ |
| endText             | 最后一个日期底部的提示文字（mode=range）                     | String                    | 结束                    | —                       | v1.0.15+ |
| customList          | 自定义列表                                                   | Array                     | []                      | —                       | v1.0.15+ |
| options             | 快捷选项,近N天(格式：见示例说明)                             | Array                     | []                      | —                       | v1.0.18+ |
| labelColor          | 文本色，对头部的title及日期、星期有效                        | String                    | #303133                 | —                       | v1.0.15+ |
| color               | 主题色，对底部按钮和选中日期有效                             | String                    | #eb4b4b                 | —                       | v1.0.15+ |
| minDate             | 最小的可选日期(默认不限)                                     | String\|Number            | 0                       | —                       | v1.0.15+ |
| maxDate             | 最大可选日期(默认不限)                                       | String\|Number            | 0                       | —                       | v1.0.15+ |
| defaultDate         | 默认选中的日期，mode为multiple或range是必须为数组格式        | Array｜String｜Date｜null | null                    | —                       | v1.0.15+ |
| maxCount            | 最多可选多少个日期，默认为number的最大值（mode=multiple）    | String｜Number            | Number.MAX_SAFE_INTEGER | —                       | v1.0.15+ |
| rowHeight           | 日期行高(px)                                                 | String｜Number            | 56                      | —                       | v1.0.15+ |
| formatter           | 日期格式化函数                                               | Function\|null            | null                    | —                       | v1.0.15+ |
| showLunar           | 是否显示农历                                                 | Boolean                   | false                   | true \| false           | v1.0.15+ |
| showMark            | 是否显示月份背景色                                           | Boolean                   | true                    | true \| false           | v1.0.15+ |
| confirmText         | 确定按钮的文字                                               | String                    | 确定                    | -                       | v1.0.15+ |
| confirmDisabledText | 确认按钮处于禁用状态时的文字                                 | String                    | 确定                    | -                       | v1.0.15+ |
| showTodayBtn        | 是否显示今日按钮                                             | Boolean                   | true                    | true \| false           | v1.0.15+ |
| todayText           | 今日按钮的文字                                               | String                    | 今天                    | -                       | v1.0.15+ |
| todayTextColor      | 今日按钮的文字颜色                                           | String                    | #5f6881                 | -                       | v1.0.15+ |
| mask                | 是否打开蒙版                                                 | Boolean                   | true                    | true \| false           | v1.0.15+ |
| maskBgColor         | 蒙版背景色                                                   | String                    | rgba(0, 0, 0, .2)       | -                       | v1.0.15+ |
| closeOnClickOverlay | 是否允许点击遮罩关闭日历                                     | Boolean                   | false                   | true \| false           | v1.0.15+ |
| readonly            | 是否为只读状态，只读状态下禁止选择日期                       | Boolean                   | false                   | true \| false           | v1.0.15+ |
| showConfirm         | 是否展示确认按钮                                             | Boolean                   | true                    | true \| false           | v1.0.15+ |
| closeable           | 是否显示关闭图标                                             | Boolean                   | true                    | true \| false           | v1.0.15+ |
| rangeMode           | 区间模式，week 周模式 month 月模式 year 年模式（mode = range） | String                    | null                    | week｜month\|year       | v1.0.16+ |
| minRange            | 日期区间选择最少天数，默认无限制（mode = range）             | Number｜String            | Number.MAX_SAFE_INTEGER | -                       | v1.0.20+ |
| rangeMinPrompt      | 范围最少选择天数时的提示文案（mode = range）                 | String                    |                         | -                       | v1.0.20+ |
| maxRange            | 日期区间最多可选天数，默认无限制（mode = range）             | Number｜String            | Number.MAX_SAFE_INTEGER | -                       | v1.0.15+ |
| rangePrompt         | 范围选择超过最多可选天数时的提示文案（mode = range）         | String                    |                         | -                       | v1.0.15+ |
| showRangePrompt     | 范围选择超过最多/最少天数时，是否展示提示文案（mode = range） | Boolean                   | true                    | true \| false           | v1.0.15+ |
| allowSameDay        | 否允许日期范围的起止时间为同一天（mode = range）             | Boolean                   | false                   | true \| false           | v1.0.15+ |
| radius              | 圆角值                                                       | String\|Number            | 0                       | -                       | v1.0.15+ |
| monthNum            | 最多展示月份数量                                             | String\|Number            | 3                       | -                       | v1.0.15+ |
| zIndex              | 弹出的z-index层级                                            | String\|Number            | 10                      | -                       | v1.0.15+ |
| safeAreaInsetBottom | 是否为留出底部安全距离                                       | Boolean                   | true                    | true \| false           | v1.0.15+ |

#### [Methods](http://mid.chinatowercom.cn:18080/appGuide/ui/calendar.html#methods)

| 方法名 | 说明 | 版本 |
| ------ | ---- | ---- |
|        |      |      |

| setFormatter | 为兼容微信小程序而暴露的内部方法 | v1.0.15+ |
| ------------ | -------------------------------- | -------- |
|              |                                  |          |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/calendar.html#events)

| 事件名 | 说明 | 返回值 | 版本 |
| ------ | ---- | ------ | ---- |
|        |      |        |      |

| confirm    | 日期选择完成后触发，若show-confirm为true，则点击确认按钮后触发 | 选择日期相关的返回参数，数组格式 | v1.0.15+ |
| ---------- | ------------------------------------------------------------ | -------------------------------- | -------- |
| close      | 日历关闭时触发                                               | -                                | v1.0.15+ |
| quickClick | 快捷方式点击触发                                             | 返回选中的快捷区间               | v1.0.19+ |
| today      | 点击今日按钮触发                                             | 返回今日时间                     | v1.0.19+ |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/calendar.html#slots)

| name | 说明 | 作用域 | 版本 |
| ---- | ---- | ------ | ---- |
|      |      |        |      |

| footer | 确定按钮底部区域 | -    | v1.0.15+ |
| ------ | ---------------- | ---- | -------- |
|        |                  |      |          |