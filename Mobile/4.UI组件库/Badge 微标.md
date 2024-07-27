# [Badge 微标](http://mid.chinatowercom.cn:18080/appGuide/ui/badge.html#badge-微标)

该组件一般用于出现在按钮、图标旁的数字或状态标记，提示用户点击，有圆点和圆包含文字两种形式。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/badge.html#基本使用)

- 通过`content`参数定义徽标内容
- 通过`type`设置主题，分别是`primary`(蓝色-主色)，`warning`(黄色-警告)， `error`(红色-错误)，`success`(绿色-成功)，`info`(灰色-信息)
- 通过`max`参数控制最大值，超过最大值会显示 '${max}+'
- 通过`isDot`参数设置小圆点

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-badge :is-dot="isDot" :max="max" :content="content" show>
        <view class="box"> </view>
      </ct-ui-badge>
      <ct-ui-badge :is-dot="isDot" show>
        <view class="box"> </view>
      </ct-ui-badge>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Badge',
  data() {
    return {
      content: 100,
      max: 99,
      isDot: false,
      bgColor: '#000000'
    }
  }
}
</script>

<style scoped lang="scss">
.box {
  width: 50px;
  height: 50px;
  border-radius: 10px;
  background-color: #999999;
  margin-left: 25px;
}
</style>
```

### [设置主题](http://mid.chinatowercom.cn:18080/appGuide/ui/badge.html#设置主题)

通过`type`进行主题样式，可选值可以为`primary`(蓝色-主色)，`warning`(黄色-警告)， `error`(红色-错误)，`success`(绿色-成功)，`info`(灰色-信息)

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置主题">
      <ct-ui-badge
        type="primary"
        :is-dot="isDot"
        :max="max"
        :content="content"
        show
      >
        <view class="box primary">蓝色</view>
      </ct-ui-badge>
      <ct-ui-badge
        type="warning"
        :is-dot="isDot"
        :max="max"
        :content="content"
        show
      >
        <view class="box warning">黄色</view>
      </ct-ui-badge>
      <ct-ui-badge
        type="error"
        :is-dot="isDot"
        :max="max"
        :content="content"
        show
      >
        <view class="box error">红色</view>
      </ct-ui-badge>
      <ct-ui-badge
        type="success"
        :is-dot="isDot"
        :max="max"
        :content="content"
        show
      >
        <view class="box success">绿色</view>
      </ct-ui-badge>
      <ct-ui-badge
        type="info"
        :is-dot="isDot"
        :max="max"
        :content="content"
        show
      >
        <view class="box info">灰色</view>
      </ct-ui-badge>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Badge',
  data() {
    return {
      content: 100,
      max: 99,
      isDot: false,
      bgColor: '#000000'
    }
  }
}
</script>

<style scoped lang="scss">
.box {
  width: 50px;
  height: 50px;
  line-height: 50px;
  text-align: center;
  font-weight: bold;
  border-radius: 10px;
  background-color: #999999;
  margin-left: 25px;
  color: #fff;
}
.primary {
  color: #3c9cff;
}
.warning {
  color: #f9ae3d;
}
.error {
  color: #f56c6c;
}
.success {
  color: #5ac725;
}
.info {
  color: #ffffff;
}
</style>
```

### [设置徽标的类型为一个圆点](http://mid.chinatowercom.cn:18080/appGuide/ui/badge.html#设置徽标的类型为一个圆点)

通过`isDot`参数设置，该形式组件没有内容，只显示一个圆点

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置圆点">
      <ct-ui-badge :is-dot="isDot" show>
        <view class="box"> </view>
      </ct-ui-badge>
      <view class="title">只显示点</view>
      <ct-ui-badge is-dot show>
        <view class="box"> </view>
      </ct-ui-badge>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Badge',
  data() {
    return {
      content: 100,
      max: 99,
      isDot: false,
      bgColor: '#000000'
    }
  }
}
</script>

<style scoped lang="scss">
.box {
  width: 50px;
  height: 50px;
  border-radius: 10px;
  background-color: #999999;
  margin-left: 25px;
}
</style>
```

### [设置徽标为状态类型](http://mid.chinatowercom.cn:18080/appGuide/ui/badge.html#设置徽标为状态类型)

通过 `isDot` 及 `isStatus` 参数设置状态模式

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置状态">
      <ct-ui-badge
        is-dot
        type="primary"
        isStatus
        content="进行中"
      ></ct-ui-badge>
      <ct-ui-badge
        is-dot
        type="success"
        isStatus
        content="已完成"
      ></ct-ui-badge>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Badge',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss">
.box {
  width: 50px;
  height: 50px;
  border-radius: 10px;
  background-color: #999999;
  margin-left: 25px;
}
</style>
```

### [设置数字的显示方式](http://mid.chinatowercom.cn:18080/appGuide/ui/badge.html#设置数字的显示方式)

通过`numberType`参数设置数字的显示方式，可选参数值为 overflow|ellipsis|limit

- **overflow** 会根据 max 字段判断，超出显示${max}+
- **ellipsis** 会根据 max 判断，超出显示${max}...
- **limit** 会依据 1000 作为判断条件，超出 1000，显示${value/1000}K，比如 2.2k、3.34w，最多保留 2 位小数

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置数字的显示方式">
      <view>overflow</view>
      <ct-ui-badge
        type="primary"
        numberType="overflow"
        :is-dot="isDot"
        :max="max"
        :content="content"
        show
      >
        <view class="box"></view>
      </ct-ui-badge>
      <view>ellipsis</view>
      <ct-ui-badge
        type="warning"
        numberType="ellipsis"
        :is-dot="isDot"
        :max="max"
        :content="content"
        show
      >
        <view class="box"></view>
      </ct-ui-badge>
      <view>limit</view>
      <ct-ui-badge
        type="error"
        numberType="limit"
        :is-dot="isDot"
        :max="max"
        :content="content"
        show
      >
        <view class="box"></view>
      </ct-ui-badge>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Badge',
  data() {
    return {
      content: 14400,
      max: 99,
      isDot: false
    }
  }
}
</script>

<style scoped lang="scss">
.box {
  width: 50px;
  height: 50px;
  border-radius: 10px;
  background-color: #999999;
  margin-left: 25px;
}
</style>
```

### [自定义微标颜色](http://mid.chinatowercom.cn:18080/appGuide/ui/badge.html#自定义微标颜色)

通过`bgColor`参数设置自定义的微标背景颜色

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义颜色">
      <ct-ui-badge :is-dot="isDot" :bg-color="bgColor" :content="content" show>
        <view class="box"> </view>
      </ct-ui-badge>
      <ct-ui-badge
        :is-dot="isDot"
        type="success"
        max="999"
        :content="content"
        show
      >
        <view class="box"> </view>
      </ct-ui-badge>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Badge',
  data() {
    return {
      content: 100,
      max: 99,
      isDot: false,
      bgColor: '#000000'
    }
  }
}
</script>

<style scoped lang="scss">
.box {
  width: 50px;
  height: 50px;
  border-radius: 10px;
  background-color: #999999;
  margin-left: 25px;
}
</style>
```

### [自定义微标内容](http://mid.chinatowercom.cn:18080/appGuide/ui/badge.html#自定义微标内容)

通过`slot`插槽，设置自定义的微标内容及排版

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义徽标内容">
      <ct-ui-badge
        :is-dot="isDot"
        type="warning"
        max="999"
        :content="content"
        show
      >
        <view class="box"> </view>
        <template #content> 您好，徽标 </template>
      </ct-ui-badge>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Badge',
  data() {
    return {
      content: 100,
      max: 99,
      isDot: false,
      bgColor: '#000000'
    }
  }
}
</script>

<style scoped lang="scss">
.box {
  width: 50px;
  height: 50px;
  border-radius: 10px;
  background-color: #999999;
  margin-left: 25px;
}
</style>
```

### [独立使用](http://mid.chinatowercom.cn:18080/appGuide/ui/badge.html#独立使用)

通过设置无插入内容单独进行使用

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="独立展示">
      <ct-ui-badge :is-dot="isDot" :max="max" :content="content" show />
      <ct-ui-badge
        :is-dot="isDot"
        :max="max"
        :content="content"
        shape="horn"
        show
      />
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Badge',
  data() {
    return {
      content: 100,
      max: 99,
      isDot: false,
      bgColor: '#000000'
    }
  }
}
</script>

<style scoped lang="scss">
.box {
  width: 50px;
  height: 50px;
  border-radius: 10px;
  background-color: #999999;
  margin-left: 25px;
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/badge.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/badge.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| show        | 是否显示                      | Boolean        | false    | true \| false                                  |          |
| ----------- | ----------------------------- | -------------- | -------- | ---------------------------------------------- | -------- |
| type        | 主题类型                      | String         | error    | primary \| warning \| success \| error \| info |          |
| shape       | 徽标形状                      | String         | circle   | circle \| horn                                 |          |
| isDot       | 不展示数字，只有一个小点      | Boolean        | false    | true ｜ false                                  |          |
| isStatus    | 是否是状态                    | Boolean        | false    | true ｜ false                                  | V1.0.26+ |
| content     | 显示内容                      | Number｜String | -        | -                                              |          |
| max         | 最大值                        | Number｜String | 99       | -                                              |          |
| fontSize    | 内容字体大小                  | Number｜String | 12       | -                                              |          |
| fontWeight  | 内容字体粗体                  | Number｜String | 400      | -                                              |          |
| color       | 内容字内容字体颜色（支持hex） | String         | #ffffff  | -                                              |          |
| bgColor     | 背景颜色                      | String         | -        | -                                              |          |
| numberType  | 数字的显示方式                | String         | overflow | overflow \| ellipsis \| limit                  |          |
| showZero    | 当数值为 0 时，是否展示       | Boolean        | true     | true \| false                                  |          |
| customStyle | 外部自定义样式                | Object         | -        | -                                              |          |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/badge.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

| default | 徽标包裹的子元素 | -    |
| ------- | ---------------- | ---- |
| content | 自定义微标内容   | -    |