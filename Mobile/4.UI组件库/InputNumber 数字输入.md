# [InputNumber 数字输入](http://mid.chinatowercom.cn:18080/appGuide/ui/inputNumber.html#inputnumber-数字输入)

该组件一般用于商城购物选择物品数量的场景。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/inputNumber.html#基本使用)

- 通过`v-model`进行双向绑定**value**初始值

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-input-number v-model="value" />
       
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      value: 0
    }
  }
}
</script>
<style lang="scss"></style>
```

### [设置步长](http://mid.chinatowercom.cn:18080/appGuide/ui/inputNumber.html#设置步长)

- 通过`step`参数设置步长，每次加或减的值， 支持小数值

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置步长">
      <ct-ui-input-number v-model="value" :step="2" />
       
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      value: 0
    }
  }
}
</script>
<style lang="scss"></style>
```

### [限制输入范围](http://mid.chinatowercom.cn:18080/appGuide/ui/inputNumber.html#限制输入范围)

- 通过`max`参数设置限制输入最大值
- 通过`min`参数设置限制输入最大值

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="限制输入范围">
        <ct-ui-input-number v-model="value1" :min="0" />
      <ct-ui-input-number v-model="value2" :max="0" />
       
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      value1: 0,
      value2: 0
    }
  }
}
</script>
<style lang="scss"></style>
```

### [保留小数](http://mid.chinatowercom.cn:18080/appGuide/ui/inputNumber.html#保留小数)

- 通过`decimal`参数设置保留小数多少位

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="保留小数">
      <ct-ui-input-number v-model="value" :decimal="2" />
       
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      value: 0
    }
  }
}
</script>
<style lang="scss"></style>
```

### [禁用操作](http://mid.chinatowercom.cn:18080/appGuide/ui/inputNumber.html#禁用操作)

- 通过`disabled`参数设置禁用所有操作
- 通过`disabledInput`参数设置禁用输入操作

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="禁用操作">
        <ct-ui-input-number v-model="value1" disabled />
      <ct-ui-input-number v-model="value2" disabledInput />
       
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      value1: 0,
      value2: 0
    }
  }
}
</script>
<style lang="scss"></style>
```

### [大小样式](http://mid.chinatowercom.cn:18080/appGuide/ui/inputNumber.html#大小样式)

- 通过`size`参数设置组件大小，参数为`medium`、`small`、`mini`
- 通过`inputStyle`参数设置*input*样式
- 通过`cutStyle`参数设置左部分样式
- 通过`addStyle`参数设置右部分样式

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="大小样式">
        <ct-ui-input-number v-model="value1" size="medium" />
      <ct-ui-input-number v-model="value2" size="small" />
      <ct-ui-input-number v-model="value3" size="mini" />
      <ct-ui-input-number
        v-model="value4"
        :inputWrapCustomStyle="inputWrapCustomStyle"
        :cutStyle="cutStyle"
        :addStyle="addStyle"
      />
       
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      value1: 0,
      value2: 0,
      value3: 0,
      value4: 0,
      inputWrapCustomStyle: {
        width: '200rpx',
        textAlign: 'center',
        background: 'rgba(0, 0, 0, .1)'
      },
      cutStyle: {
        width: '100px',
        background: '#FFF'
      },
      addStyle: {
        width: '100px',
        background: '#FFF'
      }
    }
  }
}
</script>
<style lang="scss"></style>
```

### [slot 插槽](http://mid.chinatowercom.cn:18080/appGuide/ui/inputNumber.html#slot-插槽)

- 通过`cut`设置左部分插槽
- 通过`add`设置右部分插槽

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义slot">
       
      <ct-ui-input-number v-model="value">
        <template #cut>
          <view class="demo-cut">▼</view>
        </template>
        <template #add>
          <view class="demo-add">▲</view>
        </template>
      </ct-ui-input-number>
       
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      value: 0
    }
  }
}
</script>
<style lang="scss">
.demo-page {
  .demo-cut,
  .demo-add {
    width: 80rpx;
    height: 80rpx;
    line-height: 80rpx;
    text-align: center;
    background-color: #7af9f9;
    color: #fff;
  }
}
</style>
```

### [事件触发](http://mid.chinatowercom.cn:18080/appGuide/ui/inputNumber.html#事件触发)

- `entry`事件监听直接输入时触发
- `blur`事件监听 input 失去焦点时触发
- `focus`事件监听 input 聚焦时触发
- `add`事件监听点击增加时触发
- `cut`事件监听点击减少时触发

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="事件触发">
      <ct-ui-input-number
        v-model="value"
        @entry="entry"
        @blur="blur"
        @focus="focus"
        @add="add"
        @cut="cut"
      />
       
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      value: 0
    }
  },
  methods: {
    entry(e) {
      console.log(e, 'entry')
    },
    focus(e) {
      console.log(e, 'focus')
    },
    blur(e) {
      console.log(e, 'blur')
    },
    add(e) {
      console.log(e, 'add')
    },
    cut(e) {
      console.log(e, 'cut')
    }
  }
}
</script>
<style lang="scss"></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/inputNumber.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/inputNumber.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| value                | 进行双向数据绑定的数值 | Number           | 0                       | —                       |          |
| -------------------- | ---------------------- | ---------------- | ----------------------- | ----------------------- | -------- |
| step                 | 步长，每次加或减的值   | Number           | 1                       | -                       |          |
| placeholder          | placeholder值          | String           | -                       | -                       | v1.0.20+ |
| placeholderStyle     | placeholder的样式      | String           | color: #999999          | -                       | v1.0.20+ |
| placeholderClass     | placeholderClass 类名  | String           | input-placeholder       | -                       | v1.0.20+ |
| decimal              | 保留几位小数           | Number           | 0                       | -                       |          |
| min                  | 最小值                 | Number \| String | Number.MIN_SAFE_INTEGER | -                       |          |
| max                  | 最大值                 | Number \| String | Number.MAX_SAFE_INTEGER | -                       |          |
| disabled             | 禁止所有操作           | Boolean          | false                   | true \| false           |          |
| disabledInput        | 禁止输入操作           | Boolean          | false                   | true \| false           |          |
| width                | 输入框宽度             | Number \| String |                         | -                       |          |
| height               | 输入框高度             | Number \| String |                         | -                       |          |
| size                 | 大小类型               | String           | medium                  | medium \| small \| mini |          |
| textAlign            | 文本位置               | String           | center                  | left \| center \| right | v1.0.20+ |
| inputWrapCustomStyle | input 外包裹样式       | Object           | {}                      | -                       | v1.0.20+ |
| inputStyle           | 输入框样式             | Object           | {}                      | -                       |          |
| addStyle             | 右部分增加样式         | Object           | {}                      | -                       |          |
| cutStyle             | 左部分减少样式         | Object           | {}                      | -                       |          |
| addIcon              | 右部分增加icon         | Object           | {name: "plus",size: 20} | -                       |          |
| cutIcon              | 左部分减少icon         | Object           | {name: "plus",size: 20} | -                       |          |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/inputNumber.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| entry | 直接输入时触发      | 点击的对象 |
| ----- | ------------------- | ---------- |
| blur  | input失去焦点时触发 | -          |
| focus | input聚焦时触发     | -          |
| add   | 点击增加时触发      | -          |
| cut   | 点击减少时触发      | -          |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/inputNumber.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

| add  | 设置右部分增加插槽 | -    |
| ---- | ------------------ | ---- |
| cut  | 设置左部分减少插槽 | -    |