# [Image 图片](http://mid.chinatowercom.cn:18080/appGuide/ui/image.html#image-图片)

该组件主要对图片进行封装，对图片的加载有更好的展示效果。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/image.html#基本使用)

- 通过`image`参数传入需要展示的图片，支持静态图、gif 图
- 通过`defaultImage`参数传入默认占位图

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-image
        ref="image"
        :image="image"
        :defaultImage="defaultImage"
      ></ct-ui-image>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'image',
  data() {
    return {
      image: {
        src: '/static/images/ct_advertisement.jpeg',
        class: 'ct_image',
        style: {
          width: '100%',
          height: '700rpx',
          borderRadius: '60rpx'
        },
        mode: 'scaleToFill',
        lazyLoad: true
      },
      defaultImage: ''
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [展示进度和 loading 图片](http://mid.chinatowercom.cn:18080/appGuide/ui/image.html#展示进度和-loading-图片)

通过`loading`参数和`processShow`参数设置是否显示 loading 图片以及是否显示进度，通过`loadingImage`设置 loading 图片

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="展示进度和loading图片">
      <ct-ui-image
        ref="image"
        :image="image"
        :defaultImage="defaultImage"
        :loading="loading"
        :processShow="processShow"
        :loadingImage="loadingImage"
      ></ct-ui-image>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'image',
  data() {
    return {
      image: {
        src: '/static/images/ct_advertisement.jpeg',
        class: 'ct_image',
        style: {
          width: '100%',
          height: '700rpx',
          borderRadius: '60rpx'
        },
        mode: 'scaleToFill',
        lazyLoad: true
      },
      loading: true,
      processShow: true,
      defaultImage: '/static/images/ct_loading.png',
      loadingImage: {}
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/image.html#事件监听)

`imageFail`事件可以监听图片加载失败，`imageSuccess`事件可以监听图片加载完成

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="事件监听">
      <ct-ui-image
        ref="image"
        :image="image"
        :defaultImage="defaultImage"
        @imageFail="imageFail"
        @imageSuccess="imageSuccess"
      ></ct-ui-image>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'image',
  data() {
    return {
      image: {
        src: '/static/images/ct_advertisement.jpeg',
        class: 'ct_image',
        style: {
          width: '100%',
          height: '750rpx',
          borderRadius: '60rpx'
        },
        mode: 'scaleToFill',
        lazyLoad: true
      },
      defaultImage: ''
    }
  },
  methods: {
    imageFail(e) {
      console.log(e)
    },
    imageSuccess(e) {
      console.log(e)
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/image.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/image.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| image        | 需要展示的图片                                          | Object  | {}    | src：图片路径，class：类名，mode：图片的裁剪缩放模式，lazyLoad：是否开启懒加载，style: 图片样式 |
| ------------ | ------------------------------------------------------- | ------- | ----- | ------------------------------------------------------------ |
| defaultImage | 默认占位图                                              | String  |       | -                                                            |
| errorImage   | 加载失败占位图                                          | String  |       | -                                                            |
| loadingImage | loading图片                                             | Object  | {}    | 同image参数                                                  |
| processShow  | 是否显示进度（注：app端使用本地路径时无法显示加载进度） | Boolean | false | true\|false                                                  |
| loading      | 是否显示loading图片                                     | Boolean | false | true\|false                                                  |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/image.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| imageFail    | 图片加载失败时触发 | -    |
| ------------ | ------------------ | ---- |
| imageSuccess | 图片加载完成时触发 | -    |