# [Guide 操作引导](http://mid.chinatowercom.cn:18080/appGuide/ui/guide.html#guide-操作引导)

该组件主要是对新用户使用时，对用户进行一个引导操作。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/guide.html#基本使用)

- 通过`guideList`参数传入操作引导所需对象数组
- 通过`guideList`操作引导对象数组中设置`select`属性设置对应内容类名
- 通过`guideList`操作引导对象数组中设置`content`属性设置文字内容

```vue
<template>
  <ct-ui-guide ref="guide" :guideList="guideList">
    <view class="demo">
      <view class="title">基本使用</view>
      <view class="contentA">内容一</view>
      <view class="contentB">内容二</view>
      <view class="contentC">内容三</view>
    </view>
  </ct-ui-guide>
</template>

<script>
export default {
  name: 'guide',
  data() {
    return {
      guideList: [
        {
          select: '.contentA',
          content: '内容一'
        },
        {
          select: '.contentB',
          content: '内容二'
        },
        {
          select: '.contentC',
          content: '内容三'
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss">
.demo {
  display: flex;
  flex-direction: column;
  align-items: left;
  height: 100%;
  width: 100%;
}
</style>
```

### [按钮属性](http://mid.chinatowercom.cn:18080/appGuide/ui/guide.html#按钮属性)

- 通过`guideList`操作引导对象数组中设置`skipShow`属性设置是否显示跳过按钮
- 通过`guideList`操作引导对象数组中设置`backHide`属性设置是否隐藏上一步按钮
- 通过`guideList`操作引导对象数组中设置`justify`属性设置对齐方式
- 通过`guideList`操作引导对象数组中设置`finishContent`属性设置完成按钮文字

```vue
<template>
  <ct-ui-guide ref="guide" :guideList="guideList">
    <view class="demo">
      <view class="title">按钮属性</view>
      <view class="contentA">内容一</view>
      <view class="contentB">内容二</view>
      <view class="contentC">内容三</view>
      <view class="contentD">内容四</view>
    </view>
  </ct-ui-guide>
</template>

<script>
export default {
  name: 'guide',
  data() {
    return {
      guideList: [
        {
          select: '.contentA',
          content: '内容一',
          skipShow: true
        },
        {
          select: '.contentB',
          content: '内容二',
          backHide: true
        },
        {
          select: '.contentC',
          content: '内容三',
          justify: 'left'
        },
        {
          select: '.contentD',
          content: '内容四',
          finishContent: '自定义完成按钮'
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss">
.demo {
  display: flex;
  flex-direction: column;
  align-items: left;
  height: 100%;
  width: 100%;

  view {
    width: 100px;
    margin: 20px;
  }
}
</style>
```

### [设置图片](http://mid.chinatowercom.cn:18080/appGuide/ui/guide.html#设置图片)

- 通过`guideList`操作引导对象数组中设置`image`属性设置图片

```vue
<template>
  <ct-ui-guide ref="guide" :guideList="guideList">
    <view class="demo">
      <view class="title">设置图片</view>
      <view class="contentA">内容一</view>
      <view class="contentB">内容二</view>
    </view>
  </ct-ui-guide>
</template>

<script>
export default {
  name: 'guide',
  data() {
    return {
      guideList: [
        {
          select: '.contentA',
          content: '内容一'
        },
        {
          select: '.contentB',
          image: {
            src: '/static/images/shang.png',
            width: '80px',
            height: '80px'
          }
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss">
.demo {
  display: flex;
  flex-direction: column;
  align-items: left;
  height: 100%;
  width: 100%;

  view {
    width: 100px;
    margin: 20px;
  }
}
</style>
```

### [自定义样式](http://mid.chinatowercom.cn:18080/appGuide/ui/guide.html#自定义样式)

- 通过`guideList`操作引导对象数组中设置`showStyle`属性设置显示层样式
- 通过`guideList`操作引导对象数组中设置`finishStyle`属性设置完成按钮样式

```vue
<template>
  <ct-ui-guide ref="guide" :guideList="guideList">
    <view class="demo">
      <view class="title">基本使用</view>
      <view class="contentA">内容一</view>
      <view class="contentB">内容二</view>
    </view>
  </ct-ui-guide>
</template>

<script>
export default {
  name: 'guide',
  data() {
    return {
      guideList: [
        {
          select: '.contentA',
          content: '内容一',
          skipShow: true,
          showStyle: {
            borderRadius: '50%'
          }
        },
        {
          select: '.contentB',
          content: '内容二',
          showStyle: {
            borderRadius: '50%'
          },
          finishStyle: {
            backgroundColor: '#3c9cff',
            border: 0,
            color: '#fff'
          }
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss">
.demo {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 100%;
  width: 100%;

  .contentA {
    width: 50px;
    text-align: center;
    line-height: 50px;
    height: 50px;
    margin: 50px;
  }

  .contentB {
    text-align: center;
    line-height: 100px;
    width: 100px;
    height: 100px;
    margin: 50px;
  }
}
</style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/guide.html#事件监听)

`back`事件可以监听点击上一步按钮时触发，`next`事件可以监听点击下一步按钮时触发，`skip`事件可以监听点击跳过按钮时触发，`finish`事件可以监听点击完成按钮时触发

```vue
<template>
  <ct-ui-guide
    ref="guide"
    :guideList="guideList"
    @back="back"
    @next="next"
    @finish="finish"
    @skip="skip"
  >
    <view class="demo">
      <view class="title">事件监听</view>
      <view class="contentA">内容一</view>
      <view class="contentB">内容二</view>
      <view class="contentC">内容三</view>
    </view>
  </ct-ui-guide>
</template>

<script>
export default {
  name: 'guide',
  data() {
    return {
      guideList: [
        {
          select: '.contentA',
          content: '内容一',
          skipShow: true
        },
        {
          select: '.contentB',
          content: '内容二'
        },
        {
          select: '.contentC',
          content: '内容三'
        }
      ]
    }
  },
  methods: {
    back(idx, backIdx) {
      console.log(idx, backIdx)
    },
    next(idx, nextIdx) {
      console.log(idx, nextIdx)
    },
    finish(idx) {
      console.log(idx)
    },
    skip(idx) {
      console.log(idx)
    }
  }
}
</script>

<style scoped lang="scss">
.demo {
  display: flex;
  flex-direction: column;
  align-items: left;
  height: 100%;
  width: 100%;

  view {
    width: 100px;
    margin: 20px;
  }
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/guide.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/guide.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| *guideList（必传） | 操作引导列表所需数组 | Array   | []     | [{content:"",select:"",backHide:true,nextHide:true,finishHide:true,skipShow:true,backContent:"",nextContent:"",finishContent:"",skipContent:"",justify:"center",image:{src:"",width:"",height:""},showStyle:{},backStyle:{},nextStyle:{},finishStyle:{},skipStyle:{}}] |
| ------------------ | -------------------- | ------- | ------ | ------------------------------------------------------------ |
| content            | 提示文字             | String  |        | -                                                            |
| select             | 对应显示内容类名     | String  |        | -                                                            |
| backHide           | 是否隐藏上一步按钮   | Boolean | false  | true/false                                                   |
| nextHide           | 是否隐藏下一步按钮   | Boolean | false  | true/false                                                   |
| finishHide         | 是否隐藏完成按钮     | Boolean | false  | true/false                                                   |
| skipShow           | 是否显示跳过按钮     | Boolean | false  | true/false                                                   |
| backContent        | 上一步按钮文字       | String  |        | -                                                            |
| nextContent        | 下一步按钮文字       | String  |        | -                                                            |
| finishContent      | 完成按钮文字         | String  |        | -                                                            |
| skipContent        | 跳过按钮文字         | String  |        | -                                                            |
| justify            | 对齐方式             | String  | center | left \| center \| right                                      |
| image              | 显示图片             | Object  |        | {}                                                           |
| showStyle          | 显示层样式           | Object  |        | {}                                                           |
| backStyle          | 上一步按钮样式       | Object  |        | {}                                                           |
| nextStyle          | 下一步按钮样式       | Object  |        | {}                                                           |
| finishStyle        | 完成按钮样式         | Object  |        | {}                                                           |
| skipStyle          | 跳过按钮样式         | Object  |        | {}                                                           |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/guide.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| back   | 点击上一步按钮时触发 | 当前下标，点击后的下标 |
| ------ | -------------------- | ---------------------- |
| next   | 点击下一步按钮时触发 | 当前下标，点击后的下标 |
| finish | 点击完成按钮时触发   | 当前下标               |
| skip   | 点击跳过按钮时触发   | 当前下标               |

#### [Methods](http://mid.chinatowercom.cn:18080/appGuide/ui/guide.html#methods)

| 名称 | 说明 | 所需参数 |
| ---- | ---- | -------- |
|      |      |          |

| open | 打开操作引导 | 下标 |
| ---- | ------------ | ---- |
|      |              |      |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/guide.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

|      | 页面内容 |      |
| ---- | -------- | ---- |
|      |          |      |