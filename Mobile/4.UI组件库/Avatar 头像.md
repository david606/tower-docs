# [Avatar 头像](http://mid.chinatowercom.cn:18080/appGuide/ui/avatar.html#avatar-头像)

该组件一般用于头像显示，有 img、文字、icon 三种形式。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/avatar.html#基本使用)

```vue
<template>
  <view class="avatar-page">
    <ct-demo-card title="基本使用">
      <ct-ui-avatar @click="avatarClick" />
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {}
  },
  methods: {
    avatarClick() {
      console.log('点击事件')
    }
  }
}
</script>

<style lang="scss">
.avatar-page {
  padding: 12px;
}
</style>
```

### [头像类型](http://mid.chinatowercom.cn:18080/appGuide/ui/avatar.html#头像类型)

- 通过`shape`参数设置头像形状，分别是`square`(方形)、`circle`(默认圆形)
- 通过`round`参数设置方形时的圆角大小，默认单位 rpx
- 通过`shadow`参数设置阴影，有 5 个值，依次是：水平阴影的位置、垂直阴影的位置、模糊距离、阴影的尺寸、阴影的颜色

```vue
<template>
  <view class="avatar-page">
    <ct-demo-card title="头像类型">
      <view class="" style="display: flex;">
        <ct-ui-avatar
          :src="img"
          style="margin-right: 20px;"
          shape="square"
          round="20rpx"
          shadow="5px 5px 5px"
          size="75px"
        />
        <ct-ui-avatar :src="img" shape="circle" round="20rpx" size="75px" />
      </view>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      img: require('@/static/images/ct_logo.png')
    }
  }
}
</script>

<style lang="scss">
.avatar-page {
  padding: 12px;
}
</style>
```

### [头像边框设置](http://mid.chinatowercom.cn:18080/appGuide/ui/avatar.html#头像边框设置)

- 通过`border`参数设置头像边框，值`true`为有边框，`false`为无边框
- 通过`borderColor`参数设置边框颜色

```vue
<template>
  <view class="avatar-page">
    <ct-demo-card title="头像边框设置">
      <view class="" style="display: flex;flex-wrap: wrap;">
        <ct-ui-avatar
          :src="img"
          :border="true"
          style="margin-right: 20px;"
          shape="circle"
          size="75px"
        />
        <ct-ui-avatar
          :src="img"
          :border="false"
          style="margin-right: 20px;"
          shape="square"
          size="75px"
        />
        <ct-ui-avatar
          :src="img"
          :border="true"
          shape="square"
          round="20rpx"
          size="75px"
          borderColor="#eb4b4b"
        />
      </view>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      img: require('@/static/images/ct_logo.png')
    }
  }
}
</script>

<style lang="scss">
.avatar-page {
  padding: 12px;
}
</style>
```

### [头像大小](http://mid.chinatowercom.cn:18080/appGuide/ui/avatar.html#头像大小)

- 通过`size`参数设置头像大小，值`large`、`default`、`samll`及自定义值，默认单位 rpx

```vue
<template>
  <ct-demo-card title="头像大小">
    <view class="" style="display: flex;flex-wrap: wrap;">
      <ct-ui-avatar
        :src="img"
        :border="true"
        style="margin-right: 20px;"
        round="20rpx"
        size="large"
      />
      <ct-ui-avatar
        :src="img"
        :border="true"
        style="margin-right: 20px;"
        round="20rpx"
        size="default"
      />
      <ct-ui-avatar :src="img" :border="true" round="20rpx" size="samll" />
    </view>
  </ct-demo-card>
</template>

<script>
export default {
  data() {
    return {
      img: require('@/static/images/ct_logo.png')
    }
  }
}
</script>

<style lang="scss">
.avatar-page {
  padding: 12px;
}
</style>
```

### [图像/文字/icon 头像](http://mid.chinatowercom.cn:18080/appGuide/ui/avatar.html#图像-文字-icon-头像)

- 头像优先级`label`、`src`、`iconName`
- 通过`src`参数设置图片头像
- 通过`label`参数设置文字头像
- 通过`iconName`参数设置 icon 头像
- 通过`bgColor`参数设置头像背景色
- 通过`iconSize`参数设置 icon 头像大小，默认单位 rpx
- 通过`iconColor`参数设置 icon 头像颜色
- 通过`labelSize`参数设置文字头像里文字大小，默认单位 rpx
- 通过`labelColor`参数设置文字头像里文字颜色
- 通过`defaultAvatar`参数设置图片头像下的默认图片
- 通过`modes`参数设置图片缩放比例，值：'scaleToFill'、'aspectFit'、'aspectFill'、'widthFix'、'heightFix'、'top'、'bottom'、'center'、'left'、'right'、'top left'、'top right'、'bottom left'、'bottom right'

```vue
<template>
  <ct-demo-card title="图片/文字/icon头像">
    <view class="" style="display: flex;flex-wrap: wrap;">
      <ct-ui-avatar
        :src="img"
        :border="true"
        style="margin-right: 20px;"
        round="20rpx"
        size="large"
        :defaultAvatar="defaultAvatar"
      />
      <ct-ui-avatar
        :src="img"
        :border="true"
        style="margin-right: 20px;"
        round="20rpx"
        size="large"
        bgColor="#e5e5e5"
        label="文字"
        labelSize="16px"
        labelColor="#eb4b4b"
      />
      <ct-ui-avatar
        :border="true"
        round="20rpx"
        size="large"
        iconName="home"
        iconSize="30px"
        iconColor="#eb4b4b"
      />
    </view>
  </ct-demo-card>
</template>

<script>
export default {
  data() {
    return {
      img: require('@/static/images/ct_logo.png'),
      defaultAvatar: require('@/static/images/ct-welcomepage.jpg')
    }
  }
}
</script>

<style lang="scss">
.avatar-page {
  padding: 12px;
}
</style>
```

### [头像角标](http://mid.chinatowercom.cn:18080/appGuide/ui/avatar.html#头像角标)

- 通过`dot`参数设置显示头像角标，值`true`为显示角标，`false`为不显示角标
- 通过`dotPosition`参数设置角标位置，值为左上`leftTop`、右上`rightTop`、左下`leftBottom`、 右下`rightBottom`、上中`topCenter`、下中`bottomCenter`、自定义`customLocation`
- 通过`dotSelfLocalization`参数设置自定义角标位置，当`dotPosition`参数的值为`customLocation`时才有效，值为`top`、`right`、`bottom`、`left`
- 通过`content`参数设置角标内容
- 通过`dotTheme`参数设置角标样式，值为`primary`, `warning`, `success`, `error`, `info`

```vue
<template>
  <ct-demo-card title="头像角标">
    <view class="" style="display: flex;flex-wrap: wrap;">
      <ct-ui-avatar
        :src="img"
        :border="true"
        style="margin-right: 20px;"
        shape="square"
        round="20rpx"
        size="large"
        :dot="true"
        dotPosition="leftTop"
        content="数字"
      />
      <ct-ui-avatar
        :border="true"
        style="margin-right: 20px;"
        shape="square"
        round="20rpx"
        size="large"
        label="文字"
        :dot="true"
        content="数字"
        dotTheme="primary"
      />
      <ct-ui-avatar
        :src="img"
        :border="true"
        style="margin-right: 20px;"
        shape="square"
        round="20rpx"
        size="large"
        :dot="true"
        content="数字"
        dotTheme="primary"
        :dotSelfLocalization="dotSelfLocalization"
        dotPosition="customLocation"
      />
    </view>
  </ct-demo-card>
</template>

<script>
export default {
  data() {
    return {
      img: require('@/static/images/ct_logo.png'),
      dotSelfLocalization: {
        top: '10px',
        right: '20px'
      }
    }
  }
}
</script>

<style lang="scss">
.avatar-page {
  padding: 12px;
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/avatar.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/avatar.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| shape               | 判断头像外形square：方形、circle：圆形，默认方形             | String           | circle   | circle \| square                                             |
| ------------------- | ------------------------------------------------------------ | ---------------- | -------- | ------------------------------------------------------------ |
| src                 | 头像地址                                                     | String           | -        | -                                                            |
| border              | 判断头像是否有边框true:有、false：无，默认true               | Boolean          | true     | true \| false                                                |
| borderColor         | 设置头像边框颜色                                             | String           | -        | -                                                            |
| radius              | 设置头像边框圆角，默认单位rpx                                | Number \| String | 0        | -                                                            |
| size                | 设置头像大小，large \| default \| small \| 数字 \| 数字rpx \| 数字px，默认default，数字默认rpx | Number \| String | default  | large \| default \| small \| 自定义传入，默认单位rpx         |
| label               | 判断头像是否是文字头像                                       | String           | -        | -                                                            |
| labelSize           | 设置文字头像里的文字大小，默认单位rpx                        | String \| Number | -        | -                                                            |
| labelColor          | 设置文字头像字体颜色                                         | String           | #eb4b4b  | -                                                            |
| bgColor             | 设置文字头像背景色                                           | String           | -        | -                                                            |
| shadow              | 设置头像阴影，值水平阴影的位置、垂直阴影的位置、模糊距离、阴影的尺寸、阴影的颜色 | String           | -        | -                                                            |
| dot                 | 判断头像是否显示角标                                         | Boolean          | false    | true \| false                                                |
| content             | 设置头像角标内容                                             | String \| Number | -        | -                                                            |
| dotTheme            | 设置头像角标主题                                             | String           | warning  | 设置头像角标主题，值为primary \| warning \| success \| error \| info |
| dotPosition         | 判断头像角标位置                                             | String           | rightTop | leftTop \| rightTop \| leftBottom \| rightBottom \| topCenter \| bottomCenter \| customLocation |
| dotSelfLocalization | 设置头像角标自定位                                           | Object           | {}       | -                                                            |
| defaultAvatar       | 设置默认头像                                                 | String           | -        | -                                                            |
| modes               | 设置图片缩放比例                                             | String           | -        | scaleToFill \| aspectFit \| aspectFill \| widthFix \| heightFix \| top \| bottom \| center \| left \| right \| top left \| top right \| bottom left \| bottom right |
| iconName            | 设置icon头像                                                 | String           | -        | -                                                            |
| iconSize            | 设置icon头像大小                                             | String \| Number | -        | -                                                            |
| iconColor           | 设置icon头像颜色                                             | String           | -        | -                                                            |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/avatar.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| click | 点击头像时触发 | -    |
| ----- | -------------- | ---- |
|       |                |      |