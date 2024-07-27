# [overlay 遮罩层](http://mid.chinatowercom.cn:18080/appGuide/ui/overlay.html#overlay-遮罩层)

创建一个遮罩层，通常用于阻止用户进行其他操作。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/overlay.html#基本使用)

- 通过`show`参数设置遮罩层是否显示，默认 false
- 通过`zIndex`参数设置遮罩层层级，默认 999
- 通过`duration`参数设置遮罩层的过度时间，默认 0.3，单位 s
- 通过`closeOnClickOverLay`参数设置是否可以通过点击遮罩进行关闭，默认 true
- 通过`lockScroll`参数设置是否锁定遮罩层不能滚动，默认 true
- 通过`className`参数设置自定义遮罩层样式名称
- 通过`customStyle`参数设置用户自定义样式

```vue
<template>
  <view class="maskPage">
    <ct-demo-card title="基础使用">
      <ct-ui-button btnSize="middle" @click="showMaskLayer"
        >显示遮罩层
      </ct-ui-button>
      <ct-ui-overlay
        :show="show"
        @close="show = false"
        duration="1"
        :lockScroll="false"
        :closeOnClickOverLay="true"
        :customStyle="customStyle"
        className="wrap"
      />
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      show: false,
      customStyle: {
        background: 'rgba(235, 75, 75, 0.6)'
      }
    }
  },
  methods: {
    // 基础遮罩层事件
    showMaskLayer(e) {
      this.show = true
    }
  }
}
</script>

<style lang="scss">
.maskPage {
  padding: 12px;
  /deep/ .wrap {
    margin-left: 30px;
  }
}
</style>
```

### [嵌入内容](http://mid.chinatowercom.cn:18080/appGuide/ui/overlay.html#嵌入内容)

- 通过`show`参数设置遮罩层是否显示，默认 false
- 通过`zIndex`参数设置遮罩层层级，默认 999
- 通过`duration`参数设置遮罩层的过度时间，默认 0.3，单位 s
- 通过`closeOnClickOverLay`参数设置是否可以通过点击遮罩进行关闭，默认 true
- 通过`lockScroll`参数设置是否锁定遮罩层不能滚动，默认 true
- 通过`className`参数设置自定义遮罩层样式名称
- 通过`customStyle`参数设置用户自定义样式

```vue
<template>
  <view class="maskPage">
    <ct-demo-card title="嵌入内容">
      <ct-ui-button btnSize="middle" @click="embeddedContent"
        >嵌入内容</ct-ui-button
      >
      <ct-ui-overlay :show="showCont" @close="showCont = false">
        <view class="embed">
          <view class="embeddedContent" @tap.stop>嵌入内容</view>
        </view>
      </ct-ui-overlay>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      showCont: false
    }
  },
  methods: {
    // 嵌入内容遮罩层事件
    embeddedContent() {
      this.showCont = true
    }
  }
}
</script>

<style lang="scss">
.maskPage {
  padding: 12px;
  .embed {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    .embeddedContent {
      width: 150px;
      height: 150px;
      background-color: #fff;
      text-align: center;
      line-height: 150px;
      border-radius: 10px;
    }
  }
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/overlay.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/overlay.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| show                | 是否显示遮罩                 | Boolean          | false | true \| false | v1.0.18+ |
| ------------------- | ---------------------------- | ---------------- | ----- | ------------- | -------- |
| zIndex              | 遮罩层层级设置               | String \| Number | 999   | -             | v1.0.18+ |
| duration            | 遮罩的过渡时间               | String \| Number | 0.3   | -             | v1.0.18+ |
| closeOnClickOverLay | 是否可以通过点击遮罩进行关闭 | Boolean          | true  | true \| false | v1.0.18+ |
| lockScroll          | 是否锁定遮罩层不能滚动       | Boolean          | true  | true \| false | v1.0.18+ |
| className           | 自定义遮罩层样式名称         | String           | -     | -             | v1.0.18+ |
| customStyle         | 用户自定义样式               | Object           | -     | -             | v1.0.18+ |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/overlay.html#events)

| 事件名 | 说明 | 返回值 | 版本 |
| ------ | ---- | ------ | ---- |
|        |      |        |      |

| close | 遮罩层点击事件 | -    | v1.0.18+ |
| ----- | -------------- | ---- | -------- |
|       |                |      |          |