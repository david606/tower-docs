# [LineProgress 进度条](http://mid.chinatowercom.cn:18080/appGuide/ui/LineProgress.html#lineprogress-进度条)

该组件主要用于在处理任务时，实时的，以线型形式显示处理任务的速度，完成度，剩余未完成任务量的大小。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/LineProgress.html#基本使用)

- 通过`degree`参数定义进度条的完成百分比
- 通过`lineStyle`参数传入线形进度条的样式
- 通过`completeStyle`参数传入已完成的进度条样式

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-line-progress
        ref="LineProgress"
        :degree="degree"
        :lineStyle="lineStyle"
        :completeStyle="completeStyle"
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'LineProgress',
  data() {
    return {
      degree: 48,
      lineStyle: {
        width: '400rpx',
        height: '60rpx',
        backgroundColor: '#E7E7E7FF',
        borderRadius: '30rpx',
        margin: '20rpx 20rpx'
      },
      completeStyle: {
        backgroundColor: '#EB4B4BFF'
      }
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [线型渐变进度条](http://mid.chinatowercom.cn:18080/appGuide/ui/LineProgress.html#线型渐变进度条)

通过`type`参数设置**gradual**则为线型渐变进度条，通过`gradient`参数传入渐变色

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="线型渐变进度条">
      <ct-ui-line-progress
        ref="LineProgress"
        type="gradual"
        :gradient="gradient"
        :degree="degree"
        :lineStyle="lineStyle"
        :completeStyle="completeStyle"
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'LineProgress',
  data() {
    return {
      degree: 60,
      gradient: ['#EB8E4BFF', '#EB4B4BFF'],
      lineStyle: {
        width: '80%',
        height: '30rpx',
        backgroundColor: '#E7E7E7FF',
        borderRadius: '20rpx',
        margin: '0 20rpx'
      },
      completeStyle: {
        backgroundColor: '#EB4B4BFF'
      }
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [环形进度条](http://mid.chinatowercom.cn:18080/appGuide/ui/LineProgress.html#环形进度条)

通过`type`参数设置**annular**则为环形进度条，通过`canvasId`圆形进度唯一标识 ID（若绘制多个环形进度条必须传递不同的 ID），通过`gradualStyle`参数设置圆形进度条样式，通过`canvasStyle`设置画板样式，通过`anticlockwise`设置环形进度条是否开启逆时针绘制

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="环形进度条">
       
      <ct-ui-line-progress
        ref="LineProgress"
        type="annular"
        :canvasId="1"
        :anticlockwise="false"
        :degree="degree"
        :gradualStyle="gradualStyle"
        :canvasStyle="canvasStyle"
      />
      <ct-ui-line-progress
        ref="LineProgress"
        type="annular"
        :canvasId="2"
        :anticlockwise="true"
        :degree="degree"
        :gradualStyle="gradualStyle"
        :canvasStyle="canvasStyle"
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'LineProgress',
  data() {
    return {
      degree: 80,
      gradualStyle: {
        width: '300rpx',
        height: '300rpx'
      },
      canvasStyle: {
        size: 50, // 环形大小
        lineWidth: 10, // 线条宽度
        notLineWidth: 6, // 未完成进度进度条宽度，默认比完成进度小4
        notLineColor: '#E7E7E7', // 未完成的进度条颜色
        completeLineColor: '#EB4B4B' // 已完成进度条颜色
      }
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [过渡效果](http://mid.chinatowercom.cn:18080/appGuide/ui/LineProgress.html#过渡效果)

通过`animation`参数设置过渡效果是否开启，通过`duration`参数设置过渡效果的所需时间，单位 ms

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="过渡效果">
      <ct-ui-line-progress
        ref="LineProgress"
        :degree="degree"
        :lineStyle="lineStyle"
        :completeStyle="completeStyle"
        :animation="animation"
        :duration="duration"
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'LineProgress',
  data() {
    return {
      degree: 48,
      lineStyle: {
        width: '400rpx',
        height: '60rpx',
        backgroundColor: '#E7E7E7FF',
        borderRadius: '30rpx',
        margin: '20rpx 20rpx'
      },
      completeStyle: {
        backgroundColor: '#EB4B4BFF'
      },
      animation: true,
      duration: 1500
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/LineProgress.html#事件监听)

`setDegree`事件可以监听进度发生变化，返回值发生变化的进度百分比数值

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="事件监听">
      <ct-ui-line-progress
        ref="LineProgress"
        :degree="degree"
        :lineStyle="lineStyle"
        :completeStyle="completeStyle"
        :animation="animation"
        :duration="duration"
        @setDegree="setDegree"
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'LineProgress',
  data() {
    return {
      degree: 48,
      lineStyle: {
        width: '400rpx',
        height: '60rpx',
        backgroundColor: '#E7E7E7FF',
        borderRadius: '30rpx',
        margin: '20rpx 20rpx'
      },
      completeStyle: {
        backgroundColor: '#EB4B4BFF'
      },
      animation: true,
      duration: 1500
    }
  },
  methods: {
    setDegree(degree) {
      console.log(degree)
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/LineProgress.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/LineProgress.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| type            | 选择的进度条样式             | String         | base                               | base（基础）\| gradual（渐变）\| annular（环形） |
| --------------- | ---------------------------- | -------------- | ---------------------------------- | ------------------------------------------------ |
| *degree（必传） | 完成程度                     | Number         | 0                                  | -                                                |
| lineStyle       | 线形进度条样式               | Object         | {}                                 | -                                                |
| completeStyle   | 已完成的进度条样式           | Object         | {}                                 | -                                                |
| gardenStyle     | 线形渐变进度条圆点样式       | Object         | {}                                 | -                                                |
| imgSrc          | 圆心图标                     | String         |                                    | -                                                |
| draggable       | 线型渐变进度条是否可以拖动   | Boolean        | false                              | true/false                                       |
| gradient        | 渐变色                       | Array          | []                                 | -                                                |
| canvasId        | 圆形进度唯一标识ID           | String, Number |                                    | -                                                |
| gradualStyle    | 圆形进度条样式               | Object         | {width: "300rpx",height: "300rpx"} | -                                                |
| fontStyle       | 字体样式                     | Object         | {}                                 | -                                                |
| canvasStyle     | 画板样式                     | Object         | {}                                 | -                                                |
| animation       | 是否开启过度效果             | Boolean        | true                               | true/false                                       |
| duration        | 过渡动画所需时间，单位ms     | Number         | 1000                               | -                                                |
| progressFlag    | 是否展示进度                 | Boolean        | true                               | true/false                                       |
| anticlockwise   | 环形进度条是否开启逆时针绘制 | Boolean        | false                              | true/false                                       |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/LineProgress.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| setDegree | 进度发生变化时触发 | 发生变化的进度百分比 |
| --------- | ------------------ | -------------------- |
|           |                    |                      |