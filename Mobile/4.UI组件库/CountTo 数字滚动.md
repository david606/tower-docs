# [CountTo 数字滚动](http://mid.chinatowercom.cn:18080/appGuide/ui/countTo.html#countto-数字滚动)

该组件主要是对一些数值进行滚动效果展示时使用，可实现递增、递减的效果

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/countTo.html#基本使用)

- 通过`startVal`参数传入开始滚动的初始数值
- 通过`endVal`参数传入结束滚动的到达数值

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-count-to :startVal="startVal" :endVal="endVal"></ct-ui-count-to>
      <ct-ui-count-to :startVal="endVal" :endVal="startVal"></ct-ui-count-to>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'countTo',
  data() {
    return {
      startVal: 0,
      endVal: 100
    }
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;
  display: flex;
  flex-direction: column;
  .title {
    margin: 20px 0;
  }
}
</style>
```

### [滚动时间](http://mid.chinatowercom.cn:18080/appGuide/ui/countTo.html#滚动时间)

- 通过`duration`参数设置滚动到目标数值所需时间，单位 ms

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="滚动时间">
      <ct-ui-count-to
        :startVal="startVal"
        :endVal="endVal"
        :duration="duration"
      ></ct-ui-count-to>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'countTo',
  data() {
    return {
      startVal: 0,
      endVal: 100,
      duration: 4000
    }
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;
  display: flex;
  flex-direction: column;
  .title {
    margin: 20px 0;
  }
}
</style>
```

### [分隔符](http://mid.chinatowercom.cn:18080/appGuide/ui/countTo.html#分隔符)

- 通过`decimals`参数设置需要展示的小数位数
- 通过`decimal`参数设置十进制分割符
- 通过`separator`参数设置千位分隔符

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="分隔符">
      <ct-ui-count-to
        :startVal="0"
        :endVal="1"
        :duration="duration"
        :decimals="decimals"
        decimal="."
      ></ct-ui-count-to>
      <ct-ui-count-to
        :startVal="1000"
        :endVal="2000"
        :duration="duration"
        separator=","
      ></ct-ui-count-to>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'countTo',
  data() {
    return {
      duration: 4000,
      decimals: 2
    }
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;
  display: flex;
  flex-direction: column;
  .title {
    margin: 20px 0;
  }
}
</style>
```

### [自定义样式](http://mid.chinatowercom.cn:18080/appGuide/ui/countTo.html#自定义样式)

- 通过`fontSize`参数设置字体大小
- 通过`color`参数设置字体颜色
- 通过`bold`参数设置是否开启字体加粗

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义样式">
      <ct-ui-count-to
        style="display: block;"
        :startVal="startVal"
        :endVal="endVal"
      ></ct-ui-count-to>
      <ct-ui-count-to
        style="display: block;"
        :startVal="startVal"
        :endVal="endVal"
        :fontSize="30"
      ></ct-ui-count-to>
      <ct-ui-count-to
        style="display: block;"
        :startVal="startVal"
        :endVal="endVal"
        :fontSize="30"
        :bold="true"
      ></ct-ui-count-to>
      <ct-ui-count-to
        style="display: block;"
        :startVal="startVal"
        :endVal="endVal"
        :fontSize="30"
        color="rgb(235, 75, 75)"
        :bold="true"
      ></ct-ui-count-to>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'countTo',
  data() {
    return {
      startVal: 0,
      endVal: 100
    }
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;
  display: flex;
  flex-direction: column;
  .title {
    margin: 20px 0;
  }
}
</style>
```

### [滚动时间](http://mid.chinatowercom.cn:18080/appGuide/ui/countTo.html#滚动时间-1)

- 通过`duration`参数设置滚动到目标数值所需时间，单位 ms
- 通过`useEasing`参数设置是否在即将到达目标数值的时候，使用缓慢滚动的效果

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="滚动时间">
      <ct-ui-count-to
        :startVal="startVal"
        :endVal="endVal"
        :duration="duration"
      ></ct-ui-count-to>
      <ct-ui-count-to
        :startVal="startVal"
        :endVal="endVal"
        :duration="duration"
        :useEasing="true"
      ></ct-ui-count-to>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'countTo',
  data() {
    return {
      startVal: 0,
      endVal: 100,
      duration: 4000
    }
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;
  display: flex;
  flex-direction: column;
  .title {
    margin: 20px 0;
  }
}
</style>
```

### [调用功能](http://mid.chinatowercom.cn:18080/appGuide/ui/countTo.html#调用功能)

- 通过`autoplay`参数设置是否自动滚动
- 通过绑定`ref`进行手动调用组件上的功能

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="调用功能">
      <ct-ui-count-to
        :startVal="endVal"
        :endVal="startVal"
        :autoplay="false"
        ref="countTo"
      ></ct-ui-count-to>
      <view class="buttons">
        <ct-ui-button class="button" btnSize="middle" @click="choice(1)"
          >开始</ct-ui-button
        >
        <ct-ui-button class="button" btnSize="middle" @click="choice(2)"
          >暂停/继续</ct-ui-button
        >
        <ct-ui-button class="button" btnSize="middle" @click="choice(3)"
          >暂停</ct-ui-button
        >
        <ct-ui-button class="button" btnSize="middle" @click="choice(4)"
          >继续</ct-ui-button
        >
        <ct-ui-button class="button" btnSize="middle" @click="choice(5)"
          >重置</ct-ui-button
        >
      </view>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'countTo',
  data() {
    return {
      startVal: 0,
      endVal: 100
    }
  },
  methods: {
    choice(e) {
      switch (e) {
        case 1:
          this.$refs.countTo.start() // 开始
          break
        case 2:
          this.$refs.countTo.reStart() // 暂定状态
          break
        case 3:
          this.$refs.countTo.stop() // 暂停
          break
        case 4:
          this.$refs.countTo.resume() // 继续
          break
        case 5:
          this.$refs.countTo.reset() // 重置
          break
      }
    }
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;
  display: flex;
  flex-direction: column;
  .title {
    margin: 20px 0;
  }
  .buttons {
    display: flex;
    flex-wrap: wrap;
    .button {
      margin-bottom: 5px;
    }
  }
}
</style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/countTo.html#事件监听)

`start`事件可以监听开始滚动时触发，`end`事件可以监听完成滚动时触发，`restart`事件可以监听重置滚动时触发，`paused`事件可以监听暂停滚动时触发，`resume`事件可以监听继续滚动时触发

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="事件监听">
      <ct-ui-count-to
        :startVal="startVal"
        :endVal="endVal"
        :autoplay="false"
        ref="countTo"
        @start="start"
        @end="end"
        @restart="restart"
        @paused="paused"
        @resume="resume"
      ></ct-ui-count-to>
      <view class="buttons">
        <ct-ui-button class="button" btnSize="middle" @click="choice(1)"
          >开始</ct-ui-button
        >
        <ct-ui-button class="button" btnSize="middle" @click="choice(2)"
          >暂停/继续</ct-ui-button
        >
        <ct-ui-button class="button" btnSize="middle" @click="choice(3)"
          >暂停</ct-ui-button
        >
        <ct-ui-button class="button" btnSize="middle" @click="choice(4)"
          >继续</ct-ui-button
        >
        <ct-ui-button class="button" btnSize="middle" @click="choice(5)"
          >重置</ct-ui-button
        >
      </view>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'countTo',
  data() {
    return {
      startVal: 0,
      endVal: 100
    }
  },
  methods: {
    start() {
      console.log('开始')
    },
    end() {
      console.log('结束')
    },
    restart(e) {
      console.log('重置', e)
    },
    paused(e) {
      console.log('暂停', e)
    },
    resume(e) {
      console.log('继续', e)
    },
    choice(e) {
      switch (e) {
        case 1:
          this.$refs.countTo.start() // 开始
          break
        case 2:
          this.$refs.countTo.reStart() // 暂定状态
          break
        case 3:
          this.$refs.countTo.stop() // 暂停
          break
        case 4:
          this.$refs.countTo.resume() // 继续
          break
        case 5:
          this.$refs.countTo.reset() // 重置
          break
      }
    }
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;
  display: flex;
  flex-direction: column;
  .title {
    margin: 20px 0;
  }
  .buttons {
    display: flex;
    flex-wrap: wrap;
    .button {
      margin-bottom: 5px;
    }
  }
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/countTo.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/countTo.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| startVal  | 开始的值                                         | [Number,String]  | 0       | -          |
| --------- | ------------------------------------------------ | ---------------- | ------- | ---------- |
| content   | 目标数值                                         | [Number,String]  | 1       | -          |
| select    | 对应显示内容类名                                 | String           |         | -          |
| duration  | 滚动到目标数值所需时间，单位ms                   | Number           | 2000    | -          |
| autoplay  | 是否自动滚动                                     | Boolean          | false   | true/false |
| decimals  | 需要展示的小数位数                               | Number           | 0       | -          |
| useEasing | 是否在即将到达目标数值的时候，使用缓慢滚动的效果 | Boolean          | false   | true/false |
| decimal   | 十进制分割符                                     | [String, Number] | .       | -          |
| separator | 千分位分隔符                                     | String           | ,       | -          |
| color     | 字体颜色                                         | String           | #909399 | -          |
| fontSize  | 字体大小，单位px                                 | Number           | 20      | -          |
| bold      | 是否加粗字体                                     | Boolean          | false   | true/false |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/countTo.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| start   | 开始滚动时触发 |          |
| ------- | -------------- | -------- |
| end     | 滚动结束时触发 |          |
| restart | 重置时触发     | 当前数值 |
| paused  | 暂停时触发     | 当前数值 |
| resume  | 继续时触发     | 当前数值 |

#### [Methods](http://mid.chinatowercom.cn:18080/appGuide/ui/countTo.html#methods)

| 名称 | 说明 | 所需参数 |
| ---- | ---- | -------- |
|      |      |          |

| start   | 开始滚动      |      |
| ------- | ------------- | ---- |
| reStart | 暂停/继续滚动 |      |
| stop    | 暂停滚动      |      |
| resume  | 继续滚动      |      |
| reset   | 重置          |      |