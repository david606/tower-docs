# [Rate 评分](http://mid.chinatowercom.cn:18080/appGuide/ui/rate.html#rate-评分)

该组件一般用于满意度调查，星型评分的场景

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/rate.html#基本使用)

- 通过`amount`参数设置评分数量

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-rate v-model="rate" />
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      rate: 0
    }
  }
}
</script>

<style lang="scss"></style>
```

### [自定义样式](http://mid.chinatowercom.cn:18080/appGuide/ui/rate.html#自定义样式)

- 通过`notColor`参数设置未选中颜色
- 通过`activeColor`参数设置选中颜色,颜色的数组列表请保证多余等于`amount`的大小
- 通过`size`参数设置 star 大小
- 通过`padding`参数设置 star 的间距

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义样式">
      <ct-ui-rate v-model="rate" notColor="#909399" />
      <ct-ui-rate
        v-model="rate"
        :activeColor="['#3c9cff', '#3c9cff', '#ccc', '#ccc', '#ff0000']"
      />
      <ct-ui-rate v-model="rate" :size="20" />
      <ct-ui-rate v-model="rate" :padding="20" />
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      rate: 0
    }
  }
}
</script>

<style lang="scss"></style>
```

### [评分类型](http://mid.chinatowercom.cn:18080/appGuide/ui/rate.html#评分类型)

- 通过`star`参数设置评分的类型，可选类型为`icon`、`text`

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="类型">
          <ct-ui-rate v-model="rate" :star="star1" />
      <ct-ui-rate v-model="rate" :star="star2" />
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      rate: 0,
      star1: {
        type: 'icon',
        notName: 'checkbox-circle',
        name: 'checkbox-circle-fill'
      },
      star2: {
        type: 'text',
        text: '好'
      }
    }
  }
}
</script>

<style lang="scss"></style>
```

### [选中一半](http://mid.chinatowercom.cn:18080/appGuide/ui/rate.html#选中一半)

- 通过`onHalf`参数设置是否开启选中一半

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="选中一半">
      <ct-ui-rate v-model="rate" :onHalf="true" :star="star1" />
         
    </ct-demo-card>
    <ct-demo-card title="选中一半">
      <ct-ui-rate v-model="rate" :onHalf="true" :star="star2" />
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      rate: 0,
      star1: {
        type: 'icon',
        notName: 'checkbox-circle',
        name: 'checkbox-circle-fill'
      },
      star2: {
        type: 'text',
        text: '好'
      }
    }
  }
}
</script>

<style lang="scss"></style>
```

### [提示语句](http://mid.chinatowercom.cn:18080/appGuide/ui/rate.html#提示语句)

- 通过`tipsHide`参数设置是否隐藏提示语句
- 通过`tips`参数传入提示语句

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="提示语句">
      <ct-ui-rate v-model="rate" :tipsHide="false" :tips="tips" />
      <ct-ui-rate v-model="rate2" :tipsHide="false" :tips="tips" />
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      rate: 0,
      rate2: 0,
      tips: ['bad', 'poor', 'sort', 'fine', 'nice!']
    }
  }
}
</script>

<style lang="scss"></style>
```

### [状态](http://mid.chinatowercom.cn:18080/appGuide/ui/rate.html#状态)

- 通过`state`参数设置 star 状态

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="正常状态">
      <ct-ui-rate v-model="rate" state="normal" />
         
    </ct-demo-card>
    <ct-demo-card title="只读状态">
      <ct-ui-rate v-model="rate1" state="read" />
         
    </ct-demo-card>
    <ct-demo-card title="禁用状态">
      <ct-ui-rate v-model="rate2" state="disable" />
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      rate: 2,
      rate1: 2,
      rate2: 2
    }
  }
}
</script>

<style lang="scss"></style>
```

### [其他功能](http://mid.chinatowercom.cn:18080/appGuide/ui/rate.html#其他功能)

- 通过`erash`参数设置是否开启擦除功能
- 通过`sliden`参数设置是否开启滑动选中功能

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="其他功能">
      <ct-ui-rate v-model="rate" :erash="true" />
      <ct-ui-rate v-model="rate" :sliden="true" />
      <ct-ui-rate v-model="rate" :onHalf="true" :sliden="true" />
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      rate: 0
    }
  }
}
</script>

<style lang="scss"></style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/rate.html#事件监听)

- 通过`v-model`双向绑定 star
- 通过`feedback`事件监听评分改变时触发
- 通过`click`事件监听点击事件

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="事件监听">
      <ct-ui-rate v-model="rate" @feedback="feedback" @click="click" />
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      rate: 0
    }
  },
  methods: {
    feedback(e) {
      console.log(e)
    },
    click(e) {
      console.log(e)
    }
  }
}
</script>

<style lang="scss"></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/rate.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/rate.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| value       | 评分                     | string  | —                                                       | —                         |
| ----------- | ------------------------ | ------- | ------------------------------------------------------- | ------------------------- |
| amount      | star数量                 | Number  | 5                                                       | -                         |
| most        | 最多选择star数量         | Number  |                                                         | -                         |
| hollowOut   | 是否镂空                 | Boolean | false                                                   | true/false                |
| star        | star类型（icon \| text） | Object  | {type: "icon",notName: "star",name: "star-fill",}       | confirm                   |
| activeColor | 选中颜色                 | Array   | ['#909399', '#909399', '#FAD400', '#FAD400', '#FFA940'] | -                         |
| notColor    | 未选中颜色               | String  | #dedede                                                 | -                         |
| tipsColor   | 提示语句文字颜色         | String  | #eb4b4b                                                 | -                         |
| state       | 状态                     | String  | normal                                                  | normal \| read \| disable |
| padding     | 间距，单位px             | Number  | 20                                                      | —                         |
| size        | 字体大小，单位px         | Number  | 40                                                      | —                         |
| foneColor   | 字体颜色                 | string  | #FFFFFF                                                 | —                         |
| tips        | 提示语句                 | Array   | []                                                      | —                         |
| tipsHide    | 是否隐藏提示语句         | Boolean | true                                                    | true/false                |
| onHalf      | 是否开启选中一半         | Boolean | false                                                   | true/false                |
| erash       | 是否开启擦除             | Boolean | false                                                   | true/false                |
| sliden      | 是否开启滑动选择         | Boolean | false                                                   | true/false                |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/rate.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| click    | 点击事件     | -    |
| -------- | ------------ | ---- |
| feedback | 评分改变事件 |      |