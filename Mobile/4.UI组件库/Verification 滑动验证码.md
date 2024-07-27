# 

在需要对使用者身份进行检验的场景下可使用该组件。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/verification.html#基本使用)

- 通过`mode`参数设置滑动验证码展示模式，图片验证码`image`，滑块验证码`slider`
- 通过`bgImage`参数设置**mode=image**时的图片路径

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="滑块验证码">
      <ct-ui-verification mode="slider" />
    </ct-demo-card>
    <ct-demo-card title="图片验证码">
      <ct-ui-verification mode="image" :bgImage="src" />
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      src: '/static/images/ct_advertisement.jpeg'
    }
  }
}
</script>

<style lang="scss"></style>
```

### [设置大小](http://mid.chinatowercom.cn:18080/appGuide/ui/verification.html#设置大小)

- 通过`radius`参数设置滑动条及滑块圆角大小
- 通过`slideBarHeight`参数设置滑动条高度
- 通过`slideBlockWidth`参数设置滑块宽度
- 通过`slideSize`参数设置滑动图片大小
- 通过`imageSize`参数设置验证图片大小

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置大小">
      <ct-ui-verification
        mode="slider"
        radius="0"
        slideBlockWidth="60px"
        slideBarHeight="56px"
      />
      <ct-ui-verification
        mode="image"
        :bgImage="src"
        slideSize="80"
        imageSize="400"
      />
             
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      src: '/static/images/ct_advertisement.jpeg'
    }
  }
}
</script>

<style lang="scss"></style>
```

### [调整颜色](http://mid.chinatowercom.cn:18080/appGuide/ui/verification.html#调整颜色)

- 通过`bgColor`参数设置滑动条背景色
- 通过`color`参数设置滑动提示文字初始颜色
- 通过`activeBgColor`参数设置滑动过后，滑动条的滑过区域背景颜色
- 通过`failActiveBgColor`参数设置滑动失败过后，滑动条的滑过区域背景颜色
- 通过`successColor`参数设置滑动提示文字成功颜色
- 通过`failColor`参数设置滑动提示文字失败颜色

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="调整颜色">
      <ct-ui-verification
        mode="slider"
        bgColor="#393939"
        color="rgb(255, 255, 255)"
        activeBgColor="#3c9cff"
        failActiveBgColor="#ee0a24"
        failColor="#fff"
        successColor="#fff"
      />
             
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {}
  }
}
</script>

<style lang="scss"></style>
```

### [缺失图片位置](http://mid.chinatowercom.cn:18080/appGuide/ui/verification.html#缺失图片位置)

- 通过`rowSection`参数设置缺失图片横向区间，并在其中随机选取一个值
- 通过`columnSection`参数设置缺失图片纵向区间，并在其中随机选取一个值

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="缺失图片位置">
      <ct-ui-verification
        mode="image"
        :bgImage="src"
        :rowSection="[100, 200]"
        :columnSection="[10, 160]"
      />
             
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      src: '/static/images/ct_advertisement.jpeg'
    }
  }
}
</script>

<style lang="scss"></style>
```

### [调用功能](http://mid.chinatowercom.cn:18080/appGuide/ui/verification.html#调用功能)

- 通过`reset`参数设置是否开启重置刷新图片按钮
- 通过绑定`ref`进行手动调用组件上的功能

```vue
<template>
  <view class="demo-page">
    <ct-ui-button @click="change">刷新重置</ct-ui-button>
    <ct-demo-card title="调用功能">
      <ct-ui-verification
        mode="image"
        :reset="true"
        ref="verification"
        :bgImage="src"
      />
             
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      flag: true,
      src: '/static/images/ct_advertisement.jpeg'
    }
  },
  methods: {
    change() {
      this.flag = !this.flag
      this.src = this.flag
        ? '/static/images/ct_advertisement.jpeg'
        : 'https://cn.vuejs.org/images/logo.svg'
      this.$refs.verification.refresh()
    }
  }
}
</script>

<style lang="scss"></style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/verification.html#事件监听)

- `success`事件验证成功时触发
- `fail`事件验证失败时触发

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="事件监听">
      <ct-ui-verification
        mode="image"
        :bgImage="src"
        @success="success"
        @fail="fail"
      />
             
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      flag: true,
      src: '/static/images/ct_advertisement.jpeg'
    }
  },
  methods: {
    success() {
      console.log('success')
    },
    fail() {
      console.log('fail')
    }
  }
}
</script>

<style lang="scss"></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/verification.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/verification.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| mode              | 滑动验证码展示模式 图片验证码（image）\| 滑块验证码（slider） | String        | slider                                                       | slider \| image |
| ----------------- | ------------------------------------------------------------ | ------------- | ------------------------------------------------------------ | --------------- |
| bgImage           | mode=image，图片路径                                         | String        |                                                              | -               |
| imageSize         | 验证图片高度，单位px（mode=image）                           | String,Number | 240                                                          | —               |
| slideSize         | 滑动图片大小，单位px（mode=image）                           | String,Number | 50px                                                         | —               |
| reset             | 是否开启重置刷新图片按钮                                     | Boolean       | false                                                        | true/false      |
| errorRange        | 误差范围，单位px                                             | String,Number | 5                                                            | —               |
| rowSection        | 缺失图片横向区间                                             | Array         |                                                              | —               |
| columnSection     | 缺失图片纵向区间                                             | Array         |                                                              | —               |
| initText          | 初始化提示文字                                               | String        | 请按住滑块，向右拖动滑块填充拼图（mode=image），请按住滑块，拖动到最右侧（mode=slider） | —               |
| successText       | 滑动成功提示文字                                             | String        | 验证成功                                                     | —               |
| failText          | 滑动失败提示文字                                             | String        | 验证失败                                                     | —               |
| size              | 滑动提示文字大小                                             | String        |                                                              | —               |
| initText          | 初始化提示文字,，单位px                                      | String,Number | 14px                                                         | —               |
| color             | 滑动提示文字初始颜色                                         | String        | #191919                                                      | —               |
| successColor      | 滑动提示文字成功颜色                                         | String        | #ffffff                                                      | —               |
| failColor         | 滑动提示文字失败颜色                                         | String        | #ffffff                                                      | —               |
| slideBarHeight    | 滑动条高度，单位px                                           | String,Number | 40px                                                         | —               |
| slideBlockWidth   | 滑块宽度，单位px                                             | String,Number | 40px                                                         | —               |
| radius            | 滑动条及滑块圆角，单位px                                     | String,Number | 20px                                                         | —               |
| bgColor           | 滑动条背景色                                                 | String        | #E9E9E9                                                      | —               |
| activeBgColor     | 滑动过后，滑动条的滑过区域背景颜色                           | String        | #19be6b                                                      | —               |
| failActiveBgColor | 滑动失败过后，滑动条的滑过区域背景颜色                       | String        | #f56c6c                                                      | —               |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/verification.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| success | 验证成功时触发 | -    |
| ------- | -------------- | ---- |
| fail    | 验证失败时触发 | -    |

#### [Methods](http://mid.chinatowercom.cn:18080/appGuide/ui/verification.html#methods)

| 名称 | 说明 | 所需参数 |
| ---- | ---- | -------- |
|      |      |          |

| refresh | 刷新重置滑块/滑动图片出现位置 | -    |
| ------- | ----------------------------- | ---- |
|         |                               |      |

### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/verification.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

|      | 自定义滑块内容 | -    |
| ---- | -------------- | ---- |
|      |                |      |