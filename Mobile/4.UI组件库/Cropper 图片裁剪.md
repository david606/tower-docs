# [Cropper 图片裁剪](http://mid.chinatowercom.cn:18080/appGuide/ui/cropper.html#cropper-图片裁剪)

该组件主要是对用户所选图片进行裁剪生成想要的图片大小格式。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/cropper.html#基本使用)

- 通过绑定`ref`进行手动调用组件上的功能

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
            <ct-ui-cropper ref="cropper" />
      <ct-ui-button class="button" @click="open">打开</ct-ui-button>
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'cropper',
  data() {
    return {}
  },
  methods: {
    open() {
      this.$refs.cropper.open()
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [圆形裁剪](http://mid.chinatowercom.cn:18080/appGuide/ui/cropper.html#圆形裁剪)

- 通过`round`参数设置是否使用圆形裁剪

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="圆形裁剪">
            <ct-ui-cropper ref="cropper" round />
      <ct-ui-button class="button" @click="open">打开</ct-ui-button>
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'cropper',
  data() {
    return {}
  },
  methods: {
    open() {
      this.$refs.cropper.open()
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [高斯模糊](http://mid.chinatowercom.cn:18080/appGuide/ui/cropper.html#高斯模糊)

- 通过`filterBlur`参数设置是否启用高斯模糊

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="高斯模糊">
            <ct-ui-cropper ref="cropper" round filterBlur />
      <ct-ui-button class="button" @click="open">打开</ct-ui-button>
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'cropper',
  data() {
    return {}
  },
  methods: {
    open() {
      this.$refs.cropper.open()
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [自定义样式](http://mid.chinatowercom.cn:18080/appGuide/ui/cropper.html#自定义样式)

- 通过`cropHeight`参数设置裁剪高度
- 通过`cropWidth`参数设置裁剪宽度
- 通过`backgroundColor`参数设置底色

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义样式">
         
      <ct-ui-cropper
        ref="cropper"
        :cropHeight="200"
        :cropWidth="300"
        backgroundColor="#FFF"
      />
      <ct-ui-button class="button" @click="open">打开</ct-ui-button>
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'cropper',
  data() {
    return {}
  },
  methods: {
    open() {
      this.$refs.cropper.open()
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [调用功能](http://mid.chinatowercom.cn:18080/appGuide/ui/cropper.html#调用功能)

- 通过绑定`ref`进行手动调用组件上的功能

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="调用功能">
            <ct-ui-cropper ref="cropper" />
      <ct-ui-button class="button" @click="open">打开</ct-ui-button>
      <ct-ui-button class="button" @click="close">关闭</ct-ui-button>
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'cropper',
  data() {
    return {}
  },
  methods: {
    open() {
      this.$refs.cropper.open()
    },
    close() {
      this.$refs.cropper.close()
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/cropper.html#事件监听)

`success`事件可以监听图片裁剪成功时触发，`fail`事件可以监听图片裁剪失败时触发

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="调用功能">
          <ct-ui-cropper ref="cropper" @success="success" @fail="fail" />
      <ct-ui-button class="button" @click="open">打开</ct-ui-button>
      <ct-ui-button class="button" @click="close">关闭</ct-ui-button>
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'cropper',
  data() {
    return {}
  },
  methods: {
    open() {
      this.$refs.cropper.open()
    },
    close() {
      this.$refs.cropper.close()
    },
    success(e) {
      console.log(e)
    },
    fail(e) {
      console.log(e)
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/cropper.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/cropper.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| url             | 图片路径         | String  |       | -          |
| --------------- | ---------------- | ------- | ----- | ---------- |
| imageWidth      | 图片宽度         | Number  | 320   | -          |
| cropHeight      | 裁剪高度         | Number  | 200   | -          |
| cropWidth       | 裁剪宽度         | Number  | 200   | -          |
| backgroundColor | 底色             | String  |       | -          |
| round           | 是否圆形         | Boolean | false | true/false |
| filterBlur      | 是否启用高斯模糊 | Boolean | false | true/false |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/cropper.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| success | 裁剪成功时触发 | 图片     |
| ------- | -------------- | -------- |
| fail    | 裁剪失败时触发 | 失败原因 |

#### [Methods](http://mid.chinatowercom.cn:18080/appGuide/ui/cropper.html#methods)

| 名称 | 说明 | 所需参数 |
| ---- | ---- | -------- |
|      |      |          |

| open  | 打开图片裁剪组件 |      |
| ----- | ---------------- | ---- |
| close | 关闭图片裁剪组件 |      |