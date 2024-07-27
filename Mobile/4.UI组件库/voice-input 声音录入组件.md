# [ct-ui-voice-input 声音录入组件](http://mid.chinatowercom.cn:18080/appGuide/ui/voiceInput.html#ct-ui-voice-input-声音录入组件)

在需要拾取声音时，可以使用该组件。该组件适配于 app 和小程序，在 app  中使用时，点击开始录音再次点击结束录音，在小程序中，点击录音，再次点击暂停-继续录音循环进行，长按按钮结束录音。如果使用 uniapp  开发，在使用该组件时需要在 manifest.json 文件中，配置项中选中`<uses-permission android:name="android.permission.RECORD_AUDIO"/>`。暂不适配 H5，在 H5 中请使用[js-audio-recorder](https://www.cnblogs.com/lpkshuai/p/17491846.html)包进行开发，

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/voiceInput.html#基本使用)

- 通过`tempFilePath`方法获取录音结束后的临时存储路径
- 点击录音按钮后，如果有麦克风权限直接录音，没有权限会通过`permissions`方法返回权限信息。(0 表示被临时拒绝 1 表示被永久拒绝)
- 通过`setPermissions`子组件方法，可以调起 app 中的权限设置界面

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-voice-input
        @permissions="permissions"
        @tempFilePath="tempFilePath"
        ref="voiceInput"
      ></ct-ui-voice-input>
    </ct-demo-card>
  </view>
</template>

<script>
const innerAudioContext = uni.createInnerAudioContext()
export default {
  data() {
    return {}
  },
  methods: {
    // 点击录音按钮后，没有权限会触发这个方法，有权限的时候直接开始录音
    permissions(type) {
      // type 0 表示被临时拒绝  1表示被永久拒绝
      if (type === 1) {
        // 调用组件setPermissions方法，可在安卓手机中进入权限设置界面
        this.$refs.voiceInput.setPermissions()
      }
    },
    tempFilePath(path) {
      // path 录音结束后临时存储路劲
      console.log(path)
      // 播放录音，检测录音是否正常
      innerAudioContext.src = path
      innerAudioContext.play()
    }
  }
}
</script>

<style lang="scss" scoped></style>
```

### [设置尺寸及样式](http://mid.chinatowercom.cn:18080/appGuide/ui/voiceInput.html#设置尺寸及样式)

- 通过`format`参数设置语音格式
- 通过`voiceSize`参数设置麦克风尺寸
- 通过`voiceButtonSize`参数设置麦克风外侧按钮尺寸
- 通过`voiceColor`参数设置麦克风颜色
- 通过`voiceButtonColor`参数设置麦克风外侧按钮颜色
- 通过`voiceIcon`参数设置麦克风自定义图标
- 通过`voiceCeaseIcon`参数设置停止录音的图标显示
- 通过`slot`插槽可重置录音按钮

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-voice-input
        @permissions="permissions"
        @tempFilePath="tempFilePath"
        ref="voiceInput"
      ></ct-ui-voice-input>
    </ct-demo-card>
    <ct-demo-card title="基本使用">
      <ct-ui-voice-input
        @permissions="permissions"
        @tempFilePath="tempFilePath"
        ref="voiceInput1"
      >
        <ct-ui-button btnSize="middle" @click="click">录音</ct-ui-button>
      </ct-ui-voice-input>
    </ct-demo-card>
  </view>
</template>

<script>
const innerAudioContext = uni.createInnerAudioContext()
export default {
  data() {
    return {}
  },
  methods: {
    // 点击录音按钮后，没有权限会触发这个方法，有权限的时候直接开始录音
    permissions(type) {
      // type 0 表示被临时拒绝  1表示被永久拒绝
      if (type === 1) {
        // 调用组件setPermissions方法，可在安卓手机中进入权限设置界面
        this.$refs.voiceInput.setPermissions()
      }
    },
    tempFilePath(path) {
      // path 录音结束后临时存储路劲
      console.log(path)
      // 播放录音，检测录音是否正常
      innerAudioContext.src = path
      innerAudioContext.play()
    },
    // 使用插槽后需要页面调用录音方法
    click() {
      // 这是鉴权方法，调用完成后，有权限自动录音，没有权限触发permissions方法
      this.$refs.voiceInput1.determinePermissions()
    }
  }
}
</script>

<style lang="scss" scoped></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/voiceInput.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/voiceInput.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| format            | 语音格式                                             | String           | mp3                                          | aac \| mp3 \| wav \| PCM |
| ----------------- | ---------------------------------------------------- | ---------------- | -------------------------------------------- | ------------------------ |
| voiceSize         | 麦克风尺寸（默认单位rpx）                            | String \| Number | 48                                           | —                        |
| voiceButtonSize   | 麦克风外侧按钮尺寸（默认单位rpx）                    | String \| Number | 120                                          | —                        |
| voiceColor        | 麦克风颜色                                           | String           | #fff                                         |                          |
| timeColor         | 录音时长文字颜色                                     | String           | #fff                                         |                          |
| voiceButtonColor  | 麦克风外侧按钮颜色                                   | String           | linear-gradient(to bottom, #3164F6, #4F9FFF) | —                        |
| voiceIcon         | 麦克风自定义图标                                     | String           | voice                                        | —                        |
| voiceContinueIcon | 继续录音的图标                                       | String           | arrow-right-fill                             | —                        |
| voiceSuspendIcon  | 暂停录音的图标                                       | String           | minus-square-fill                            | —                        |
| voiceCeaseIcon    | 停止录音的图标显示                                   | String           | checkbox-blank-fill                          | —                        |
| showDuratio       | 是否显示语音录制时长                                 | Boolean          | true                                         | —                        |
| limitDuration     | 限制语音录入时长（默认单位ms，最大不能超过600000ms） | Number           | 60000                                        | —                        |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/voiceInput.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| tempFilePath                | 停止录音时触发                 | 录音存放临时地址                  |
| --------------------------- | ------------------------------ | --------------------------------- |
| permissions                 | 点击录音后，没有麦克风权限触发 | 0 表示被临时拒绝  1表示被永久拒绝 |
| $refs.xxx.startRecording    | 开始录音功能，可直接触发       |                                   |
| $refs.xxx.stopRecording     | 暂停录音功能，可直接触发       |                                   |
| $refs.xxx.continueRecording | 继续录音功能，可直接触发       |                                   |
| $refs.xxx.ceaseRecording    | 停止录音功能，可直接触发       |                                   |