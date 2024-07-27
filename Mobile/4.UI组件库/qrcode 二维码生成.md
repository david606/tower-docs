# [qrcode 二维码生成](http://mid.chinatowercom.cn:18080/appGuide/ui/qrcode.html#qrcode-二维码生成)

该组件通常用于生成二维码。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/qrcode.html#基本使用)

- 通过`modal`参数设置是否显示二维码
- 通过`url`参数设置要生成的二维码值
- 通过`height`参数设置二维码的高度
- 通过`width`参数设置二维码的宽度
- 通过`themeColor`参数设置二维码的颜色
- 通过`qrcode_id`参数设置画布 id
- 通过`is_themeImg`参数设置是否显示展示中间 logo
- 通过`themeImg`参数设置 logo 的路径，可以是网络路径，还可以是本地路径
- 通过`h_w_img`参数设置图片的大小

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-qrcode
        ref="qrcode"
        qrcode_id="qrcode"
        :modal="modal_qr"
        :url="url"
        @hideQrcode="hideQrcode"
      />
    </ct-demo-card>
    <ct-demo-card title="调整大小">
      <ct-ui-qrcode
        ref="qrcode"
        :width="300"
        :height="300"
        qrcode_id="qrcode"
        :modal="modal_qr"
        :url="url"
        @hideQrcode="hideQrcode"
      />
    </ct-demo-card>
    <ct-demo-card title="修改颜色">
      <ct-ui-qrcode
        ref="qrcode2"
        qrcode_id="qrcode2"
        :modal="modal_qr"
        :url="url"
        @hideQrcode="hideQrcode"
        themeColor="#33CCCC"
      />
    </ct-demo-card>
    <ct-demo-card title="添加logo">
      <ct-ui-qrcode
        ref="qrcode4"
        qrcode_id="qrcode4"
        :modal="modal_qr"
        :url="url"
        @hideQrcode="hideQrcode"
        themeColor="#ddd890"
        :is_themeImg="true"
        themeImg="https://cdn.pixabay.com/photo/2016/11/29/13/24/balloons-1869816__340.jpg"
        :h_w_img="50"
      />
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      //二维码相关参数
      modal_qr: false,
      url: 'https://pixabay.com/images/search/?order=ec' // 要生成的二维码值
    }
  },
  onLoad() {
    let that = this
    that.showQrcode() //一加载生成二维码
  },
  methods: {
    // 展示二维码
    showQrcode() {
      let _this = this
      this.modal_qr = true
      setTimeout(function () {
        _this.$refs.qrcode.crtQrCode()
        _this.$refs.qrcode2.crtQrCode()
        _this.$refs.qrcode4.crtQrCode()
      }, 100)
    },
    //传入组件的方法
    hideQrcode() {
      this.modal_qr = false
    }
  }
}
</script>
<style lang="scss"></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/qrcode.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/qrcode.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| modal       | 是否显示                                     | boolean | false     | true/false |
| ----------- | -------------------------------------------- | ------- | --------- | ---------- |
| url         | 要生成的二维码值                             | string  | —         | —          |
| height      | 二维码的高度                                 | Number  | 260       | —          |
| width       | 二维码的宽度                                 | Number  | 260       | —          |
| themeColor  | 二维码的颜色                                 | string  | #333333   | —          |
| qrcode_id   | 画布id                                       | string  | qrcode_id | —          |
| is_themeImg | 是否显示展示中间logo                         | boolean | false     | —          |
| themeImg    | 图片的路径，可以是网络路径，还可以是本地路径 | string  | —         | —          |
| h_w_img     | 图片的大小                                   | Number  | 30        | —          |