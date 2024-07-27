# [Button 按钮](http://mid.chinatowercom.cn:18080/appGuide/ui/button.html#button-按钮)

常用的操作按钮

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/button.html#基本使用)

- 通过`btnSize`参数设置按钮尺寸，该属性控制按钮高度，按钮宽度自适应父元素宽度，分别是`middle`(大号按钮)、`default`(常规按钮)、`small`(中号按钮)、`min`(小号按钮)
- 通过`shape`参数设置按钮形状，分别是`default`(默认方形)、`circle`(圆形)或自定义传入数字，单位 px

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="btnSize样式">
      <view class="demo-item">
        <ct-ui-button btnSize="middle">大</ct-ui-button>
      </view>
      <view class="demo-item">
        <ct-ui-button btnSize="default">常规</ct-ui-button>
      </view>
      <view class="demo-item">
        <ct-ui-button btnSize="small">中</ct-ui-button>
      </view>
      <view class="demo-item">
        <ct-ui-button btnSize="min">小</ct-ui-button>
      </view>
    </ct-demo-card>
    <ct-demo-card title="shape按钮形状">
      <view class="demo-item">
        <ct-ui-button shape="default">默认</ct-ui-button>
      </view>
      <view class="demo-item">
        <ct-ui-button shape="circle">圆形</ct-ui-button>
      </view>
      <view class="demo-item">
        <ct-ui-button shape="20">自定义</ct-ui-button>
      </view>
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

<style lang="scss">
.demo-page {
  .demo-item {
    width: 100%;
    box-sizing: border-box;
    display: inline-block;
    padding: 10px;
  }
}
</style>
```

### [样式类型](http://mid.chinatowercom.cn:18080/appGuide/ui/button.html#样式类型)

- 通过`type`参数设置样式类型，分别是`default`、`primary`、`info`、`warning`、`error`、`success`

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="type样式">
      <view class="demo-item">
        <ct-ui-button type="default">默认</ct-ui-button>
      </view>
      <view class="demo-item">
        <ct-ui-button type="primary">主要</ct-ui-button>
      </view>
      <view class="demo-item">
        <ct-ui-button type="info">消息</ct-ui-button>
      </view>
      <view class="demo-item">
        <ct-ui-button type="warning">警告</ct-ui-button>
      </view>
      <view class="demo-item">
        <ct-ui-button type="error">危险</ct-ui-button>
      </view>
      <view class="demo-item">
        <ct-ui-button type="success">成功</ct-ui-button>
      </view>
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

<style lang="scss">
.demo-item {
  width: 100%;
  box-sizing: border-box;
  display: inline-block;
  padding: 10px;
}
</style>
```

### [按钮类型](http://mid.chinatowercom.cn:18080/appGuide/ui/button.html#按钮类型)

- 通过`btnType`参数设置按钮类型，分别是`confirm`、`cancel`、`dashed`、`text`

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="btnType按钮样式">
      <view class="demo-item">
        <ct-ui-button btnType="confirm">主要</ct-ui-button>
      </view>
      <view class="demo-item">
        <ct-ui-button btnType="cancel">次要</ct-ui-button>
      </view>
      <view class="demo-item">
        <ct-ui-button btnType="dashed">虚线</ct-ui-button>
      </view>
      <view class="demo-item">
        <ct-ui-button btnType="text">文字</ct-ui-button>
      </view>
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

<style lang="scss">
.demo-item {
  width: 100%;
  box-sizing: border-box;
  display: inline-block;
  padding: 10px;
}
</style>
```

### [朴素按钮](http://mid.chinatowercom.cn:18080/appGuide/ui/button.html#朴素按钮)

- 通过`plain`参数设置是否为朴素按钮，背景变为透明

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="朴素按钮">
      <view class="demo-item">
        <ct-ui-button :plain="false">确认</ct-ui-button>
      </view>
      <view class="demo-item">
        <ct-ui-button :plain="true">确认</ct-ui-button>
      </view>
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

<style lang="scss">
.demo-item {
  width: 100%;
  box-sizing: border-box;
  display: inline-block;
  padding: 10px;
}
</style>
```

### [自定义样式](http://mid.chinatowercom.cn:18080/appGuide/ui/button.html#自定义样式)

- 通过`btnWidth`参数设置按钮宽度
- 通过`btnHeight`参数设置按钮高度
- 通过`fontSize`参数设置按钮字体大小
- 通过`fontColor`参数设置按钮字体颜色
- 通过`bgColor`参数设置按钮背景色
- 通过`disabledBgColor`参数设置按钮状态为禁止时的背景色
- 通过`disabledFontColor`参数设置按钮状态为禁止时的字体颜色
- 通过`customStyle`参数设置按钮的`style`属性（`customStyle`属性的权重最高）

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义样式">
      <view class="demo-item">
        <ct-ui-button
          :btnWidth="220"
          :btnHeight="70"
          :fontSize="20"
          bgColor="#3EBBC7"
          data-name="custom"
          >自定义样式</ct-ui-button
        >
      </view>

      <view class="demo-item">
        <ct-ui-button :customStyle="customStyle" data-name="custom"
          >自定义样式</ct-ui-button
        >
      </view>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      customStyle: {
        background: '#3EBBC7',
        fontSize: '20px',
        width: '200px',
        height: '60px',
        boxShadow: '0 8 32rpx rgba(62, 187, 199, 0.3)'
      }
    }
  }
}
</script>

<style lang="scss">
.demo-item {
  width: 100%;
  box-sizing: border-box;
  display: inline-block;
  padding: 10px;
}
</style>
```

### [按钮状态](http://mid.chinatowercom.cn:18080/appGuide/ui/button.html#按钮状态)

- 通过`state`参数设置按钮状态，分别是`normal`、`disable`、`loading`

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="state按钮状态">
      <view class="demo-item">
        <ct-ui-button state="normal">正常</ct-ui-button>
      </view>
      <view class="demo-item">
        <ct-ui-button state="disable">禁用</ct-ui-button>
      </view>
      <view class="demo-item">
        <ct-ui-button state="loading">加载中...</ct-ui-button>
      </view>
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

<style lang="scss">
.demo-item {
  width: 100%;
  box-sizing: border-box;
  display: inline-block;
  padding: 10px;
}
</style>
```

### [icon 图标](http://mid.chinatowercom.cn:18080/appGuide/ui/button.html#icon-图标)

- 通过`icon`参数设置 icon 图标，详细参数参考**icon**组件

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="icon图标">
      <view class="demo-item">
        <ct-ui-button
          :icon="icon"
          shape="default"
          btnSize="small"
        ></ct-ui-button>
      </view>
      <view class="demo-item">
        <ct-ui-button
          :icon="icon"
          shape="circle"
          btnSize="small"
        ></ct-ui-button>
      </view>
      <view class="demo-item">
        <ct-ui-button :icon="icon" shape="circle">收藏</ct-ui-button>
      </view>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      icon: {
        name: 'star',
        size: 17
      }
    }
  }
}
</script>

<style lang="scss">
.demo-item {
  width: 100%;
  box-sizing: border-box;
  display: inline-block;
  padding: 10px;
}
</style>
```

### [自定义插槽](http://mid.chinatowercom.cn:18080/appGuide/ui/button.html#自定义插槽)

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义插槽">
      <ct-ui-button bgColor="rgba(77, 122, 255, 0.15)" data-name="slot">
        <view class="btn-item">
          <view class="btn-item-point"></view>
          <view class="btn-item-text">自定义插槽</view>
        </view>
      </ct-ui-button>
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

<style lang="scss">
.btn-item {
  height: 40px;
  display: flex;
  align-items: center;
  text-align: center;
  .btn-item-point {
    width: 28rpx;
    height: 28rpx;
    border-radius: 14rpx;
    background: #4d7aff;
    margin-right: 20rpx;
  }
  .btn-item-text {
    height: 36rpx;
    line-height: 36rpx;
    font-size: 32rpx;
    color: #4d7aff;
  }
}
.demo-item {
  width: 100%;
  box-sizing: border-box;
  display: inline-block;
  padding: 10px;
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/button.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/button.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| type              | 样式类型                                                     | String           | default \| primary \| info \| warning \| error \| success    | default       |
| ----------------- | ------------------------------------------------------------ | ---------------- | ------------------------------------------------------------ | ------------- |
| btnSize           | 按钮大小                                                     | String           | middle \| default \| small \| min                            | middle        |
| btnType           | 按钮类型                                                     | String           | confirm \| cancel \| dashed \| text                          | confirm       |
| plain             | 是否为朴素按钮                                               | Boolean          | false                                                        | true \| false |
| btnWidth          | 按钮宽度，单位px                                             | Number \| String | 270                                                          | -             |
| btnHeight         | 按钮高度，单位px                                             | Number \| String | 45                                                           | -             |
| text              | 按钮文字                                                     | String           | -                                                            | -             |
| fontSize          | 字体大小                                                     | Number \| String | 16                                                           | -             |
| fontColor         | 字体颜色                                                     | String           | #FFFFFF                                                      | -             |
| icon              | 字体图标                                                     | Object           | {}                                                           | -             |
| shape             | 按钮形状                                                     | Number \| String | default \| circle \| 自定义传入数字，单位px                  | default       |
| bgColor           | 背景色                                                       | String           | linear-gradient(260.21deg, rgba(74, 151, 255, 1) 19.01%, rgba(68, 114, 255, 1) 124.37%) | -             |
| loading           | 加载中                                                       | Boolean          | false                                                        | -             |
| disabled          | 禁用                                                         | Boolean          | false                                                        | -             |
| disabledBgColor   | 禁止状态的背景色                                             | String           |                                                              | -             |
| disabledFontColor | 禁止状态的字体颜色                                           | String           |                                                              | -             |
| dataName          | 额外传参参数，用于小程序的data-xxx属性，通过target.dataset.name获取 | String           | —                                                            | -             |
| throttleTime      | 节流，一定时间内只能触发一次                                 | Number \| String | 100                                                          | -             |
| hoverClass        | 按下效果类名，需在css里自定义                                | String           | ct-default-hover                                             | -             |
| hoverStartTime    | 按住后多久出现点击态，单位毫秒                               | Number \| String | 20                                                           | -             |
| hoverStayTime     | 手指松开后点击态保留时间，单位毫秒                           | Number \| String | 150                                                          | -             |
| customStyle       | 自定义样式，对象形式，注意驼峰命名，并且值必须用引号包括     | object           | {}                                                           | -             |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/button.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| click | 按钮点击事件 | -    |
| ----- | ------------ | ---- |
|       |              |      |