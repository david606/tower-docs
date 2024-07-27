# [title 标题栏](http://mid.chinatowercom.cn:18080/appGuide/ui/title.html#title-标题栏)

该组件主要用于对列表进行单项选择或多项选择。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/title.html#基本使用)

- 通过`title`参数传入标题内容
- 通过`secondary`参数传入二级标题内容
- 通过`fixed`参数设置开启*fixed*定位固定在最前端
- 通过`placeholder`参数设置是否占位，该属性只有在设置*fixed*属性后才能生效

```vue
<template>
  <view class="demo">
    <ct-ui-title title="标题栏" secondary="二级标题描述" fixed placeholder />
    <view class="demo-page">
      <ct-demo-card title="取消固定最顶部">
        <ct-ui-title title="标题栏" secondary="二级标题描述" :fixed="false" />
      </ct-demo-card>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss"></style>
```

### [按钮设置](http://mid.chinatowercom.cn:18080/appGuide/ui/title.html#按钮设置)

- 通过`showBack`参数设置是否显示左侧返回按钮
- 通过`showEllipsis`参数设置是否显示右侧按钮

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="按钮设置">
      <ct-ui-title
        title="标题栏"
        :showBack="false"
        :fixed="false"
        :showEllipsis="false"
        placeholder
      />
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss"></style>
```

### [自定义 icon](http://mid.chinatowercom.cn:18080/appGuide/ui/title.html#自定义-icon)

- 通过`showBack`参数设置是否显示左侧返回按钮
- 通过`showEllipsis`参数设置是否显示右侧按钮

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义icon">
      <ct-ui-title
        title="标题栏"
        :fixed="false"
        :leftIcon="leftIcon"
        :rightIcon="rightIcon"
        placeholder
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      leftIcon: {
        type: 'icon',
        name: 'arrow-left',
        size: 24
      },
      rightIcon: {
        type: 'icon',
        name: 'share',
        size: 24,
        hot: true,
        transition: 360
      }
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [样式](http://mid.chinatowercom.cn:18080/appGuide/ui/title.html#样式)

- 通过`topColor`参数设置背景颜色
- 通过`border`参数设置*border-bottom*样式，通过**true**打开、**false**关闭，或直接传值设置
- 通过`leftIconStyle`参数设置左按钮样式
- 通过`rightIconStyle`参数设置右按钮样式

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="样式">
      <ct-ui-title
        title="标题栏"
        :fixed="false"
        topColor="rgba(235, 75, 75,.9)"
        border="6px solid #2a5caa"
        :leftIconStyle="style"
        :rightIconStyle="style"
        placeholder
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      style: {
        width: '20px',
        height: '20px'
      }
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [自定义 slot](http://mid.chinatowercom.cn:18080/appGuide/ui/title.html#自定义-slot)

通过设置插槽内容自行进行使用

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义slot">
         
      <ct-ui-title title="标题栏" placeholder :fixed="false">
        <template slot="left">
          <view class="demo-slot-left">left</view>
        </template>
        <template slot="content">
          <view class="demo-slot-content">content</view>
        </template>
        <template slot="right">
          <view class="demo-slot-right">right</view>
        </template>
      </ct-ui-title>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  .demo-slot-left,
  .demo-slot-right {
    text-align: center;
    padding: 0 26rpx;
  }
  .demo-slot-content {
    text-align: center;
    height: 100rpx;
    line-height: 100rpx;
    flex: 1;
  }
}
</style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/title.html#事件监听)

-`click`事件监听点击标题栏时触发 -`back`事件监听点击左侧返回按钮时触发 -`ellipsis`事件监听点击右侧按钮时触发

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="事件监听">
      <ct-ui-title
        title="标题栏"
        placeholder
        @click="click"
        @back="back"
        @ellipsis="ellipsis"
        :fixed="false"
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {}
  },
  methods: {
    click() {
      console.log('click')
    },
    back() {
      console.log('back')
    },
    ellipsis() {
      console.log('ellipsis')
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/title.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/title.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| *(必填)title   | 一级默认标题              | String                      | 标题                                         | -             |          |
| -------------- | ------------------------- | --------------------------- | -------------------------------------------- | ------------- | -------- |
| titleColor     | 标题颜色                  | String                      | #262F40                                      | -             | v1.0.20+ |
| titleSize      | 标题字体大小，单位rpx     | String \| Number            | 36                                           | -             | v1.0.20+ |
| secondary      | 二级标题                  | String                      |                                              | -             |          |
| secondaryColor | 二级标题颜色              | String                      | #9E9E9E                                      | -             | v1.0.20+ |
| secondarySize  | 二级标题字体大小，单位rpx | String \| Number            | 24                                           | -             | v1.0.20+ |
| fixed          | 开启fixed定位固定在最前端 | Boolean                     | true                                         | true \| false |          |
| placeholder    | 开始fixed时是否占位       | Boolean                     | false                                        | true \| false |          |
| showBack       | 是否显示左侧返回按钮      | Boolean                     | true                                         | true \| false |          |
| showEllipsis   | 是否显示右侧按钮          | Boolean                     | true                                         | true \| false |          |
| url            | 自定义返回地址            | String                      |                                              | -             |          |
| border         | 下边框                    | String \| Boolean \| Number | false                                        | -             |          |
| borderColor    | 边框颜色                  | String                      | -                                            | -             | v1.0.20+ |
| topColor       | 标题颜色                  | String                      | #F8F8F8                                      | -             |          |
| leftIcon       | 左Icon选择                | Object                      | {name: 'chevron-left', size: 24, hot: false} | -             |          |
| leftIconStyle  | 左Icon样式                | Object                      | []                                           | -             |          |
| rightIcon      | 右Icon选择                | Object                      | {}                                           | -             |          |
| rightIconStyle | 右Icon样式                | Object                      | []                                           | -             |          |
| leftText       | 左侧文字提示              | String                      | -                                            | -             | v1.0.20+ |
| leftTextColor  | 左侧文字提示颜色          | String                      | -                                            | #262F40       | v1.0.20+ |
| leftTextSize   | 左侧文字提示大小，单位rpx | String \| Number            | 32                                           | #262F40       | v1.0.20+ |
| rightText      | 右侧文字提示              | String                      | -                                            | -             | v1.0.20+ |
| rightTextColor | 右侧文字提示颜色          | String                      | -                                            | #262F40       | v1.0.20+ |
| rightTextSize  | 右侧文字提示大小，单位rpx | String \| Number            | 32                                           | #262F40       | v1.0.20+ |
| rightWidth     | 右侧宽度，单位rpx         | String \| Number            | 140                                          | -             | v1.0.30+ |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/title.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| click    | 点击事件               | -    |
| -------- | ---------------------- | ---- |
| back     | 点击左侧返回按钮时触发 | -    |
| ellipsis | 点击右侧更多按钮时触发 | -    |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/title.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

| left    | 左侧标题部分 | -    |
| ------- | ------------ | ---- |
| content | 中间内容部分 | -    |
| right   | 右侧标题部分 | -    |

### [leftIcon | rightIcon](http://mid.chinatowercom.cn:18080/appGuide/ui/title.html#lefticon-righticon)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/title.html#props-1)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| name  | type为icon时icon的名称或者远程url图片地址 | String         |       | -             |
| ----- | ----------------------------------------- | -------------- | ----- | ------------- |
| color | 字体图标颜色                              | String         |       | -             |
| size  | 字体图标大小                              | String\|Number |       | -             |
| hot   | 右上角小圆点                              | Boolean        | false | true \| false |
| info  | 右上角内容                                | String         | -     | -             |