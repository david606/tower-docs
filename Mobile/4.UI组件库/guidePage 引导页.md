# [guidePage 引导页](http://mid.chinatowercom.cn:18080/appGuide/ui/guidePage.html#guidepage-引导页)

该组件主要用于首次加载应用时或应用版本更新出现，对用户进行指导性展示使用。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/guidePage.html#基本使用)

- 通过`list`参数传入需要展示的滑动引导图，支持静态图、gif 图
- 通过`pagination`参数设置是否显示面板分页器指示点
- 通过`indicatorColor`参数设置指示点颜色
- 通过`activeColor`参数设置当前指示点颜色

```vue
<template>
  <view class="demo">
    <view class="title">基本使用</view>
    <ct-ui-guide-page
      ref="guidePage"
      :list="list"
      :pagination="pagination"
      :indicatorColor="indicatorColor"
      :activeColor="activeColor"
    ></ct-ui-guide-page>
  </view>
</template>

<script>
export default {
  name: 'guidePage',
  data() {
    return {
      list: [
        {id: 111, src: '/static/images/ct_guide1.png'},
        {id: 222, src: '/static/images/ct_guide2.png'},
        {id: 333, src: '/static/images/ct_guide1.png'},
        {id: 444, src: '/static/images/ct_guide2.png'}
      ],
      pagination: true,
      indicatorColor: '#EB4B4B80',
      activeColor: '#EB4B4BFF'
    }
  }
}
</script>

<style scoped lang="scss">
.demo {
  padding: 20px;

  .title {
    margin: 20px 0;
  }
}
</style>
```

### [设置引导图片数量](http://mid.chinatowercom.cn:18080/appGuide/ui/guidePage.html#设置引导图片数量)

通过`amount`参数设置展示的引导图片数量，通过`buttonFlag`设置按钮根据下标在第几页显示出来，不传默认最后一页

```vue
<template>
  <view class="demo">
    <view class="title">设置引导图片数量</view>
    <ct-ui-guide-page
      ref="guidePage"
      :list="list"
      :amount="amount"
      :buttonFlag="buttonFlag"
      :pagination="pagination"
    ></ct-ui-guide-page>
  </view>
</template>

<script>
export default {
  name: 'guidePage',
  data() {
    return {
      list: [
        {id: 111, src: '/static/images/ct_guide1.png'},
        {id: 222, src: '/static/images/ct_guide2.png'},
        {id: 333, src: '/static/images/ct_guide1.png'},
        {id: 444, src: '/static/images/ct_guide2.png'}
      ],
      pagination: true,
      amount: 3,
      buttonFlag: 1
    }
  }
}
</script>

<style scoped lang="scss">
.demo {
  padding: 20px;

  .title {
    margin: 20px 0;
  }
}
</style>
```

### [自定义样式](http://mid.chinatowercom.cn:18080/appGuide/ui/guidePage.html#自定义样式)

通过`buttonContent`属性设置传入按钮文字，通过`customStyle`属性设置按钮样式,通过`dotStyle`属性设置分页器指示点样式,通过`activeStyle`属性设置当前指示点样式

```vue
<template>
  <view class="demo">
    <view class="title">自定义样式</view>
    <ct-ui-guide-page
      ref="guidePage"
      :list="list"
      :buttonContent="buttonContent"
      :customStyle="customStyle"
      :dotStyle="dotStyle"
      :activeStyle="activeStyle"
      :pagination="pagination"
    ></ct-ui-guide-page>
  </view>
</template>

<script>
export default {
  name: 'guidePage',
  data() {
    return {
      list: [
        {id: 111, src: '/static/images/ct_guide1.png'},
        {id: 222, src: '/static/images/ct_guide2.png'}
      ],
      pagination: true,
      buttonContent: '自定义文本',
      customStyle: {
        backgroundColor: '#EB4B4BFF',
        color: '#fff'
      },
      dotStyle: {
        backgroundColor: '#ff5500'
      },
      activeStyle: {
        width: '40rpx',
        height: '40rpx',
        borderRadius: '50%',
        backgroundColor: '#4adede'
      }
    }
  }
}
</script>

<style scoped lang="scss">
.demo {
  padding: 20px;

  .title {
    margin: 20px 0;
  }
}
</style>
```

### [滑动方式](http://mid.chinatowercom.cn:18080/appGuide/ui/guidePage.html#滑动方式)

通过`vertical`参数设置引导页是否采用纵向垂直滑动，通过`duration`参数设置引导页的滑动时长，单位 ms

```vue
<template>
  <view class="demo">
    <view class="title">设置引导图片数量</view>
    <ct-ui-guide-page
      ref="guidePage"
      :list="list"
      :vertical="vertical"
      :duration="duration"
      :pagination="pagination"
    ></ct-ui-guide-page>
  </view>
</template>

<script>
export default {
  name: 'guidePage',
  data() {
    return {
      list: [
        {id: 111, src: '/static/images/ct_guide1.png'},
        {id: 222, src: '/static/images/ct_guide2.png'},
        {id: 333, src: '/static/images/ct_guide1.png'},
        {id: 444, src: '/static/images/ct_guide2.png'}
      ],
      pagination: true,
      vertical: true,
      duration: 600
    }
  }
}
</script>

<style scoped lang="scss">
.demo {
  padding: 20px;

  .title {
    margin: 20px 0;
  }
}
</style>
```

### [手动控制打开关闭](http://mid.chinatowercom.cn:18080/appGuide/ui/guidePage.html#手动控制打开关闭)

通过绑定`ref`进行手动控制 **打开、关闭**，通过`open`打开引导页，通过`experience`事件关闭引导页

```vue
<template>
  <view class="demo">
    <view class="title">手动控制打开关闭</view>
    <ct-ui-guide-page
      ref="guidePage"
      :list="list"
      :pagination="pagination"
    ></ct-ui-guide-page>
    <view class="demo-row">
      <view class="demo-row-title">打开引导页</view>
      <view class="demo-row-btn" @click="open">点击打开</view>
    </view>
    <view class="demo-row">
      <view class="demo-row-title">关闭引导页</view>
      <view class="demo-row-btn" @click="experience">点击关闭</view>
    </view>
  </view>
</template>

<script>
export default {
  name: 'guidePage',
  data() {
    return {
      list: [
        {id: 111, src: '/static/images/ct_guide1.png'},
        {id: 222, src: '/static/images/ct_guide2.png'}
      ],
      pagination: true
    }
  },
  methods: {
    open() {
      this.$refs.guidePage.open()
    },
    experience() {
      this.$refs.guidePage.experience()
    }
  }
}
</script>

<style scoped lang="scss">
.demo {
  padding: 20px;

  .title {
    margin: 20px 0;
  }
}
</style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/guidePage.html#事件监听)

`getInto`事件可以监听进入按钮事件

```vue
<template>
  <view class="demo">
    <view class="title">事件监听</view>
    <ct-ui-guide-page
      ref="guidePage"
      :list="list"
      :pagination="pagination"
      @getInto="getInto"
    ></ct-ui-guide-page>
  </view>
</template>

<script>
export default {
  name: 'guidePage',
  data() {
    return {
      list: [
        {id: 111, src: '/static/images/ct_guide1.png'},
        {id: 222, src: '/static/images/ct_guide2.png'}
      ],
      pagination: true
    }
  },
  methods: {
    getInto() {
      console.log('点击按钮进入')
    }
  }
}
</script>

<style scoped lang="scss">
.demo {
  padding: 20px;

  .title {
    margin: 20px 0;
  }
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/guidePage.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/guidePage.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| list           | 引导页图片数组                             | Array   | []        | -          |
| -------------- | ------------------------------------------ | ------- | --------- | ---------- |
| amount         | 设置展示引导图片数量，默认全部展示         | Number  | 0         | -          |
| pagination     | 是否显示面板指示点                         | Boolean | true      | true/false |
| indicatorColor | 指示点颜色                                 | String  | #EB4B4B80 | -          |
| activeColor    | 当前指示点颜色                             | String  | #EB4B4BFF | -          |
| closeTime      | 广告自动关闭所需时间,单位ms                | Number  | 4000      | -          |
| dotStyle       | 指示点样式                                 | Object  | {}        | -          |
| activeStyle    | 当前指示点样式                             | Object  | {}        | -          |
| vertical       | 是否采用纵向滑动                           | Boolean | false     | true/false |
| duration       | 滑动动画时长，单位ms                       | Number  | 500       | -          |
| buttonContent  | 按钮文字                                   | String  | #FFFFFF8C | -          |
| activeColor    | 当前选中的指示点颜色                       | String  | 立即体验  | -          |
| customStyle    | 按钮样式                                   | Object  | {}        | -          |
| buttonFlag     | 按钮根据下标在第几页显示出来，默认最后一页 | Number  | 0         | -          |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/guidePage.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| getInto | 点击立即体验按钮时触发 | -    |
| ------- | ---------------------- | ---- |
|         |                        |      |

#### [Methods](http://mid.chinatowercom.cn:18080/appGuide/ui/guidePage.html#methods)

| 名称 | 说明 |
| ---- | ---- |
|      |      |

| open       | 打开引导页事件 |
| ---------- | -------------- |
| experience | 关闭引导页事件 |