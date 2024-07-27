# [Steps 步骤条](http://mid.chinatowercom.cn:18080/appGuide/ui/steps.html#steps-步骤条)

该组件一般用于完成一个任务要分几个步骤，标识目前处于第几步的场景。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/steps.html#基本使用)

- 通过设置`steps`的`current`参数设置当前处于第几步
- 通过设置`step`的`title`参数设置步骤标题
- 通过设置`step`的`content`参数设置步骤内容

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
         
      <ct-ui-steps :current="2">
        <ct-ui-step title="步骤一" content="2021-04-27"></ct-ui-step>
        <ct-ui-step title="步骤二" content="2021-05-28"></ct-ui-step>
        <ct-ui-step title="步骤三" content="2021-06-29"></ct-ui-step>
      </ct-ui-steps>
         
    </ct-demo-card>
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {}
  }
}
</script>

<style lang="scss"></style>
```

### [自定义样式](http://mid.chinatowercom.cn:18080/appGuide/ui/steps.html#自定义样式)

- 通过设置`steps`的`activeColor`参数设置已完成颜色（图标/数字）
- 通过设置`steps`的`disActiveColor`参数设置未完成颜色（图标/数字）
- 通过设置`steps`的`stepActiveColor`参数设置已完成颜色（步骤文字）
- 通过设置`steps`的`stepDisActiveColor`参数设置未完成颜色（步骤文字）
- 通过设置`step`的`titleSize`参数设置标题文字大小
- 通过设置`step`的`descSize`参数设置描述文字大小

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义样式">
         
      <ct-ui-steps
        :current="2"
        activeColor="#5ac725"
        stepActiveColor="#07c160"
        stepDisActiveColor="#78797e"
        disActiveColor="#78797e"
      >
        <ct-ui-step title="步骤一" content="2021-04-27"></ct-ui-step>
        <ct-ui-step title="步骤二" content="2021-05-28"></ct-ui-step>
        <ct-ui-step
          title="步骤三"
          content="2021-06-29"
          titleSize="20px"
          descSize="10px"
        ></ct-ui-step>
      </ct-ui-steps>
         
    </ct-demo-card>
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {}
  }
}
</script>

<style lang="scss"></style>
```

### [设置 icon](http://mid.chinatowercom.cn:18080/appGuide/ui/steps.html#设置-icon)

- 通过设置`step`的`icon`参数设置 icon 的 name 属性，若不设置显示圆

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置icon">
         
      <ct-ui-steps :current="2">
        <ct-ui-step
          icon="home-fill"
          title="步骤一"
          content="2021-04-27"
        ></ct-ui-step>
        <ct-ui-step
          icon="lock-unlock"
          title="步骤二"
          content="2021-05-28"
        ></ct-ui-step>
        <ct-ui-step
          icon="upload"
          title="步骤三"
          content="2021-06-29"
        ></ct-ui-step>
      </ct-ui-steps>
       
    </ct-demo-card>
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {}
  }
}
</script>

<style lang="scss"></style>
```

### [设置状态](http://mid.chinatowercom.cn:18080/appGuide/ui/steps.html#设置状态)

- 通过设置`step`的`status`参数设置每一个单独的步骤状态，**process**（进行）| **error**（错误，优先级大于 activeColor）| **finish**（完成）

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置状态">
         
      <ct-ui-steps :current="2" activeColor="#3c9cff" stepActiveColor="#3c9cff">
        <ct-ui-step
          status="process"
          title="process进行中"
          content="2021-04-27"
        ></ct-ui-step>
        <ct-ui-step
          status="finish"
          title="finish完成"
          content="2021-05-28"
        ></ct-ui-step>
        <ct-ui-step
          status="error"
          title="error错误"
          content="2021-06-29"
        ></ct-ui-step>
      </ct-ui-steps>
       
    </ct-demo-card>
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {}
  }
}
</script>

<style lang="scss"></style>
```

### [设置方向](http://mid.chinatowercom.cn:18080/appGuide/ui/steps.html#设置方向)

- 通过设置`steps`的`direction`参数设置步骤条的排列方向，参数为**row**，**column**

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置方向">
         
      <ct-ui-steps :current="2" direction="column">
        <ct-ui-step title="步骤一" content="2021-04-27"></ct-ui-step>
        <ct-ui-step title="步骤二" content="2021-05-28"></ct-ui-step>
        <ct-ui-step title="步骤三" content="2021-06-29"></ct-ui-step>
      </ct-ui-steps>
         
    </ct-demo-card>
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {}
  }
}
</script>

<style lang="scss"></style>
```

### [使用方式](http://mid.chinatowercom.cn:18080/appGuide/ui/steps.html#使用方式)

- 此组件可以通过调用 ct-ui-step 标签设置每一个步骤，也可以通过数组的方式调用

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="使用方式">
      <ct-ui-steps :current="2" :list="list"></ct-ui-steps>
         
    </ct-demo-card>
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {
      list: [
        {
          title: '步骤一',
          content: '2021-04-27'
        },
        {
          title: '步骤二',
          content: '2021-04-27'
        },
        {
          title: '步骤三',
          content: '2021-04-27'
        }
      ]
    }
  }
}
</script>

<style lang="scss"></style>
```

### [STEPS](http://mid.chinatowercom.cn:18080/appGuide/ui/steps.html#steps)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/steps.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| current            | 当前处于第几步         | String \| Number | —       | —             |
| ------------------ | ---------------------- | ---------------- | ------- | ------------- |
| direction          | 排列方向               | String           | row     | row \| column |
| activeColor        | 已完成颜色（图标）     | String           | #FF6A6C | —             |
| disActiveColor     | 未完成颜色（图标）     | String           | #909399 | —             |
| stepActiveColor    | 已完成颜色（步骤文字） | String           | #FF6A6C | —             |
| stepDisActiveColor | 未完成颜色（步骤文字） | String           | #606266 | —             |
| iconSIze           | 图标尺寸（单位rpx）    | String \| Number | 24      | —             |
| lineStyleChange    | 线段样式是否随进度变化 | Boolean          | false   | —             |
| multipleData       | 多数据显示模式         | Boolean          | false   | —             |
| multipleDataText   | 多数据显示文本         | String           |         | —             |

### [STEP](http://mid.chinatowercom.cn:18080/appGuide/ui/steps.html#step)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/steps.html#props-1)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| title            | 标题                             | String,Number    | —     | —                                                |
| ---------------- | -------------------------------- | ---------------- | ----- | ------------------------------------------------ |
| content          | 描述                             | String,Number    | —     | —                                                |
| icon             | icon的name属性，若不设置则为数字 | String           | —     | —                                                |
| status           | 状态                             | String           |       | process（进行）\| error（错误）\| finish（完成） |
| titleSize        | 标题文字大小（单位rpx）          | String           | —     | 28                                               |
| icon             | 描述文字大小（单位rpx）          | String           | —     | 24                                               |
| iconSIze         | 图标尺寸（单位rpx）              | String \| Number | 24    | —                                                |
| lineStyleChange  | 线段样式是否随进度变化           | Boolean          | false | —                                                |
| multipleData     | 多数据显示模式                   | Boolean          | false | —                                                |
| multipleDataText | 多数据显示文本                   | String           |       | —                                                |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/steps.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| click | 点击step时触发 | -    |
| ----- | -------------- | ---- |
|       |                |      |

### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/steps.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

|      | 自定义内容 | -    |
| ---- | ---------- | ---- |
|      |            |      |