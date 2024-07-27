# [rotation 轮播图](http://mid.chinatowercom.cn:18080/appGuide/ui/rotation.html#rotation-轮播图)

该组件主要用于进行轮播展示视频、图片。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/rotation.html#基本使用)

- 通过`list`参数传入展示的轮播对象，默认为`[]`
- 通过`interval`参数设置自动切换时间间隔，单位为`ms`
- 通过`autoplay`参数设置是否自动播放轮播
- 通过`color`参数设置指示点颜色
- 通过`activeColor`参数设置当前选中的指示点颜色

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-rotation
        :list="list"
        width="100%"
        ref="rotation"
        :autoplay="true"
        :interval="6000"
        color="#000"
        activeColor="#fff"
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'rotation',
  data() {
    return {
      list: [
        {
          id: 222,
          isPlay: false, // 是否可播放
          src: '' // 图片地址
        },
        {
          id: 333,
          isPlay: true, // 是否可播放
          src: '', // 视频展示图地址
          vide: '' // 视频地址
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [轮播方式](http://mid.chinatowercom.cn:18080/appGuide/ui/rotation.html#轮播方式)

通过`indicatorDots`设置是否显示面板指示点，通过`circular`设置是否采用衔接滑动，即播放到末尾后重新回到开头，通过`vertical`设置滑动方向是否为纵向，

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="轮播方式">
      <ct-ui-rotation
        :list="list"
        ref="rotation"
        width="100%"
        :indicatorDots="true"
        :circular="true"
        :vertical="true"
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'rotation',
  data() {
    return {
      list: [
        {
          id: 222,
          isPlay: false, // 是否可播放
          src: '' // 图片地址
        },
        {
          id: 333,
          isPlay: true, // 是否可播放
          src: '', // 视频展示图地址
          vide: '' // 视频地址
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [样式设置](http://mid.chinatowercom.cn:18080/appGuide/ui/rotation.html#样式设置)

`width`属性设置轮播图宽度，`height`属性设置轮播图高度，`previousMargin`设置轮播的前边距，可用于露出前一项的一小部分(接受 px 和 rpx 值)，`nextMargin`设置轮播的后边距，可用于露出后一项的一小部分(接受 px 和 rpx 值)

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="样式设置">
      <ct-ui-rotation
        :list="list"
        ref="rotation"
        width="100%"
        height="650rpx"
        previousMargin="60rpx"
        nextMargin="60rpx"
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'rotation',
  data() {
    return {
      list: [
        {
          id: 222,
          isPlay: false, // 是否可播放
          src: '' // 图片地址
        },
        {
          id: 333,
          isPlay: true, // 是否可播放
          src: '', // 视频展示图地址
          vide: '' // 视频地址
        },
        {
          id: 444,
          isPlay: false, // 是否可播放
          src: '' // 图片地址
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/rotation.html#事件监听)

`change`事件监听手动滑动，`click`事件监听当前点击的轮播内容，`playVideo`事件可以监听点击播放视频按钮，`refresh`事件可以监听视频或图片加载失败时点击的刷新按钮，

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="事件监听">
      <ct-ui-rotation
        :list="list"
        width="100%"
        @change="change"
        @click="click"
        @playVideo="playVideo"
        @refresh="refresh"
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'rotation',
  data() {
    return {
      list: [
        {
          id: 222,
          isPlay: false, // 是否可播放
          src: '' // 图片地址
        },
        {
          id: 333,
          isPlay: true, // 是否可播放
          src: '', // 视频展示图地址
          vide: '' // 视频地址
        }
      ]
    }
  },
  methods: {
    change(item) {
      console.log(item)
    },
    click(item) {
      console.log(item)
    },
    playVideo(item) {
      console.log(item)
    },
    refresh(item) {
      console.log(item)
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [加载时间设置](http://mid.chinatowercom.cn:18080/appGuide/ui/rotation.html#加载时间设置)

通过`imgloading`设置图片的加载过慢提示时间，单位为`ms`，通过`videoloading`设置视频的加载过慢提示时间，当超过加载时间还未加载出来时出现提示，单位为 ms`

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="加载时间设置">
      <ct-ui-rotation
        :list="list"
        width="100%"
        ref="rotation"
        :videoloading="7000"
        :imgloading="7000"
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'rotation',
  data() {
    return {
      list: [
        {
          id: 222,
          isPlay: false, // 是否可播放
          src: '' // 图片地址
        },
        {
          id: 333,
          isPlay: true, // 是否可播放
          src: '', // 视频展示图地址
          vide: '' // 视频地址
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/rotation.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/rotation.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| *(必填)list    | 需要轮播的数组                               | Array   | []        | -          |
| -------------- | -------------------------------------------- | ------- | --------- | ---------- |
| autoplay       | 是否自动播放轮播                             | Boolean | true      | true/false |
| interval       | 自动切换时间间隔,单位ms                      | Number  | 1000      | -          |
| duration       | 滑动动画时长,单位ms                          | Number  | 1000      | -          |
| indicatorDots  | 是否显示面板指示点                           | Boolean | true      | true/false |
| circular       | 是否采用衔接滑动，即播放到末尾后重新回到开头 | Boolean | true      | true/false |
| vertical       | 滑动方向是否为纵向                           | Boolean | false     | true/false |
| width          | 轮播图宽度                                   | String  | 750rpx    | -          |
| height         | 轮播图高度                                   | String  | 650rpx    | -          |
| color          | 指示点颜色                                   | String  | #FFFFFF8C | -          |
| activeColor    | 当前选中的指示点颜色                         | String  | #FFF      | -          |
| previousMargin | 前边距                                       | String  | 0px       | -          |
| nextMargin     | 后边距                                       | String  | 0px       | -          |
| imgloading     | 图片的加载过慢提示时间                       | Number  | 6000      | -          |
| videoloading   | 视频的加载过慢提示时间                       | Number  | 6000      | -          |
| muted          | 是否静音播放                                 | Boolean | false     | true/false |
| popup          | 是否来自弹窗                                 | Boolean | false     | true/false |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/rotation.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| change（currentChange已取消） | 手动滑动时触发         | -              |
| ----------------------------- | ---------------------- | -------------- |
| click                         | 滑块点击时触发         | 点击的轮播对象 |
| playVideo                     | 点击播放视频按钮时触发 | 点击的视频对象 |
| refresh                       | 点击刷新按钮时触发     | 点击的刷新对象 |

#### [Methods](http://mid.chinatowercom.cn:18080/appGuide/ui/rotation.html#methods)

| 名称 | 说明 | 需要参数 |
| ---- | ---- | -------- |
|      |      |          |

| picture | 查看图片     | 点击的图片对象 |
| ------- | ------------ | -------------- |
| suspend | 暂停视频播放 | 暂停的视频对象 |