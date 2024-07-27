# [Keyboard 键盘](http://mid.chinatowercom.cn:18080/appGuide/ui/keyboard.html#keyboard-键盘)

该组件主要使用在特殊场景下用户需要输入某些值，可以起到更加方便安全的作用

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/keyboard.html#基本使用)

- 通过`visible`参数设置是否显示键盘，支持 **.sync** 修饰符
- 通过`v-model`绑定`value`获取当前点击按键
- 通过`click`事件监听点击按键时触发

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
         
      <ct-ui-keyboard
        :visible.sync="visible"
        tips="基本使用"
        v-model="value"
        @click="click"
        @backspace="backspace"
      />
      <text class="demo-text" @tap="turnon" :style="[{borderColor}]">
        {{ text }}
        <text v-if="!text.length">基本使用</text>
      </text>
         
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      visible: false,
      value: '',
      text: '',
      borderColor: ''
    }
  },
  watch: {
    visible(e) {
      this.borderColor = e ? '#09bafa' : '#dcdfe6'
    }
  },
  methods: {
    click() {
      this.text += this.value
    },
    backspace() {
      this.text = this.text.slice(0, this.text.length - 1)
    },
    turnon() {
      this.visible = true
    }
  }
}
</script>
<style lang="scss">
.demo-page {
  .demo-text {
    position: relative;
    display: inline-block;
    border: 1px solid #dcdfe6;
    width: 480rpx;
    height: 60rpx;
    line-height: 60rpx;
    border-radius: 10rpx;
    padding: 0 20rpx;
    margin: 16rpx 10rpx;
    text {
      position: absolute;
      height: 100%;
      top: 0;
      left: 20rpx;
      color: #a8a8a8;
    }
  }
}
</style>
```

### [键盘模式](http://mid.chinatowercom.cn:18080/appGuide/ui/keyboard.html#键盘模式)

- 通过`mode`参数设置键盘模式，`number`数字模式、`idCard`身份证模式、`password`密码模式、`car`车牌号模式

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="键盘模式">
         
      <ct-ui-keyboard
        :visible.sync="visible"
        tips="键盘模式"
        v-model="value"
        :mode="mode"
        @click="click"
        @backspace="backspace"
      />
      <ct-ui-checkbox
        :list="list"
        :choice="false"
        @checkboxClick="checkboxClick"
      ></ct-ui-checkbox>
      <text class="demo-text" @tap="turnon" :style="[{borderColor}]">
        {{ text }}
        <text v-if="!text.length">键盘模式</text>
      </text>
         
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      visible: false,
      value: '',
      text: '',
      borderColor: '',
      mode: 'number',
      list: [
        {
          title: '数字键盘',
          id: 'number'
        },
        {
          title: '身份证键盘',
          id: 'idCard'
        },
        {
          title: '密码键盘',
          id: 'password'
        },
        {
          title: '车牌号键盘',
          id: 'car'
        }
      ]
    }
  },
  watch: {
    visible(e) {
      this.borderColor = e ? '#09bafa' : '#dcdfe6'
    }
  },
  methods: {
    click() {
      this.text += this.value
    },
    backspace() {
      this.text = this.text.slice(0, this.text.length - 1)
    },
    turnon() {
      this.visible = true
    },
    checkboxClick(list) {
      this.mode = list.id
    }
  }
}
</script>
<style lang="scss">
.demo-page {
  .demo-text {
    position: relative;
    display: inline-block;
    border: 1px solid #dcdfe6;
    width: 480rpx;
    height: 60rpx;
    line-height: 60rpx;
    border-radius: 10rpx;
    padding: 0 20rpx;
    margin: 16rpx 10rpx;
    text {
      position: absolute;
      height: 100%;
      top: 0;
      left: 20rpx;
      color: #a8a8a8;
    }
  }
}
</style>
```

### [皮肤选择](http://mid.chinatowercom.cn:18080/appGuide/ui/keyboard.html#皮肤选择)

- 通过`theme`参数设置键盘皮肤模式，`white`白、`black`黑、`ctRed`铁塔红

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="键盘模式">
         
      <ct-ui-keyboard
        :visible.sync="visible"
        tips="键盘模式"
        v-model="value"
        mode="password"
        :theme="theme"
        @click="click"
        @backspace="backspace"
      />
      <ct-ui-checkbox
        :list="list"
        :choice="false"
        @checkboxClick="checkboxClick"
      ></ct-ui-checkbox>
      <text class="demo-text" @tap="turnon" :style="[{borderColor}]">
        {{ text }}
        <text v-if="!text.length">键盘模式</text>
      </text>
         
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      visible: false,
      value: '',
      text: '',
      borderColor: '',
      theme: 'number',
      list: [
        {
          title: 'white 白',
          id: 'white'
        },
        {
          title: 'black 黑',
          id: 'black'
        },
        {
          title: 'ctRed 铁塔红',
          id: 'ctRed'
        }
      ]
    }
  },
  watch: {
    visible(e) {
      this.borderColor = e ? '#09bafa' : '#dcdfe6'
    }
  },
  methods: {
    click() {
      this.text += this.value
    },
    backspace() {
      this.text = this.text.slice(0, this.text.length - 1)
    },
    turnon() {
      this.visible = true
    },
    checkboxClick(list) {
      this.theme = list.id
    }
  }
}
</script>
<style lang="scss">
.demo-page {
  .demo-text {
    position: relative;
    display: inline-block;
    border: 1px solid #dcdfe6;
    width: 480rpx;
    height: 60rpx;
    line-height: 60rpx;
    border-radius: 10rpx;
    padding: 0 20rpx;
    margin: 16rpx 10rpx;
    text {
      position: absolute;
      height: 100%;
      top: 0;
      left: 20rpx;
      color: #a8a8a8;
    }
  }
}
</style>
```

### [数字键盘设置](http://mid.chinatowercom.cn:18080/appGuide/ui/keyboard.html#数字键盘设置)

- 通过`point`参数设置是否开启小数点
- 通过`upset`参数设置是否开启随机打乱键盘
- 通过`showClose`参数设置是否显示关闭按钮

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="数字键盘设置">
         
      <ct-ui-keyboard
        :visible.sync="visible"
        tips="数字键盘设置"
        v-model="value"
        :point="point"
        :upset="upset"
        :showClose="showClose"
        @click="click"
        @backspace="backspace"
      />
      <ct-ui-checkbox
        :list="list"
        :choice="false"
        @checkboxClick="checkboxClick"
      ></ct-ui-checkbox>
      <text class="demo-text" @tap="turnon" :style="[{borderColor}]">
        {{ text }}
        <text v-if="!text.length">数字键盘设置</text>
      </text>
         
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      visible: false,
      value: '',
      text: '',
      borderColor: '',
      point: false,
      upset: false,
      showClose: false,
      list: [
        {
          title: '开启小数点',
          id: 'point'
        },
        {
          title: '开启随机打乱',
          id: 'upset'
        },
        {
          title: '显示关闭按钮',
          id: 'showClose'
        }
      ]
    }
  },
  watch: {
    visible(e) {
      this.borderColor = e ? '#09bafa' : '#dcdfe6'
    }
  },
  methods: {
    click() {
      this.text += this.value
    },
    backspace() {
      this.text = this.text.slice(0, this.text.length - 1)
    },
    turnon() {
      this.visible = true
    },
    checkboxClick(list) {
      ;(this.point = false),
        (this.upset = false),
        (this.showClose = false),
        (this[list.id] = true)
    }
  }
}
</script>
<style lang="scss">
.demo-page {
  .demo-text {
    position: relative;
    display: inline-block;
    border: 1px solid #dcdfe6;
    width: 480rpx;
    height: 60rpx;
    line-height: 60rpx;
    border-radius: 10rpx;
    padding: 0 20rpx;
    margin: 16rpx 10rpx;
    text {
      position: absolute;
      height: 100%;
      top: 0;
      left: 20rpx;
      color: #a8a8a8;
    }
  }
}
</style>
```

### [自定义设置](http://mid.chinatowercom.cn:18080/appGuide/ui/keyboard.html#自定义设置)

- 通过`radius`参数设置按键圆角大小
- 通过`confirmText`参数设置确认按键文字内容
- 通过`closeText`参数设置关闭按键文字内容
- 通过`fontColor`参数设置按键字体颜色（操作按键除外）
- 通过`duration`参数设置键盘打开动画时间，单位 ms

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义设置">
         
      <ct-ui-keyboard
        :visible.sync="visible"
        tips="自定义设置"
        v-model="value"
        :radius="40"
        confirmText="自定义确认"
        closeText="收起"
        fontColor="rgb(247, 78, 78)"
        theme="ctRed"
        :duration="400"
        @click="click"
        @backspace="backspace"
      />
      <text class="demo-text" @tap="turnon" :style="[{borderColor}]">
        {{ text }}
        <text v-if="!text.length">自定义设置</text>
      </text>
         
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      visible: false,
      value: '',
      text: '',
      borderColor: ''
    }
  },
  watch: {
    visible(e) {
      this.borderColor = e ? '#09bafa' : '#dcdfe6'
    }
  },
  methods: {
    click() {
      this.text += this.value
    },
    backspace() {
      this.text = this.text.slice(0, this.text.length - 1)
    },
    turnon() {
      this.visible = true
    }
  }
}
</script>
<style lang="scss">
.demo-page {
  .demo-text {
    position: relative;
    display: inline-block;
    border: 1px solid #dcdfe6;
    width: 480rpx;
    height: 60rpx;
    line-height: 60rpx;
    border-radius: 10rpx;
    padding: 0 20rpx;
    margin: 16rpx 10rpx;
    text {
      position: absolute;
      height: 100%;
      top: 0;
      left: 20rpx;
      color: #a8a8a8;
    }
  }
}
</style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/keyboard.html#事件监听)

-`click`事件监听按键被点击时触发 -`longpress`事件监听按键长按时触发 -`touchend`事件监听按键松开时触发 -`backspace`事件监听点击退格按键时触发 -`confirm`事件监听按点击确认按键时触发 -`open`事件监听组件打开时触发 -`close`事件监听组件关闭时触发

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="事件监听">
         
      <ct-ui-keyboard
        :visible.sync="visible"
        tips="事件监听"
        v-model="value"
        @click="click"
        @longpress="longpress"
        @touchend="touchend"
        @backspace="backspace"
        @confirm="confirm"
        @open="open"
        @close="close"
      />
      <text class="demo-text" @tap="turnon" :style="[{borderColor}]">
        {{ text }}
        <text v-if="!text.length">事件监听</text>
      </text>
         
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      visible: false,
      value: '',
      text: '',
      borderColor: ''
    }
  },
  watch: {
    visible(e) {
      this.borderColor = e ? '#09bafa' : '#dcdfe6'
    }
  },
  methods: {
    click() {
      this.text += this.value
      console.log('click')
    },
    backspace() {
      this.text = this.text.slice(0, this.text.length - 1)
      console.log('backspace')
    },
    turnon() {
      this.visible = true
    },
    confirm() {
      console.log('confirm')
    },
    open() {
      console.log('open')
    },
    close() {
      console.log('close')
    },
    longpress() {
      console.log('longpress')
    },
    touchend() {
      console.log('touchend')
    }
  }
}
</script>
<style lang="scss">
.demo-page {
  .demo-text {
    position: relative;
    display: inline-block;
    border: 1px solid #dcdfe6;
    width: 480rpx;
    height: 60rpx;
    line-height: 60rpx;
    border-radius: 10rpx;
    padding: 0 20rpx;
    margin: 16rpx 10rpx;
    text {
      position: absolute;
      height: 100%;
      top: 0;
      left: 20rpx;
      color: #a8a8a8;
    }
  }
}
</style>
```

### [注意事项](http://mid.chinatowercom.cn:18080/appGuide/ui/keyboard.html#注意事项)

- 由于**input**在移动端上点击就会出现手机自带键盘，且官方并未给出解决方法，所以建议在使用`keyboard`组件时通过将**text**等标签自定义成**input**

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/keyboard.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/keyboard.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| visible     | 是否显示 keyboard，支持 .sync 修饰符               | Boolean       | false  | true/false                          |
| ----------- | -------------------------------------------------- | ------------- | ------ | ----------------------------------- |
| value       | 当前按下的键盘对应值                               | String,Number | right  | -                                   |
| mode        | 键盘模式                                           | String        | number | number \| idCard \| password \| car |
| theme       | 皮肤模式                                           | String        | white  | white \| black \| ctRed             |
| point       | 是否开启小数点，(mode=number有效)                  | Boolean       | true   | true/false                          |
| upset       | 是否开启随机打乱键盘，(mode=number有效)            | Boolean       | true   | true/false                          |
| confirmText | 确认按钮的文字内容                                 | String,Number | 确认   | -                                   |
| closeText   | 关闭按钮的文字内容                                 | String,Number | 关闭   | -                                   |
| radius      | 按钮圆角大小                                       | String,Number | 20rpx  | -                                   |
| fontColor   | 字体颜色（操作按键除外）                           | String        | #000   | -                                   |
| showClose   | 是否显示关闭按钮                                   | Boolean       | true   | true/false                          |
| automatic   | 输入文字之后是否自动切换到字母模式（mode=car有效） | Boolean       | true   | true/false                          |
| duration    | 打开动画时间，单位ms                               | Number        | 240    | -                                   |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/keyboard.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| click     | 按键被点击时触发   | 点击的按键 |
| --------- | ------------------ | ---------- |
| longpress | 按键长按时触发     | 长按的按键 |
| touchend  | 按键松开时触发     | 松开的按键 |
| backspace | 点击退格按键时触发 | -          |
| confirm   | 点击确认按键时触发 | -          |
| open      | 组件打开时触发     | -          |
| close     | 组件关闭时触发     | -          |