# [Grid 宫格布局](http://mid.chinatowercom.cn:18080/appGuide/ui/grid.html#grid-宫格布局)

该宫格组件一般用于同时展示多个同类项目的场景，可以给宫格的项目设置徽标组件([badge](http://mid.chinatowercom.cn:18080/appGuide/ui/badge.html))，或者图标等，用于展示内容或进行页面导航。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/grid.html#基本使用)

- 可配合`ct-ui-grid-item`使用
- 通过`border`设置为宫格的边框
- 通过`items`快速设置 item 内容
- 内部通过`ut-ui-grid-item`组件的 slot 设置宫格的内容
- 通过`direction`设置为格子内容排列的方向
- 通过使用`ct-ui-grid-item`可以单独使用

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-grid :border="false">
        <ct-ui-grid-item
          :icon="iconImg"
          label="综合查询"
          @click="itemClick"
        ></ct-ui-grid-item>
      </ct-ui-grid>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Grid',
  data() {
    return {
      iconImg:
        'https://listimg.pinclipart.com/picdir/s/485-4851736_free-png-search-icon-search-icon-free-download.png'
    }
  },
  methods: {
    itemClick(value) {
      console.log('click', value)
    }
  }
}
</script>
<style scoped lang="scss"></style>
```

### [自定义每行列数](http://mid.chinatowercom.cn:18080/appGuide/ui/grid.html#自定义每行列数)

通过`col`进行设置列数

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义每行列数">
         
      <ct-ui-grid :col="col" border square gutter="10px">
        <ct-ui-grid-item
          :icon="iconImg"
          label="综合查询"
          @click="itemClick"
        ></ct-ui-grid-item>
      </ct-ui-grid>
      <ct-ui-grid
        :col="col"
        :clickable="false"
        square
        border
        direction="textVertical"
        reverse
        gutter="10px"
      >
        <ct-ui-grid-item
          v-for="i in 8"
          :index="i"
          :key="i"
          :icon="iconImg"
          :label="`综合查询${i}`"
          @click="itemClick"
        ></ct-ui-grid-item>
      </ct-ui-grid>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Grid',
  data() {
    return {
      border: true,
      col: 3,
      hoverBgColor: '#000',
      iconImg:
        'https://listimg.pinclipart.com/picdir/s/485-4851736_free-png-search-icon-search-icon-free-download.png'
    }
  },
  methods: {
    itemClick(value) {
      console.log('click', value)
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [方形带边框带间距](http://mid.chinatowercom.cn:18080/appGuide/ui/grid.html#方形带边框带间距)

通过`border`参数设置边框，`square`参数设置方形

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="方形带边框带间距">
      <ct-ui-grid border square gutter="10px">
        <ct-ui-grid-item
          :icon="iconImg"
          label="综合查询"
          @click="itemClick"
        ></ct-ui-grid-item>
      </ct-ui-grid>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Grid',
  data() {
    return {
      border: true,
      col: 3,
      hoverBgColor: '#000',
      iconImg:
        'https://listimg.pinclipart.com/picdir/s/485-4851736_free-png-search-icon-search-icon-free-download.png'
    }
  },
  methods: {
    itemClick(value) {
      console.log('click', value)
    }
  }
}
</script>
<style scoped lang="scss"></style>
```

### [自定义文字 icon 大小、颜色](http://mid.chinatowercom.cn:18080/appGuide/ui/grid.html#自定义文字-icon-大小、颜色)

通过`iconSize` `labelSize` `labelColor`参数设置 icon、文字的颜色、字体大小

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-grid
        :col="col"
        :icon-size="iconSize"
        :label-size="labelSize"
        :label-color="labelColor"
        border
        square
        gutter="10px"
      >
        <ct-ui-grid-item
          :icon="iconImg"
          label="综合查询"
          @click="itemClick"
        ></ct-ui-grid-item>
      </ct-ui-grid>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Grid',
  data() {
    return {
      border: true,
      col: 3,
      hoverBgColor: '#000',
      labelSize: '16px',
      iconSize: '60rpx',
      labelColor: '#f00',
      iconImg:
        'https://listimg.pinclipart.com/picdir/s/485-4851736_free-png-search-icon-search-icon-free-download.png'
    }
  },
  methods: {
    itemClick(value) {
      console.log('click', value)
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [自定义文字 icon 排列方式](http://mid.chinatowercom.cn:18080/appGuide/ui/grid.html#自定义文字-icon-排列方式)

通过`direction`参数设置排列方式

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义文字icon排列方式">
          <view class="sec-title">icon 上 文字下</view>
      <ct-ui-grid direction="vertical" :col="col" border square gutter="10px">
        <ct-ui-grid-item
          :icon="iconImg"
          label="综合查询"
          @click="itemClick"
        ></ct-ui-grid-item>
      </ct-ui-grid>
      <view class="sec-title">icon 左 文字右</view>
      <ct-ui-grid direction="horizontal" :col="col" border square gutter="10px">
        <ct-ui-grid-item
          :icon="iconImg"
          label="综合查询"
          @click="itemClick"
        ></ct-ui-grid-item>
      </ct-ui-grid>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Grid',
  data() {
    return {
      border: true,
      col: 3,
      hoverBgColor: '#000',
      labelSize: '16px',
      iconSize: '60rpx',
      labelColor: '#f00',
      iconImg:
        'https://listimg.pinclipart.com/picdir/s/485-4851736_free-png-search-icon-search-icon-free-download.png'
    }
  },
  methods: {
    itemClick(value) {
      console.log('click', value)
    }
  }
}
</script>

<style scoped lang="scss">
.sec-title {
  font-size: 14px;
  font-weight: bold;
  line-height: 40px;
}
</style>
```

### [使用本地 Icon 字体图标](http://mid.chinatowercom.cn:18080/appGuide/ui/grid.html#使用本地-icon-字体图标)

通过`icon`、`icon-prefix`参数设置字体图标

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="使用本地Icon字体图标">
      <ct-ui-grid direction="vertical" :col="col" border square gutter="10px">
        <ct-ui-grid-item
          icon="chat-fill"
          iconColor="#f56c6c"
          iconSize="2rem"
          label="消息"
          @click="itemclick"
        />
        <ct-ui-grid-item
          icon="share"
          iconColor="#f56c6c"
          iconSize="2rem"
          label="分享"
          @click="itemclick"
        />
      </ct-ui-grid>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Grid',
  data() {
    return {
      col: 3
    }
  },
  methods: {
    itemClick(value) {
      console.log('click', value)
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [集合使用](http://mid.chinatowercom.cn:18080/appGuide/ui/grid.html#集合使用)

通过`items`参数设置集合

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-grid :col="col" :items="items" border square gutter="10px" />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Grid',
  data() {
    return {
      border: true,
      col: 3,
      items: [
        {
          label: '综合查询',
          icon: 'https://listimg.pinclipart.com/picdir/s/485-4851736_free-png-search-icon-search-icon-free-download.png',
          dot: true,
          direction: 'horizontal'
        },
        {
          label: '业务变更',
          icon: 'https://listimg.pinclipart.com/picdir/s/485-4851736_free-png-search-icon-search-icon-free-download.png',
          badge: 2
        },
        {
          label: '需求承接',
          icon: 'https://listimg.pinclipart.com/picdir/s/485-4851736_free-png-search-icon-search-icon-free-download.png',
          reverse: true
        },
        {
          label: '疑难问题',
          icon: 'https://listimg.pinclipart.com/picdir/s/485-4851736_free-png-search-icon-search-icon-free-download.png',
          badge: '52',
          direction: 'textHorizontal'
        }
      ]
    }
  },
  methods: {
    itemClick(value) {
      console.log('click', value)
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [ct-ui-grid-item 独立使用](http://mid.chinatowercom.cn:18080/appGuide/ui/grid.html#ct-ui-grid-item-独立使用)

通过设置无插入内容单独进行使用

```vue
<template>
  <view class="demo-page">
    <ct-ui-grid-item label="新闻资讯2" :icon="iconImg"></ct-ui-grid-item>
    <view class="label">使用本地Icon字体图标</view>
    <ct-ui-grid-item
      direction="vertical"
      border
      square
      gutter="10px"
      icon="chat-fill"
      label="消息"
    ></ct-ui-grid-item>
  </view>
</template>

<script>
export default {
  name: 'GridItem',
  data() {
    return {
      iconImg:
        'https://listimg.pinclipart.com/picdir/s/485-4851736_free-png-search-icon-search-icon-free-download.png'
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/grid.html#api)

#### [Grid Props](http://mid.chinatowercom.cn:18080/appGuide/ui/grid.html#grid-props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| col          | 列数                     | Number\|String | 4       | -                                                            |
| ------------ | ------------------------ | -------------- | ------- | ------------------------------------------------------------ |
| icon-size    | 图标大小                 | Number\|String | 42rpx   | -                                                            |
| icon-color   | 图标颜色                 | String         | #000000 | -                                                            |
| label-size   | 文字大小                 | Number\|String | 14px    | -                                                            |
| label-color  | 文本颜色                 | String         | -       | -                                                            |
| border       | 是否显示边框             | Boolean        | false   | true\|false                                                  |
| center       | 内容居中                 | Boolean        | true    | true\|false                                                  |
| gutter       | 宫格项间距               | Number｜String | 0       | -                                                            |
| reverse      | 文字与图标反转，内容反转 | Boolean        | false   | true\|false                                                  |
| direction    | 格子内容排列的方向       | vertical       | 400     | horizontal（图左文右）｜ vertical（图上文下）｜textHorizontal （文左图右）｜ textVertical（文上图下） |
| square       | 是否保持正方形           | Boolean        | false   | true\|false                                                  |
| clickable    | 点击反馈                 | Boolean        | false   | true\|false                                                  |
| hoverGgColor | 按下的背景颜色           | String         | #EB4B4B | -                                                            |
| items        | 列表集合                 | Array          | -       | -                                                            |
| custom-style | 外部自定义样式           | Object         | -       | -                                                            |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/grid.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

| default | 自定义内嵌内容 | -    |
| ------- | -------------- | ---- |
|         |                |      |

#### [Grid Item Props](http://mid.chinatowercom.cn:18080/appGuide/ui/grid.html#grid-item-props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| width        | 宽度                                                         | Number\|String | 100%       | -                                                            |
| ------------ | ------------------------------------------------------------ | -------------- | ---------- | ------------------------------------------------------------ |
| icon         | 图标icon（支持本地图标/远程图片）                            | String         | -          | -                                                            |
| icon-prefix  | 图标类名前缀，等同于 [Icon](http://mid.chinatowercom.cn:18080/appGuide/ui/icon.html) 组件的 class-prefix 属性 | String         | cticon-    | -                                                            |
| icon-size    | 图标大小                                                     | Number\|String | 42rpx      | -                                                            |
| icon-color   | 图标颜色                                                     | String         | #000000    | -                                                            |
| label        | 文字内容                                                     | String         | -          | -                                                            |
| labelSize    | 文字大小                                                     | Number\|String | 14px       | -                                                            |
| labelColor   | 文本颜色                                                     | String         | -          | -                                                            |
| border       | 是否显示边框                                                 | Boolean        | false      | true\|false                                                  |
| center       | 内容居中                                                     | Boolean        | true       | true\|false                                                  |
| gutter       | 宫格项间距                                                   | Number｜String | 0          | -                                                            |
| reverse      | 文字与图标反转，内容反转                                     | Boolean        | false      | true\|false                                                  |
| direction    | 格子内容排列的方向                                           | vertical       | 400        | horizontal（图左文右）｜ vertical（图上文下）｜textHorizontal （文左图右）｜ textVertical（文上图下） |
| square       | 是否保持正方形                                               | Boolean        | false      | true\|false                                                  |
| clickable    | 点击反馈                                                     | Boolean        | false      | true\|false                                                  |
| dot          | 微标右上角小红点                                             | Boolean        | false      | true\|false                                                  |
| badge        | 微标内容                                                     | Number\|String | -          | -                                                            |
| url          | 跳转的地址                                                   | String         | -          | -                                                            |
| linkType     | 链接跳转类型                                                 | String         | navigateTo | navigateTo\|redirectTo\|switchTab\|reLaunch                  |
| hoverBgColor | 按下的背景颜色                                               | String         | #EB4B4B    | -                                                            |
| index        | 序号                                                         | Number         | 0          | -                                                            |
| custom-style | 外部自定义样式                                               | Object         | -          | -                                                            |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/grid.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| click | 点击单个宫格项事件 | 返回当前的index |
| ----- | ------------------ | --------------- |
|       |                    |                 |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/grid.html#slots-1)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

| default | 自定义内嵌内容 | -    |
| ------- | -------------- | ---- |
| icon    | 自定义图标内容 | -    |
| label   | 自定义文字内容 | -    |