# [Text 文本组件](http://mid.chinatowercom.cn:18080/appGuide/ui/textarea.html#text-文本组件)

该组件主要是多行纯文本编辑控件，适用于评论或反馈表单中的一段意见。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/textarea.html#基本使用)

- 通过`value`参数传入内容

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
         
      <ct-ui-textarea
        v-model="value"
        border="surround"
        @input="handleInput"
      ></ct-ui-textarea>
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ctTextArea',
  data() {
    return {
      value: ''
    }
  },
  methods: {
    handleInput(e) {
      console.log('e::', e)
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [字数统计](http://mid.chinatowercom.cn:18080/appGuide/ui/textarea.html#字数统计)

- 通过`showWordLimit`参数设置是否进行字数统计；

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="字数统计">
      <ct-ui-textarea
        v-model="value"
        height="180"
        border="surround"
        :confirmType="null"
        showWordLimit
        autoHeight
        @input="handleInput"
      ></ct-ui-textarea>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ctTextArea',
  data() {
    return {
      value: ''
    }
  },
  methods: {
    handleInput(e) {
      console.log('e::', e)
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [自动高度](http://mid.chinatowercom.cn:18080/appGuide/ui/textarea.html#自动高度)

- 通过`autoHeight`参数设置自动高度，如果为 true，则设定的 height 则不起效

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自动高度">
      <ct-ui-textarea
        v-model="value"
        border="surround"
        :confirmType="null"
        autoHeight
        @input="handleInput"
      ></ct-ui-textarea>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ctTextArea',
  data() {
    return {
      value: ''
    }
  },
  methods: {
    handleInput(e) {
      console.log('e::', e)
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [高度限制](http://mid.chinatowercom.cn:18080/appGuide/ui/textarea.html#高度限制)

通过`height`参数设置高度，如果为 autoHeight 则无效

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="高度限制">
      <ct-ui-textarea
        v-model="value"
        height="100"
        border="surround"
        showWordLimit
        @input="handleInput"
      ></ct-ui-textarea>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ctTextArea',
  data() {
    return {
      value: ''
    }
  },
  methods: {
    handleInput(e) {
      console.log('e::', e)
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [禁用](http://mid.chinatowercom.cn:18080/appGuide/ui/textarea.html#禁用)

通过`disabled`参数设置禁用

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="禁用">
      <ct-ui-textarea
        v-model="value"
        height="180"
        border="surround"
        :confirmType="null"
        showWordLimit
        autoHeight
        @input="handleInput"
        disabled
      ></ct-ui-textarea>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ctTextArea',
  data() {
    return {
      value: ''
    }
  },
  methods: {
    handleInput(e) {
      console.log('e::', e)
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [下边框](http://mid.chinatowercom.cn:18080/appGuide/ui/textarea.html#下边框)

通过`border`设置为 bottom，则显示下边框

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="下边框">
      <ct-ui-textarea
        v-model="value"
        height="180"
        border="bottom"
        :confirmType="null"
        showWordLimit
        autoHeight
        @input="handleInput"
      ></ct-ui-textarea>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ctTextArea',
  data() {
    return {
      value: ''
    }
  },
  methods: {
    handleInput(e) {
      console.log('e::', e)
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/textarea.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/textarea.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| value                  | 输入框的内容                                                 | String                      |                      | -                                                            | v1.0.34+ |
| ---------------------- | ------------------------------------------------------------ | --------------------------- | -------------------- | ------------------------------------------------------------ | -------- |
| placeholder            | 输入框为空时占位符                                           | String                      |                      | 请输入                                                       | v1.0.34+ |
| placeholderStyle       | 指定 placeholder 的样式                                      | String                      | color: #c0c4cc       | -                                                            | v1.0.34+ |
| placeholderClass       | 指定 placeholder 的样式类                                    | String                      | textarea-placeholder | -                                                            | v1.0.34+ |
| height                 | 输入框高度                                                   | String \| Number            | 70                   | -                                                            | v1.0.34+ |
| disabled               | 是否禁用                                                     | Boolean                     | false                | -                                                            | v1.0.34+ |
| maxlength              | 最大输入长度，设置为 -1 的时候不限制最大长度                 | Number                      | 140                  | -                                                            | v1.0.34+ |
| focus                  | 获取焦点                                                     | Boolean                     | false                | true \| false                                                | v1.0.34+ |
| autoFocus              | 自动聚焦，拉起键盘                                           | Boolean                     | false                | true \| false                                                | v1.0.34+ |
| autoHeight             | 自动增高，值类型为 number 时，表示最小高度；值为 auto 时，表示自动撑满父容器。是否自动增高，设置auto-height时，style.height不生效 | Boolean \| Number \| String | false                | true \| false                                                | v1.0.34+ |
| fixed                  | Fixed                                                        | Boolean                     | false                | true \| false                                                | v1.0.34+ |
| cursorSpacing          | 指定光标与键盘的距离，单位 px                                | Number                      | 0                    | -                                                            | v1.0.34+ |
| cursor                 | 指定focus时的光标位置                                        | Number                      | -                    | -                                                            | v1.0.34+ |
| cursorColor            | 光标颜色                                                     | String                      |                      | -                                                            |          |
| showWordLimit          | 是否显示字数统计                                             | Boolean                     | false                | true \| false                                                | v1.0.34+ |
| confirmType            | 设置键盘右下角按钮的文字                                     | String \| null              | null                 | send \| done \| search \| next \| go                         | v1.0.34+ |
| confirmHold            | 点击键盘右下角按钮时是否保持键盘不收起                       | Boolean                     | false                | true \| false                                                | v1.0.34+ |
| showConfirmBar         | 是否显示键盘上方带有”完成“按钮那一栏                         | Boolean                     | true                 | true \| false                                                | v1.0.34+ |
| selectionStart         | 光标起始位置，自动聚焦时有效，需与selection-end搭配使用      | Number                      | -1                   | -                                                            | v1.0.34+ |
| selectionEnd           | 光标结束位置，自动聚焦时有效，需与selection-start搭配使用    | Number                      | -1                   | -                                                            | v1.0.34+ |
| adjustPosition         | 键盘弹起时，是否自动上推页面                                 | Boolean                     | true                 | true \| false                                                | v1.0.34+ |
| disableDefaultPadding  | 是否去掉 iOS 下的默认内边距                                  | Boolean                     | false                | true \| false                                                | v1.0.34+ |
| holdKeyboard           | focus时，点击页面的时候不收起键盘                            | Boolean                     | false                | true \| false                                                | v1.0.34+ |
| autoBlur               | 键盘收起时，是否自动失去焦点                                 | Boolean                     | false                | true \| false                                                | v1.0.34+ |
| ignoreCompositionEvent | 是否忽略组件内对文本合成系统事件的处理                       | Boolean                     | true                 | true \| false                                                | v1.0.34+ |
| inputmode              | 数据类型的提示                                               | String                      | text                 | none \| text \| decimal \| numeric \| tel \| email \| url \| search \| idcard | v1.0.34+ |
| minRows                | 最小行数                                                     | Number                      | 2                    | -                                                            | v1.0.34+ |
| shape                  | 圆角                                                         | Number                      | 0                    | -                                                            | v1.0.34+ |
| border                 | 边框                                                         | String                      | none                 | surround 四周 \| bottom 底部 \| none 没有任何边框            | v1.0.34+ |
| borderColor            | 边框颜色                                                     | String                      | #8590A6              | -                                                            | v1.0.34+ |
| borderWidth            | 边框                                                         | String                      | 1                    | -                                                            | v1.0.34+ |
| size                   | 文字大小(px)                                                 | String \| Number            | 14                   | -                                                            | v1.0.34+ |
| color                  | 文字颜色                                                     | String                      | #303133              | -                                                            | v1.0.34+ |
| customStyle            | 自定义样式                                                   | Object                      | {}                   | -                                                            | v1.0.34+ |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/textarea.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| focus                | 输入框聚焦时触发                 | event.detail = { value, height }，height 为键盘高度    |
| -------------------- | -------------------------------- | ------------------------------------------------------ |
| blur                 | 输入框失去焦点时触发             | event.detail = {value, cursor}                         |
| linechange           | 输入框行数变化时调用             | event.detail = {height: 0, heightRpx: 0, lineCount: 0} |
| input                | 当键盘输入时，触发 input 事件    | 输入的内容                                             |
| confirm              | 点击完成时， 触发 confirm 事件   | event.detail = {value: value}                          |
| keyboardheightchange | 键盘高度发生变化的时候触发此事件 | event.detail = {height: height, duration: duration}    |