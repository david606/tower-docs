# [CountDown 倒计时](http://mid.chinatowercom.cn:18080/appGuide/ui/countDown.html#countdown-倒计时)

该组件主要用于某个活动截止时间上，通过数字的变化，给用户明确的时间感受，提示用户进行某一个行为操作及相对事件监听。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/countDown.html#基本使用)

- 通过`time`参数定义倒计时时间，单位为`毫秒(ms)`
- 通过`format`参数定义时间格式，默认为`HH:mm:ss`
- 通过`type`设置主题样式，分别是`round`(圆形)，`square`(方形)， `default`(默认)
- 通过`bgColor`参数设置背景色（*只有在 type 为 round 和 square 有效*）
- 通过`autoStart`参数设置自动开始

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-count-down
        ref="countDown"
        :format="`HH时mm分ss秒`"
        :millisecond="false"
        type="default"
        time="60000"
        :auto-start="false"
      ></ct-ui-count-down>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'CountDown',
  data() {
    return {}
  }
}
</script>
```

### [设置时间格式](http://mid.chinatowercom.cn:18080/appGuide/ui/countDown.html#设置时间格式)

通过`format`进行时间格式设定，默认为`HH:mm:ss`
**时间标识：**

| 格式 | 描述                  |
| ---- | --------------------- |
| D    | 天（1-31）            |
| DD   | 天（01-31）           |
| H    | 小时（0-23）          |
| HH   | 小时（00-23）两位数   |
| m    | 分钟（0-59）          |
| mm   | 分钟（00-59）两位数   |
| s    | 秒（0-59）            |
| ss   | 秒（00-59）两位数     |
| S    | 毫秒（0-9）一位数     |
| SS   | 毫秒（00-99）两位数   |
| SSS  | 毫秒（000-999）三位数 |

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置时间格式">
      <ct-ui-count-down
        ref="countDown"
        :format="`DD天HH时mm分ss秒`"
        time="60000"
      ></ct-ui-count-down>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'CountDown',
  data() {
    return {}
  }
}
</script>
```

### [设置主题](http://mid.chinatowercom.cn:18080/appGuide/ui/countDown.html#设置主题)

通过`type`设置主题样式，可选值可以为`round`(圆形)，`square`(方形)， `default`(默认)

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置类型">
      <view class="sec-title">默认 default</view>
      <ct-ui-count-down
        ref="countDown"
        :format="`DD天HH时mm分ss秒`"
        type="default"
        time="60000"
      ></ct-ui-count-down>
      <view class="sec-title">圆形 round</view>
      <ct-ui-count-down
        :format="`HH时mm分ss秒`"
        type="round"
        time="60000"
        color="#fff"
      ></ct-ui-count-down>
      <view class="sec-title">方形 square</view>
      <ct-ui-count-down
        :format="`HH:mm:ss`"
        type="square"
        time="60000"
        color="#fff"
      ></ct-ui-count-down>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'CountDown',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;

  .title {
    margin: 20px 0;
  }

  .sec-title {
    font-size: 15px;
    margin: 20px 0;
  }
}
</style>
```

### [颜色反转](http://mid.chinatowercom.cn:18080/appGuide/ui/countDown.html#颜色反转)

通过`inverted`参数设置背景色跟文字颜色进行调换，只有在`type`为 **round(圆形)、square(方形)** 才起效

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="颜色反转">
      <ct-ui-count-down
        :format="`HH:mm:ss SSS`"
        type="square"
        time="60000"
        color="#f9ba02"
        bg-color="#000000"
      ></ct-ui-count-down>
      <ct-ui-count-down
        :format="`HH:mm:ss SSS`"
        type="square"
        time="60000"
        inverted
        color="#f9ba02"
        bg-color="#000000"
      ></ct-ui-count-down>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'CountDown',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;

  .title {
    margin: 20px 0;
  }
}
</style>
```

### [自定义样式](http://mid.chinatowercom.cn:18080/appGuide/ui/countDown.html#自定义样式)

通过`customStyle`参数设置自定义样式

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置自定义样式">
      <ct-ui-count-down
        :format="`HH时mm分ss秒`"
        :millisecond="false"
        type="default"
        time="60000"
        color="#f00"
        :custom-style="style"
      ></ct-ui-count-down>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'CountDown',
  data() {
    return {
      style: {
        color: '#f00'
      }
    }
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;

  .title {
    margin: 20px 0;
  }
}
</style>
```

### [手动控制开始结束](http://mid.chinatowercom.cn:18080/appGuide/ui/countDown.html#手动控制开始结束)

通过绑定`ref`进行手动控制 **开始、暂停、重置**

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="手动控制">
      <ct-ui-count-down
        ref="countDown"
        :format="`HH时mm分ss秒`"
        :millisecond="false"
        type="default"
        time="60000"
        :auto-start="false"
      ></ct-ui-count-down>
      <ct-ui-button
        style="display: inline-block;width:80px;margin:5px;"
        @click="reset"
        >重置</ct-ui-button
      >
      <ct-ui-button
        style="display: inline-block;width:80px;margin:5px;"
        @click="start"
        >开始</ct-ui-button
      >
      <ct-ui-button
        style="display: inline-block;width:80px;margin:5px;"
        @click="pause"
        >暂停</ct-ui-button
      >
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'CountDown',
  data() {
    return {}
  },
  methods: {
    reset() {
      this.$refs.countDown.reset()
    },
    start() {
      this.$refs.countDown.start()
    },
    pause() {
      this.$refs.countDown.pause()
    }
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;

  .title {
    margin: 20px 0;
  }
}
</style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/countDown.html#事件监听)

`change`事件可以时刻监听倒计时时间变化，`finish`事件可以监听倒计时结束

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="事件监听">
      <ct-ui-count-down
        :format="`HH时mm分ss秒 SSS`"
        :millisecond="false"
        type="round"
        time="60000"
        color="#fff"
        @change="changeListener"
        @finish="finishListener"
      ></ct-ui-count-down>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'CountDown',
  data() {
    return {}
  },
  methods: {
    changeListener(e) {
      console.log('change', e)
    },
    finishListener() {
      console.log('finish')
    }
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;

  .title {
    margin: 20px 0;
  }
}
</style>
```

### [独立使用](http://mid.chinatowercom.cn:18080/appGuide/ui/countDown.html#独立使用)

通过设置无插入内容单独进行使用

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="独立展示">
      <ct-ui-count-down
        ref="countDown"
        :format="`HH时mm分ss秒`"
        :millisecond="false"
        type="default"
        time="60000"
        :auto-start="false"
      >
        <view class="time">
          <text class="time__item">{{ timeData.days }}&nbsp;天</text>
          <text class="time__item">{{ timeData.hours }}&nbsp;时</text>
          <text class="time__item">{{ timeData.minutes }}&nbsp;分</text>
          <text class="time__item">{{ timeData.seconds }}&nbsp;秒</text>
        </view>
      </ct-ui-count-down>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'CountDown',
  data() {
    return {
      timeData: {}
    }
  },
  methods: {
    changeListener(e) {
      this.timeData = e
    }
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;

  .title {
    margin: 20px 0;
  }
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/countDown.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/countDown.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| *time（必须） | 倒计时时长，单位ms                                           | Number｜String | 0        | -                                      |
| ------------- | ------------------------------------------------------------ | -------------- | -------- | -------------------------------------- |
| format        | 时间格式，D/DD-日，H/HH-时，m/mm-分，s/ss-秒，S/SS/SSS-毫秒  | String         | HH:mm:ss | -                                      |
| type          | 主题类型                                                     | String         | default  | round(圆)\|square(方)\|default(无背景) |
| bgColor       | 背景色，支持hex&rgba，只有在type为round(圆)\|square(方)时，起效 | String         | #e34d59  | -                                      |
| color         | 文字颜色，支持hex&rgba                                       | String         | #000000  | -                                      |
| inverted      | 是否反转色                                                   | Boolean        | false    | true\|false                            |
| autoStart     | 是否自动开始                                                 | Boolean        | true     | true\|false                            |
| millisecond   | 是否展示毫秒倒计时                                           | Boolean        | false    | true\|false                            |
| customStyle   | 外部自定义样式                                               | Object         | -        | -                                      |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/countDown.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| change | 倒计时变化时触发 | 剩余时间集合 |
| ------ | ---------------- | ------------ |
| finish | 倒计时结束时触发 | -            |

#### [Methods](http://mid.chinatowercom.cn:18080/appGuide/ui/countDown.html#methods)

| 名称 | 说明 |
| ---- | ---- |
|      |      |

| start | 倒计时开始 |
| ----- | ---------- |
| pause | 倒计时暂停 |
| reset | 倒计时重置 |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/countDown.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

| default | 自定义倒计时内容 | -    |
| ------- | ---------------- | ---- |
|         |                  |      |