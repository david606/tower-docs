# [sticky 吸顶容器](http://mid.chinatowercom.cn:18080/appGuide/ui/sticky.html#sticky-吸顶容器)

该组件主要用于容器吸顶，当组件达到预设的到顶部距离时， 就会固定在指定位置，组件位置大于预设的顶部距离时，会重新按照正常的布局排列。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/sticky.html#基本使用)

- 该组件使用了 CSS 中 position: sticky 属性，sticky 元素会“固定”在离它最近的一个拥有“滚动机制”的祖先上，因此建议您将此组件放置在页面外层元素中，否则可能会导致 sticky 失效
- 通过`scrollTopNum`参数传入当前页面活动数值，通过调用页面生命周期 onPageScroll，监听页面滚动，参数为 Object，需要将 scrollTopNum 属性传递给组件

```vue
<template>
  <view class="dome">
    <view class="txt">
      <text>基础使用1</text>
      <text>滚动页面,即可看到下方的吸顶按钮1会吸顶。</text>
    </view>
    <ct-ui-sticky :scrollTopNum="scrollTopNum" :disable="disable">
      <view>
        <button class="sticky-btn">吸顶按钮1</button>
      </view>
    </ct-ui-sticky>
    <view style="height: 1000px;"></view>
    <view style="text-align: center;"> ---------已到底部--------- </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      scrollTopNum: 0,
      disable: false
    }
  },
  onPageScroll(e) {
    this.scrollTopNum = e.scrollTop
  }
}
</script>

<style scoped lang="scss">
.dome {
  padding: 20rpx;
  .txt {
    height: 200rpx;
    margin-bottom: 20rpx;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
  .sticky-btn {
    width: 90%;
    background-color: #eb4b4b;
    color: white;
  }
}
</style>
```

### [自定义距顶距离&滚动条距离](http://mid.chinatowercom.cn:18080/appGuide/ui/sticky.html#自定义距顶距离-滚动条距离)

- 通过`stickyTop`属性设置吸顶容器在吸顶时与顶部的距离
- 通过`scrollTop`属性设置滚动条距离

```vue
<template>
  <view class="dome">
    <view class="txt">
      <text>自定义距顶距离&滚动条距离</text>
    </view>
    <ct-ui-sticky
      class="sticky"
      :stickyTop="stickyTop"
      :scrollTop="scrollTop"
      :scrollTopNum="scrollTopNum"
      :backgroundColor="backgroundColor"
    >
    </ct-ui-sticky>
    <view style="height: 1000px;"></view>
    <view style="text-align: center;"> ---------已到底部--------- </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      scrollTopNum: 0,
      stickyTop: 60,
      scrollTop: 20,
      backgroundColor: '#eb4b4b'
    }
  },
  onPageScroll(e) {
    this.scrollTopNum = e.scrollTop
  }
}
</script>

<style scoped lang="scss">
.dome {
  padding: 20rpx;
  .txt {
    height: 100rpx;
    margin-bottom: 20rpx;
  }
  .sticky {
    padding: 20rpx;
    color: white;
    height: 200rpx;
  }
}
</style>
```

### [使用插槽](http://mid.chinatowercom.cn:18080/appGuide/ui/sticky.html#使用插槽)

- 支持设置插槽内容自行进行使用

```vue
<template>
  <view class="dome">
    <ct-ui-sticky
      class="sticky"
      :stickyTop="stickyTop"
      :scrollTopNum="scrollTopNum"
    >
      <view class="slotContent txt">
        <text>使用插槽</text>
      </view>
    </ct-ui-sticky>
    <view style="height: 1000px;"></view>
    <view style="text-align: center;"> ---------已到底部--------- </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      scrollTopNum: 0,
      stickyTop: 60
    }
  },
  onPageScroll(e) {
    this.scrollTopNum = e.scrollTop
  }
}
</script>

<style scoped lang="scss">
.dome {
  padding: 20rpx;
  .txt {
    height: 100rpx;
    margin-bottom: 20rpx;
  }
  .slotContent {
    background-color: #eb4b4b;
    border-radius: 20px;
    text-align: center;
    line-height: 50px;
  }
  .sticky {
    padding: 20rpx;
    color: white;
  }
}
</style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/sticky.html#事件监听)

- 通过`@change`事件可以监听吸顶容器是否已吸顶

```vue
<template>
  <view class="demo">
    <view class="txt">
      <text>使用插槽的吸顶容器</text>
    </view>
    <ct-ui-sticky :scrollTopNum="scrollTopNum" @change="stickyChange">
      <view>
        <button class="sticky-btn">吸顶按钮</button>
      </view>
    </ct-ui-sticky>
    <view style="height: 1000px;"></view>
    <view style="text-align: center;"> ---------已到底部--------- </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      scrollTopNum: 0,
      stickyTop: 60
    }
  },
  methods: {
    // 是否已吸顶
    stickyChange(e) {
      console.log('是否吸顶', e)
    }
  },
  onPageScroll(e) {
    this.scrollTopNum = e.scrollTop
  }
}
</script>

<style scoped lang="scss">
.dome {
  padding: 20rpx;
  .txt {
    height: 200rpx;
    margin-bottom: 20rpx;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
  .sticky-btn {
    width: 90%;
    background-color: #eb4b4b;
    color: white;
  }
}
</style>
```

### [注意事项](http://mid.chinatowercom.cn:18080/appGuide/ui/sticky.html#注意事项)

- 必须要传`scrollTopNum`参数，由于`scroll-view`的性能优化问题不适合放长列表，所以使用页面生命周期`onPageScroll`监听页面滚动，因为`onPageScroll`为页面生命周期，组件内部无法调用，所以需要将`scrollTopNum`参数传递给组件，监听页面滚动，参数为**Object**，需要将`scrollTopNum`属性传递给组件

```vue
<script>
export default {
  data() {
    return {}
  },
  onPageScroll(e) {
    this.scrollTopNum = e.scrollTop
  }
}
</script>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/sticky.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/sticky.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| *scrollTopNum（必传） | 滑动事件传递的距离 | Number  | 0                | -          |
| --------------------- | ------------------ | ------- | ---------------- | ---------- |
| scrollTop             | 滚动条距离         | Number  | 0                | —          |
| stickyTop             | 距顶距离           | Number  | 0                | —          |
| hasNativeHeader       | 是否包含原生顶部   | Boolean | false            | true/false |
| backgroundColor       | 容器背景色         | String  | rgba(0, 0, 0, 0) | -          |
| disable               | 是否禁止吸顶功能   | Boolean | false            | true/false |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/sticky.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| change | 事件可以监听容器是否已吸顶 | 吸顶容器是否已吸顶 |
| ------ | -------------------------- | ------------------ |
|        |                            |                    |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/sticky.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

| -    | 自定义吸顶容器内容 | -    |
| ---- | ------------------ | ---- |
|      |                    |      |