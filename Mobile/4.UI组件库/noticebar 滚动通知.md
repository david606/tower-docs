# [noticebar 滚动通知](http://mid.chinatowercom.cn:18080/appGuide/ui/noticebar.html#noticebar-滚动通知)

该组件一般用于通告滚动通知。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/noticebar.html#基本使用)

- 通过`text`参数定义显示的内容，数组
- 通过`direction`设置通告滚动模式，row-横向滚动，column-竖向滚动
- 通过`step`参数 direction = row 时，是否使用步进形式滚动
- 通过`icon`参数设置是否显示左侧的通知图标
- 通过`mode`参数设置通告模式，link-显示右箭头，closable-显示右侧关闭图标
- 通过`color`参数设置文字颜色，各图标也会使用文字颜色
- 通过`bgColor`参数设置背景颜色
- 通过`speed`参数设置水平滚动时的滚动速度，即每秒滚动多少 px(px)，这有利于控制文字无论多少时，都能有一个恒定的速度
- 通过`fontSize`参数设置字体大小
- 通过`duration`参数设置滚动一个周期的时间长，单位 ms
- 通过`disableTouch`参数设置是否禁止用手滑动切换
- 通过`customStyle`参数设置定义需要用到的外部样式

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-noticebar :text="text1" @click="click" />
         
    </ct-demo-card>
    <ct-demo-card title="可关闭">
      <ct-ui-noticebar
        :text="text5"
        mode="closable"
        @click="click"
        @ctNoticebarClose="ctNoticebarClose"
      />
         
    </ct-demo-card>
    <ct-demo-card title="自定义横向滚动速度">
      <ct-ui-noticebar
        :text="text2"
        speed="250"
        mode="closable"
        @click="click"
        @ctNoticebarClose="ctNoticebarClose"
      />
         
    </ct-demo-card>
    <ct-demo-card title="可跳转(点击右箭头)">
      <ct-ui-noticebar
        :text="text3"
        mode="link"
        @click="click"
        @ctNoticebarClose="ctNoticebarClose"
      />
         
    </ct-demo-card>
    <ct-demo-card title="横向步进滚动">
      <ct-ui-noticebar :text="text4" :step="true" @click="ctNoticebarOfStep" />
         
    </ct-demo-card>
    <ct-demo-card title="纵向滚动">
      <ct-ui-noticebar
        :text="text4"
        direction="column"
        @click="ctNoticebarOfColumn"
      />
         
    </ct-demo-card>
    <ct-demo-card title="自定义样式">
      <ct-ui-noticebar
        :text="text1"
        color="#f9ae3d"
        bgColor="#fdf6ec"
        @click="click"
      />
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      text1:
        '今夕何夕兮，搴舟中流。今日何日兮，得与王子同舟。蒙羞被好兮，不訾诟耻。心几烦而不绝兮，得知王子。山有木兮木有枝，心悦君兮君不知。',
      text2: '曾经沧海难为水，除却巫山不是云。取次花丛懒回顾，半缘修道半缘君。',
      text3:
        '我住长江头，君住长江尾。日日思君不见君，共饮长江水。此水几时休，此恨何时已。只愿君心似我心，定不负相思意。',
      text4: [
        '去年今日此门中',
        '人面桃花相映红',
        '人面不知何处去',
        '桃花依旧笑春风'
      ],
      text5: '人间四月芳菲尽，山寺桃花始盛开。长恨春归无觅处，不知转入此中来。'
    }
  },
  methods: {
    click() {
      this.$ctmobile.dialog.alertConfirm({
        title: '点击了通告栏',
        content: '横向滚动并且不是步进形式'
      })
    },
    ctNoticebarOfStep(e) {
      this.$ctmobile.dialog.alertConfirm({
        title: '点击了通告栏',
        content: '横向滚动并且是步进形式，参数为【' + e + '】'
      })
    },
    ctNoticebarOfColumn(e) {
      this.$ctmobile.dialog.alertConfirm({
        title: '点击了通告栏',
        content: '竖向滚动，参数为【' + e + '】'
      })
    },
    ctNoticebarClose() {
      this.$ctmobile.dialog.alertConfirm({
        title: '关闭了通告栏'
      })
    }
  }
}
</script>

<style lang="scss" scoped></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/noticebar.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/noticebar.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| text         | 显示的内容，数组                                             | String, Array  | -            | -           |
| ------------ | ------------------------------------------------------------ | -------------- | ------------ | ----------- |
| direction    | 通告滚动模式，row-横向滚动，column-竖向滚动                  | String         | row          | row\|column |
| step         | direction = row时，是否使用步进形式滚动                      | Boolean        | false        | false\|true |
| icon         | 是否显示左侧的通知图标                                       | String         | notification | -           |
| mode         | 通告模式，link-显示右箭头，closable-显示右侧关闭图标         | String         | -            | -           |
| color        | 文字颜色，各图标也会使用文字颜色                             | String         | #FFFFFF      | -           |
| bgColor      | 背景颜色                                                     | String         | #EB4B4B      | -           |
| speed        | 水平滚动时的滚动速度，即每秒滚动多少px(px)，这有利于控制文字无论多少时，都能有一个恒定的速度 | String, Number | 80           | -           |
| fontSize     | 字体大小                                                     | String, Number | 14           | -           |
| duration     | 滚动一个周期的时间长，单位ms                                 | String, Number | 2000         | -           |
| disableTouch | 是否禁止用手滑动切换                                         | Boolean        | true         | true\|false |
| customStyle  | 定义需要用到的外部样式                                       | Object         | -            | -           |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/noticebar.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| click            | 点击通告栏事件   | -    |
| ---------------- | ---------------- | ---- |
| ctNoticebarClose | 点击关闭按钮事件 | -    |