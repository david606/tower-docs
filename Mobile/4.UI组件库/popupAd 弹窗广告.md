# [popupAd 弹窗广告](http://mid.chinatowercom.cn:18080/appGuide/ui/popupAd.html#popupad-弹窗广告)

该组件主要用于加载应用时出现的广告弹窗，用户可以通过传入图片或自定义内容展示广告内容。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/popupAd.html#基本使用)

- 通过`amount`参数定义设置广告数量
- 通过`list`参数传入的广告内容，默认为`[]`

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-popup-ad ref="popupAd" :list="list" />
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'popupAd',
  data() {
    return {
      list: [
        {
          id: 1,
          src: '/static/images/ct_advertisement.jpeg'
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [自定义样式](http://mid.chinatowercom.cn:18080/appGuide/ui/popupAd.html#自定义样式)

通过`maskStyle`参数设置遮罩层样式，通过`width`以及`height`参数设置广告内容宽高，通过`closeFlag`参数设置是否显示底部关闭按钮 ，通过`activeColor`设置当前广告的指示点颜色，通过`color`参数设置指示点颜色

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义样式">
      <ct-ui-popup-ad
        ref="popupAd"
        :list="list"
        :maskStyle="maskStyle"
        :width="width"
        :height="height"
        :closeFlag="closeFlag"
        color="#FFFFFF8C"
        activeColor="#FFFFFF"
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'popupAd',
  data() {
    return {
      list: [{id: 1, src: '/static/images/ct_advertisement.jpeg'}],
      maskStyle: {
        backgroundColor: '#EB4B4B'
      },
      width: '600rpx',
      height: '800rpx',
      closeFlag: false
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [设置随机广告](http://mid.chinatowercom.cn:18080/appGuide/ui/popupAd.html#设置随机广告)

通过`random`是否设定为随机广告，**true**为打开，通过`amount`设置展示的广告数量，若没有则默认全部展示

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置随机广告">
      <ct-ui-popup-ad
        ref="popupAd"
        :list="list"
        :amount="amount"
        :random="false"
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'popupAd',
  data() {
    return {
      list: [
        {id: 1, src: '/static/images/ct_advertisement.jpeg'},
        {id: 2, src: '/static/images/ct_advertisement.jpeg'},
        {id: 3, src: '/static/images/ct_advertisement.jpeg'}
      ],
      amount: 2
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [自动关闭](http://mid.chinatowercom.cn:18080/appGuide/ui/popupAd.html#自动关闭)

通过`autoOff`参数设置广告是否自动关闭，通过`closeTime`参数设置广告自动关闭所需时间，通过`closeFlag`参数设置是否显示底部关闭按钮

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自动关闭">
      <ct-ui-popup-ad
        ref="popupAd"
        :list="list"
        :autoOff="true"
        :closeTime="6000"
        :rotation="2000"
        :closeFlag="false"
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'popupAd',
  data() {
    return {
      list: [{id: 1, src: '/static/images/ct_advertisement.jpeg'}]
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [手动控制打开关闭](http://mid.chinatowercom.cn:18080/appGuide/ui/popupAd.html#手动控制打开关闭)

通过绑定`ref`进行手动控制 **打开、关闭**

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="手动控制打开关闭">
        <ct-ui-popup-ad ref="popupAd" :list="list" />
      <ct-ui-button style="marginTop: 20rpx;" @click="open">打开</ct-ui-button>
      <ct-ui-button style="marginTop: 20rpx;" @click="close">关闭</ct-ui-button>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'popupAd',
  data() {
    return {
      list: [{id: 1, src: '/static/images/ct_advertisement.jpeg'}]
    }
  },
  methods: {
    open() {
      this.$refs.popupAd.open() // 打开弹窗广告
    },
    close() {
      this.$refs.popupAd.close() // 关闭弹窗广告
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/popupAd.html#事件监听)

`close`事件可以监听关闭广告，`refresh`事件可以监听广告加载失败点击的刷新按钮，`click`事件可以监听广告内容的点击

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="事件监听">
      <ct-ui-popup-ad
        ref="popupAd"
        :list="list"
        @close="close"
        @refresh="refresh"
        @click="click"
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'popupAd',
  data() {
    return {
      list: [{id: 1, src: '/static/images/ct_advertisement.jpeg'}]
    }
  },
  methods: {
    close() {
      console.log('close')
    },
    refresh(item) {
      console.log(item)
    },
    click(item) {
      console.log(item)
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [使用插槽](http://mid.chinatowercom.cn:18080/appGuide/ui/popupAd.html#使用插槽)

通过设置插槽内容自行进行使用

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="使用插槽">
       
      <ct-ui-popup-ad ref="popupAd" :list="list">
        <template v-slot:content>
          <view class="slotContent">
            <text>自定义弹窗广告</text>
          </view>
        </template>
      </ct-ui-popup-ad>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'popupAd',
  data() {
    return {
      list: [{id: 1, src: '/static/images/ct_advertisement.jpeg'}]
    }
  }
}
</script>

<style scoped lang="scss">
.slotContent {
  width: 100%;
  height: 700rpx;
  margin: 0;
  border-radius: 12rpx;
  overflow: hidden;
  background-color: #eb4b4b;
  text-align: center;
  text {
    display: inline-block;
    padding-top: 100rpx;
    color: #ffffff;
  }
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/popupAd.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/popupAd.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| list         | 传入的广告内容              | Array   | []        | -          |
| ------------ | --------------------------- | ------- | --------- | ---------- |
| amount       | 设置广告数量                | Number  | 0         | -          |
| random       | 是否设定为随机广告          | Boolean | false     | true/false |
| rotation     | 广告几秒轮换一次,单位ms     | Number  | 4000      | -          |
| autoOff      | 广告是否自动关闭            | Boolean | false     | true/false |
| closeTime    | 广告自动关闭所需时间,单位ms | Number  | 4000      | -          |
| closePicture | 关闭图标                    | String  | -         | -          |
| closeFlag    | 是否显示底部关闭按钮        | Boolean | true      | true/false |
| width        | 广告内容宽度                | String  | 600rpx    | -          |
| height       | 广告内容高度                | String  | 700rpx    | -          |
| color        | 指示点颜色                  | String  | #FFFFFF8C | -          |
| activeColor  | 当前选中的指示点颜色        | String  | #FFF      | -          |
| frequency    | 是否只弹出一次或多次        | Number  | 1         | -          |
| autoOpen     | 是否自动打开或用户控制打开  | Boolean | true      | true/false |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/popupAd.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| close   | 点击关闭广告按钮或广告自动关闭时触发 | -              |
| ------- | ------------------------------------ | -------------- |
| click   | 广告内容点击时触发                   | 点击的广告对象 |
| refresh | 广告加载失败点击刷新按钮             | 点击的广告对象 |

#### [Methods](http://mid.chinatowercom.cn:18080/appGuide/ui/popupAd.html#methods)

| 名称 | 说明 |
| ---- | ---- |
|      |      |

| open  | 打开弹窗广告 |
| ----- | ------------ |
| close | 关闭广告事件 |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/popupAd.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

| content | 自定义弹窗广告内容 | -    |
| ------- | ------------------ | ---- |
|         |                    |      |