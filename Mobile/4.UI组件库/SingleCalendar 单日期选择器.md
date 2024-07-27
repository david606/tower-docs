# [SingleCalendar 单日期选择器](http://mid.chinatowercom.cn:18080/appGuide/ui/singleCalendar.html#singlecalendar-单日期选择器)

该组件主要用于选择或输入日期，有单选日期和选择一个时间段两种形式，只显示一个日历，年/月使用箭头切换。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/singleCalendar.html#基本使用)

- 通过`maxDate`参数控制最大可选日期
- 通过`minDate`参数控制最小可选日期
- 通过`mode`参数控制选择器模式

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="单选日期">
      <view class="demo-row-sel" @click="sel('date')">
        <view class="demo-row-sel-l">日期</view>
        <view class="demo-row-sel-r">{{ dateValue }}</view>
        <image
          class="demo-row-sel-img"
          src="../../static/images/ct_arrows.png"
        ></image>
      </view>
    </ct-demo-card>

    <ct-demo-card title="选择时间段">
      <view class="demo-row-sel" @click="sel('range')">
        <view class="demo-row-sel-l">时间段</view>
        <view class="demo-row-sel-r">{{ rangeValue }}</view>
        <image
          class="demo-row-sel-img"
          src="../../static/images/ct_arrows.png"
        ></image>
      </view>
    </ct-demo-card>

    <!-- 日历 -->
    <ct-ui-single-calendar
      ref="ctCalendar"
      :mode="calendar.mode"
      @ctCalendarConfirm="ctCalendarConfirm"
    >
    </ct-ui-single-calendar>
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {
      dateValue: '请选择',
      rangeValue: '请选择',
      calendar: {
        mode: '',
        minDate: '2021-12-05',
        maxDate: '2025-12-31'
      }
    }
  },
  onLoad() {
    _self = this
  },
  methods: {
    sel(e) {
      _self.calendar.mode = e
      _self.$refs.ctCalendar.show()
    },
    ctCalendarConfirm(e) {
      if (_self.calendar.mode == 'date') {
        _self.dateValue = e.result
      } else if (_self.calendar.mode == 'range') {
        _self.rangeValue = e.result
      }
    }
  }
}
</script>

<style></style>
```

### [设置最大可选日期](http://mid.chinatowercom.cn:18080/appGuide/ui/singleCalendar.html#设置最大可选日期)

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="单选日期">
      <view class="demo-row-sel" @click="sel('date')">
        <view class="demo-row-sel-l">日期</view>
        <view class="demo-row-sel-r">{{ dateValue }}</view>
        <image
          class="demo-row-sel-img"
          src="../../static/images/ct_arrows.png"
        ></image>
      </view>
    </ct-demo-card>

    <ct-demo-card title="选择时间段">
      <view class="demo-row-sel" @click="sel('range')">
        <view class="demo-row-sel-l">时间段</view>
        <view class="demo-row-sel-r">{{ rangeValue }}</view>
        <image
          class="demo-row-sel-img"
          src="../../static/images/ct_arrows.png"
        ></image>
      </view>
    </ct-demo-card>

    <!-- 日历 -->
    <ct-ui-single-calendar
      ref="ctCalendar"
      :mode="calendar.mode"
      :maxDate="calendar.maxDate"
      @ctCalendarConfirm="ctCalendarConfirm"
    >
    </ct-ui-single-calendar>
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {
      dateValue: '请选择',
      rangeValue: '请选择',
      calendar: {
        mode: '',
        minDate: '2021-12-05',
        maxDate: '2021-12-31'
      }
    }
  },
  onLoad() {
    _self = this
  },
  methods: {
    sel(e) {
      _self.calendar.mode = e
      _self.$refs.ctCalendar.show()
    },
    ctCalendarConfirm(e) {
      if (_self.calendar.mode == 'date') {
        _self.dateValue = e.result
      } else if (_self.calendar.mode == 'range') {
        _self.rangeValue = e.result
      }
    }
  }
}
</script>

<style></style>
```

### [设置最小可选日期](http://mid.chinatowercom.cn:18080/appGuide/ui/singleCalendar.html#设置最小可选日期)

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="单选日期">
      <view class="demo-row-sel" @click="sel('date')">
        <view class="demo-row-sel-l">日期</view>
        <view class="demo-row-sel-r">{{ dateValue }}</view>
        <image
          class="demo-row-sel-img"
          src="../../static/images/ct_arrows.png"
        ></image>
      </view>
    </ct-demo-card>

    <ct-demo-card title="选择时间段">
      <view class="demo-row-sel" @click="sel('range')">
        <view class="demo-row-sel-l">时间段</view>
        <view class="demo-row-sel-r">{{ rangeValue }}</view>
        <image
          class="demo-row-sel-img"
          src="../../static/images/ct_arrows.png"
        ></image>
      </view>
    </ct-demo-card>

    <!-- 日历 -->
    <ct-ui-single-calendar
      ref="ctCalendar"
      :mode="calendar.mode"
      :minDate="calendar.minDate"
      @ctCalendarConfirm="ctCalendarConfirm"
    >
    </ct-ui-single-calendar>
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {
      dateValue: '请选择',
      rangeValue: '请选择',
      calendar: {
        mode: '',
        minDate: '2021-12-05',
        maxDate: '2021-12-31'
      }
    }
  },
  onLoad() {
    _self = this
  },
  methods: {
    sel(e) {
      _self.calendar.mode = e
      _self.$refs.ctCalendar.show()
    },
    ctCalendarConfirm(e) {
      if (_self.calendar.mode == 'date') {
        _self.dateValue = e.result
      } else if (_self.calendar.mode == 'range') {
        _self.rangeValue = e.result
      }
    }
  }
}
</script>

<style></style>
```

### [设置日期选择器为 date 模式](http://mid.chinatowercom.cn:18080/appGuide/ui/singleCalendar.html#设置日期选择器为-date-模式)

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="单选日期">
      <view class="demo-row-sel" @click="sel('date')">
        <view class="demo-row-sel-l">日期</view>
        <view class="demo-row-sel-r">{{ dateValue }}</view>
        <image
          class="demo-row-sel-img"
          src="../../static/images/ct_arrows.png"
        ></image>
      </view>
    </ct-demo-card>

    <!-- 日历 -->
    <ct-ui-single-calendar
      ref="ctCalendar"
      :mode="calendar.mode"
      @ctCalendarConfirm="ctCalendarConfirm"
    >
    </ct-ui-single-calendar>
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {
      dateValue: '请选择',
      rangeValue: '请选择',
      calendar: {
        mode: '',
        minDate: '2021-12-05',
        maxDate: '2021-12-31'
      }
    }
  },
  onLoad() {
    _self = this
  },
  methods: {
    sel(e) {
      _self.calendar.mode = e
      _self.$refs.ctCalendar.show()
    },
    ctCalendarConfirm(e) {
      if (_self.calendar.mode == 'date') {
        _self.dateValue = e.result
      } else if (_self.calendar.mode == 'range') {
        _self.rangeValue = e.result
      }
    }
  }
}
</script>

<style></style>
```

### [设置日期选择器为 range 模式](http://mid.chinatowercom.cn:18080/appGuide/ui/singleCalendar.html#设置日期选择器为-range-模式)

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="选择时间段">
      <view class="demo-row-sel" @click="sel('range')">
        <view class="demo-row-sel-l">时间段</view>
        <view class="demo-row-sel-r">{{ rangeValue }}</view>
        <image
          class="demo-row-sel-img"
          src="../../static/images/ct_arrows.png"
        ></image>
      </view>
    </ct-demo-card>

    <!-- 日历 -->
    <ct-ui-single-calendar
      ref="ctCalendar"
      :mode="calendar.mode"
      @ctCalendarConfirm="ctCalendarConfirm"
    >
    </ct-ui-single-calendar>
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {
      dateValue: '请选择',
      rangeValue: '请选择',
      calendar: {
        mode: '',
        minDate: '2021-12-05',
        maxDate: '2021-12-31'
      }
    }
  },
  onLoad() {
    _self = this
  },
  methods: {
    sel(e) {
      _self.calendar.mode = e
      _self.$refs.ctCalendar.show()
    },
    ctCalendarConfirm(e) {
      if (_self.calendar.mode == 'date') {
        _self.dateValue = e.result
      } else if (_self.calendar.mode == 'range') {
        _self.rangeValue = e.result
      }
    }
  }
}
</script>

<style></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/singleCalendar.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/singleCalendar.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| mode    | 模式         | string | date       | date/range |
| ------- | ------------ | ------ | ---------- | ---------- |
| maxDate | 最大可选日期 | string | 今天       | —          |
| minDate | 最小可选日期 | String | 1950-01-01 | —          |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/singleCalendar.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| ctCalendarConfirm | 日期选择完成事件 | -    |
| ----------------- | ---------------- | ---- |
|                   |                  |      |