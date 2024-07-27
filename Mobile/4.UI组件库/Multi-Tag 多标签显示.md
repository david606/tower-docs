# [Multi-Tag 多标签显示](http://mid.chinatowercom.cn:18080/appGuide/ui/multiTag.html#multi-tag-多标签显示)

组件用于多标签显示场景。**`(v1.0.25+支持)`**

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/multiTag.html#基本使用)

- 通过`options`参数定义 Tag 列表，**一维数组**
- 通过`mode`参数定义显示的模式，scroll 滚动，inner 可视区域，wrap 自定换行

```vue
<template>
  <view class="demo-page">
    <ct-ui-multi-tag
      ref="refTag"
      :options="options"
      color="#ffffff"
      bgColor="#eb4b4b"
      @click="handleClick"
      @arrowClick="handleArrowClick"
    ></ct-ui-multi-tag>
  </view>
</template>

<script>
export default {
  name: 'multiTag',
  data() {
    return {
      options: [
        '新闻资讯',
        '腾讯文档',
        '网易云',
        '铁塔',
        '横琴马拉松',
        '港珠澳大桥'
      ]
    }
  },
  methods: {
    handleClick(index, item) {
      console.log(index, item)
    },
    handleArrowClick() {
      console.log('handleArrowClick')
    }
  }
}
</script>
```

### [自定义 mode 模式，scroll 滚动、inner 只显示可视区域、wrap 可视区域自动换行](http://mid.chinatowercom.cn:18080/appGuide/ui/multiTag.html#自定义-mode-模式-scroll-滚动、inner-只显示可视区域、wrap-可视区域自动换行)

通过设定**mode**，显示不同的视图展示

```vue
<template>
  <view class="demo-page">
    <view class="h2">inner</view>
    <ct-ui-multi-tag
      ref="refTagInner"
      :options="options"
      mode="inner"
      color="#ffffff"
      bgColor="#eb4b4b"
      @click="handleClick"
      @arrowClick="handleArrowClick"
    ></ct-ui-multi-tag>
    <view class="h2">wrap</view>
    <ct-ui-multi-tag
      ref="refTagWrap"
      :options="options"
      mode="wrap"
      color="#ffffff"
      bgColor="#eb4b4b"
      @click="handleClick"
      @arrowClick="handleArrowClick"
    ></ct-ui-multi-tag>
  </view>
</template>

<script>
export default {
  name: 'multiTag',
  data() {
    return {
      options: [
        '新闻资讯',
        '腾讯文档',
        '网易云',
        '铁塔',
        '横琴马拉松',
        '港珠澳大桥'
      ]
    }
  },
  methods: {
    handleClick(index, item) {
      console.log(index, item)
    },
    handleArrowClick() {
      console.log('handleArrowClick')
    }
  }
}
</script>

<style scoped lang="scss">
.h2 {
  font-weight: 500;
  font-size: 32rpx;
  padding: 20rpx 0;
}
</style>
```

### [最多显示个数，默认为 auto，自动判断](http://mid.chinatowercom.cn:18080/appGuide/ui/multiTag.html#最多显示个数-默认为-auto-自动判断)

通过`maxCount`设置最多可显示的 Tag 标签数量，默认为自适应

```vue
<template>
  <view class="demo-page">
    <view class="h2">自动适配</view>
    <ct-ui-multi-tag
      :options="options"
      mode="inner"
      color="#ffffff"
      bgColor="#eb4b4b"
      @click="handleClick"
      @arrowClick="handleArrowClick"
    ></ct-ui-multi-tag>
    <view class="h2">设置最大个数</view>
    <ct-ui-multi-tag
      :options="options"
      mode="inner"
      color="#ffffff"
      :maxCount="2"
      bgColor="#eb4b4b"
      @click="handleClick"
      @arrowClick="handleArrowClick"
    ></ct-ui-multi-tag>
  </view>
</template>

<script>
export default {
  name: 'multiTag',
  data() {
    return {
      options: [
        '新闻资讯',
        '腾讯文档',
        '网易云',
        '铁塔',
        '横琴马拉松',
        '港珠澳大桥'
      ]
    }
  },
  methods: {
    handleClick(index, item) {
      console.log(index, item)
    },
    handleArrowClick() {
      console.log('handleArrowClick')
    }
  }
}
</script>

<style scoped lang="scss">
.h2 {
  font-weight: 500;
  font-size: 32rpx;
  padding: 20rpx 0;
}
</style>
```

### [超出提示带/不带单位](http://mid.chinatowercom.cn:18080/appGuide/ui/multiTag.html#超出提示带-不带单位)

通过`exceedTipUnit`设置超出提示单位名称

```vue
<template>
  <view class="demo-page">
    <view class="h2">带单位，默认为个</view>
    <ct-ui-multi-tag
      ref="refTagWithUnit"
      :options="options"
      mode="inner"
      color="#ffffff"
      bgColor="#eb4b4b"
      @click="handleClick"
      @arrowClick="handleArrowClick"
    ></ct-ui-multi-tag>
    <view class="h2">不带单位，exceedTipUnit设置为空即可</view>
    <ct-ui-multi-tag
      ref="refTagWithOutUnit"
      :options="options"
      mode="inner"
      color="#ffffff"
      exceedTipUnit=""
      bgColor="#eb4b4b"
      @click="handleClick"
      @arrowClick="handleArrowClick"
    ></ct-ui-multi-tag>
  </view>
</template>

<script>
export default {
  name: 'multiTag',
  data() {
    return {
      options: [
        '新闻资讯',
        '腾讯文档',
        '网易云',
        '铁塔',
        '横琴马拉松',
        '港珠澳大桥'
      ]
    }
  },
  methods: {
    handleClick(index, item) {
      console.log(index, item)
    },
    handleArrowClick() {
      console.log('handleArrowClick')
    }
  }
}
</script>

<style scoped lang="scss">
.h2 {
  font-weight: 500;
  font-size: 32rpx;
  padding: 20rpx 0;
}
</style>
```

### [设置显示的字符最大长度](http://mid.chinatowercom.cn:18080/appGuide/ui/multiTag.html#设置显示的字符最大长度)

通过`maxLabelTextLength`设置显示的字符最大长度

```vue
<template>
  <view class="demo-page">
    <ct-ui-multi-tag
      ref="refTagMaxLabel"
      :options="options"
      mode="inner"
      color="#ffffff"
      :maxLabelTextLength="2"
      bgColor="#eb4b4b"
      @click="handleClick"
      @arrowClick="handleArrowClick"
    ></ct-ui-multi-tag>
  </view>
</template>

<script>
export default {
  name: 'multiTag',
  data() {
    return {
      options: [
        '新闻资讯',
        '腾讯文档',
        '网易云',
        '铁塔',
        '横琴马拉松',
        '港珠澳大桥'
      ]
    }
  },
  methods: {
    handleClick(index, item) {
      console.log(index, item)
    },
    handleArrowClick() {
      console.log('handleArrowClick')
    }
  }
}
</script>
```

### [手动重排，通过 refs 调用 resetLayout 方法](http://mid.chinatowercom.cn:18080/appGuide/ui/multiTag.html#手动重排-通过-refs-调用-resetlayout-方法)

通过**refs**调用`resetLayout`方法

```vue
<template>
  <view class="demo-page">
    <ct-ui-multi-tag
      ref="refTagReset"
      :options="options"
      color="#ffffff"
      bgColor="#eb4b4b"
      @click="handleClick"
      @arrowClick="handleArrowClick"
    ></ct-ui-multi-tag>
    <ct-ui-button @click="resetLayout" class="ct-u-m-t-32"
      >重置排版</ct-ui-button
    >
  </view>
</template>

<script>
export default {
  name: 'multiTag',
  data() {
    return {
      options: [
        '新闻资讯',
        '腾讯文档',
        '网易云',
        '铁塔',
        '横琴马拉松',
        '港珠澳大桥'
      ]
    }
  },
  methods: {
    handleClick(index, item) {
      console.log(index, item)
    },
    handleArrowClick() {
      console.log('handleArrowClick')
    },
    resetLayout() {
      this.$refs.refTagReset.resetLayout()
    }
  }
}
</script>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/multiTag.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/multiTag.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| options             | 显示值集合                   | Array            | []            | -                                              | v1.0.25+ |
| ------------------- | ---------------------------- | ---------------- | ------------- | ---------------------------------------------- | -------- |
| mode                | 模式                         | String           | scroll        | scroll 滚动 \| inner 可视区域 \| wrap 自定换行 | v1.0.25+ |
| showExceedTip       | 是否显示+N提示               | Boolean          | true          | true ｜ false                                  | v1.0.25+ |
| exceedTipUnit       | 提示的单位                   | String ｜ null   | 个            | -                                              | v1.0.25+ |
| maxCount            | 最大显示数量                 | String ｜ Number | auto          | -                                              | v1.0.25+ |
| maxLabelTextLength  | 最大显示文本长度             | Number ｜ null   | null          | -                                              | v1.0.25+ |
| maxLabelPlaceholder | 超出显示字符                 | String           | ...           | -                                              | v1.0.25+ |
| showRightIcon       | 是否显示右侧图标             | Boolean          | true          | true ｜ false                                  | v1.0.25+ |
| icon                | 右侧icon图标，参照ct-ui-icon | String           | chevron-right | -                                              | v1.0.25+ |
| iconSize            | 右侧icon图标大小             | String \| Number | 24            | -                                              | v1.0.25+ |
| iconColor           | 右侧icon图标颜色             | String           | #8590a6       | -                                              | v1.0.25+ |
| color               | 颜色                         | String           | #262F40       | -                                              | v1.0.25+ |
| size                | 文字大小,单位rpx             | String \| Number | 28            | -                                              | v1.0.25+ |
| bgColor             | 背景颜色                     | String           | #ffffff       | -                                              | v1.0.25+ |
| radius              | 圆角,单位rpx                 | String \| Number | 8             | -                                              | v1.0.25+ |
| border              | 是否边框                     | Boolean          | true          | true ｜ false                                  | v1.0.25+ |
| borderColor         | 边框颜色                     | String           | #EB4B4B       | -                                              | v1.0.25+ |
| borderSize          | 边框大小，单位rpx            | String ｜ Number | 2             | -                                              | v1.0.25+ |
| gutter              | 间距                         | String ｜ Number | 10            | -                                              | v1.0.25+ |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/multiTag.html#events)

| 事件名 | 说明 | 回调参数 | 版本 |
| ------ | ---- | -------- | ---- |
|        |      |          |      |

| resetLayout | 手动重排     | -                                           | v1.0.25+ |
| ----------- | ------------ | ------------------------------------------- | -------- |
| click       | tag 点击     | index options 下标，item options 下标对应值 | v1.0.25+ |
| arrowClick  | 右侧图标点击 | -                                           | v1.0.25+ |