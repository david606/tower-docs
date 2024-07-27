# [SignBoard 手写签名板](http://mid.chinatowercom.cn:18080/appGuide/ui/signBoard.html#signboard-手写签名板)

该组件主要用于签名时保存用户签名笔迹。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/signBoard.html#基本使用)

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-button shape="default" @click="show = true"
        >打开签名板</ct-ui-button
      >
    </ct-demo-card>
    <ct-ui-sign-board v-if="show"> </ct-ui-sign-board>
  </view>
</template>

<script>
export default {
  data() {
    return {
      show: false
    }
  },
  onLoad() {},
  onReady() {},
  methods: {}
}
</script>
```

### [设置显示样式](http://mid.chinatowercom.cn:18080/appGuide/ui/signBoard.html#设置显示样式)

- 通过`isFullScreen`参数设置签名板组件是否全屏显示
- 通过`cid`参数设置签名板组件中 canvas 的 id
- 通过`isShowBorder`参数设置 canvas 的边框是否显示
- 通过`width`参数设置 canvas 的宽度（在全屏显示时不生效）
- 通过`height`参数设置 canvas 的高度（在全屏显示时不生效）
- 通过`lineWidth`参数画笔的粗细（文字的粗细）
- 通过`lineColor`参数设置文字的颜色
- 通过`bgColor`参数设置签名板的组件颜色
- 通过`showGrid`参数设置签名板的网格是否显示（网格包括外边框，和`isShowBorder`属性样式有交集）
- 通过`borderWidth`参数设置网格的宽度
- 通过`borderColor`参数设置网格的颜色

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-button shape="default" @click="show = true"
        >打开签名板</ct-ui-button
      >
    </ct-demo-card>
    <ct-ui-sign-board
      :isFullScreen="false"
      cid="board-my"
      :isShowBorder="true"
      width="200px"
      height="200px"
      :lineWidth="6"
      lineColor="red"
      bgColor="#00ffe7"
      :showGrid="true"
      :borderWidth="2"
      borderColor="red"
      v-if="show"
    >
    </ct-ui-sign-board>
  </view>
</template>

<script>
export default {
  data() {
    return {
      show: false
    }
  },
  onLoad() {},
  onReady() {},
  methods: {}
}
</script>
```

### [设置选择器类型](http://mid.chinatowercom.cn:18080/appGuide/ui/signBoard.html#设置选择器类型)

- 通过`slot`插槽可以插入按钮
- 通过`ref`可以调用组件内部方法（具体方法说明可查看下方 api 具体参数）

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-button shape="default" @click="show = true"
        >打开签名板</ct-ui-button
      >
    </ct-demo-card>
    <ct-ui-sign-board
      ref="board"
      v-if="show"
      :isShowBorder="false"
      :showGrid="true"
    >
      <view slot="button" class="signBtn-box">
        <view class="signBtn-item1">
          <button
            type="default"
            plain="true"
            class="lnvestor-btn"
            hover-class="hover"
            @click="cancellation"
          >
            取消
          </button>
          <button
            type="default"
            plain="true"
            class="lnvestor-btn"
            hover-class="hover"
            @click="revoke"
          >
            撤销
          </button>
        </view>
        <view class="signBtn-item2">
          <view @click="clear">
            <button
              type="default"
              plain="true"
              class="lnvestor-btn1"
              hover-class="hover"
            >
              重写
            </button>
          </view>
          <view @click="submit">
            <button type="primary" class="lnvestor-btn2" hover-class="hover">
              提交签名
            </button>
          </view>
        </view>
      </view>
    </ct-ui-sign-board>
  </view>
</template>

<script>
export default {
  data() {
    return {
      show: false
    }
  },
  onLoad() {},
  onReady() {},
  methods: {
    cancellation() {
      this.show = false
    },
    clear() {
      this.$refs.board.clear()
    },
    revoke() {
      this.$refs.board.revoke()
    },
    submit() {
      this.$refs.board.saveImageToPhotosAlbum()
    }
  }
}
</script>

<style lang="scss" scoped>
.signBtn-box {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 30rpx;

  .signBtn-item1 {
    // 按钮样式
    .lnvestor-btn {
      width: 150rpx;
      height: 70rpx;
      border-radius: 40rpx;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 32rpx;
    }

    .hover {
      border: 2rpx solid #ccc !important;
      color: #ccc !important;
      font-size: 16rpx !important;
    }
  }

  .signBtn-item2 {
    display: flex;

    // 按钮样式
    .lnvestor-btn1 {
      width: 150rpx;
      height: 70rpx;
      border-radius: 40rpx;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 32rpx;
      margin-right: 20rpx;
    }

    .lnvestor-btn2 {
      width: 220rpx;
      height: 70rpx;
      border-radius: 40rpx;
      display: flex;
      justify-content: center;
      align-items: center;
      background: #b99c65;
      font-size: 32rpx;
    }

    .hover {
      border: 2rpx solid #ccc !important;
      color: #ccc !important;
      font-size: 32rpx !important;
    }
  }
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/signBoard.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/signBoard.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| isFullScreen | 组件是否全屏显示         | Boolean          | true                 | -    | 1.0.26+ |
| ------------ | ------------------------ | ---------------- | -------------------- | ---- | ------- |
| cid          | canvas id                | String           | v-sign-1721657254931 | —    | 1.0.26+ |
| isShowBorder | canvas 边框是否显示      | Boolean          | false                | —    | 1.0.26+ |
| width        | canvas 宽度              | String \| Number | 682upx               | —    | 1.0.26+ |
| height       | canvas 高度              | String \| Number | 500rpx               | —    | 1.0.26+ |
| lineWidth    | 画笔大小                 | String \| Number | 4                    | —    | 1.0.26+ |
| lineColor    | 文字颜色                 | String           | #333                 | —    | 1.0.26+ |
| bgColor      | 画布背景颜色             | string           | #ccc                 | —    | 1.0.26+ |
| showGrid     | 是否显示网格             | Boolean          | true                 | —    | 1.0.26+ |
| borderWidth  | 设置网格宽度             | String \| Number | 1                    | —    | 1.0.26+ |
| borderColor  | 设置网格颜色             | String           | #f00                 | —    | 1.0.26+ |
| customStyle  | 自定义canvas外的view样式 | Object           | {}                   | —    | 1.0.26+ |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/signBoard.html#events)

| 事件名 | 说明 | 返回值 | 调用方法 |
| ------ | ---- | ------ | -------- |
|        |      |        |          |

| getBase64Img           | 获取图片base64，             | 签名图片的base64地址 | this.$refs.xxx.getBase64Img()                                |
| ---------------------- | ---------------------------- | -------------------- | ------------------------------------------------------------ |
| saveImageToPhotosAlbum | 下载图片，h5暂不支持         | -                    | this.$refs.xxx.saveImageToPhotosAlbum(name)   name表示图片名称 |
| revoke                 | 撤销（撤销上一步的庇护）     | -                    | this.$refs.xxx.revoke()                                      |
| clear                  | 清空画布（可用于重写等操作） | -                    | this.$refs.xxx.clear()                                       |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/signBoard.html#slots)

| name | 说明 | 作用域 | 版本 |
| ---- | ---- | ------ | ---- |
|      |      |        |      |

| button | 自定义的内容 | -    | 1.0.26+ |
| ------ | ------------ | ---- | ------- |
|        |              |      |         |