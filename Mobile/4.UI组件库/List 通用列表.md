# [List 通用列表](http://mid.chinatowercom.cn:18080/appGuide/ui/list.html#list-通用列表)

该组件主要用于通用列表数据的展示。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/list.html#基本使用)

- 通过`title`参数设置列表标题
- 通过`content`参数设置内容

```vue
<template>
  <view class="demo">
    <view>
      <ct-demo-card title="基本使用">
        <ct-ui-list
          title="基本使用"
          content="一段很长很长的内容文字"
          rightText="右侧数据"
        >
        </ct-ui-list>
      </ct-demo-card>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {}
  },
  onLoad() {},
  methods: {}
}
</script>

<style lang="scss">
.demo {
  padding: 30rpx;
  padding-bottom: 100rpx;
  background: #ffffff;
}
</style>
```

### [修改排列方式](http://mid.chinatowercom.cn:18080/appGuide/ui/list.html#修改排列方式)

- 通过`direction`参数修改排列方式

```vue
<template>
  <view class="demo">
    <view>
      <ct-demo-card title="修改排列方式">
        <ct-ui-list
          title="修改排列方式"
          direction="column"
          content="一段很长很长的内容文字"
          rightText="右侧数据"
        >
        </ct-ui-list>
      </ct-demo-card>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {}
  },
  onLoad() {},
  methods: {}
}
</script>

<style lang="scss">
.demo {
  padding: 30rpx;
  padding-bottom: 100rpx;
  background: #ffffff;
}
</style>
```

### [修改标题溢出显示](http://mid.chinatowercom.cn:18080/appGuide/ui/list.html#修改标题溢出显示)

- 通过`ellipsis`参数修改标题溢出显示

```vue
<template>
  <view class="demo">
    <view>
      <ct-demo-card title="标题溢出显示">
        <ct-ui-list
          title="标题溢出显示标题溢出显示标题溢出显示标题溢出显示标题溢出显示标题溢出显示标题溢出显示标题溢出显示标题溢出显示标题溢出显示"
          content="一段很长很长的内容文字"
          ellipsis="0"
        >
        </ct-ui-list>
        <ct-ui-list
          title="标题溢出显示标题溢出显示标题溢出显示标题溢出显示标题溢出显示标题溢出显示标题溢出显示标题溢出显示标题溢出显示标题溢出显示"
          content="一段很长很长的内容文字"
          ellipsis="1"
        >
        </ct-ui-list>
        <ct-ui-list
          title="标题溢出显示标题溢出显示标题溢出显示标题溢出显示标题溢出显示标题溢出显示标题溢出显示标题溢出显示标题溢出显示标题溢出显示"
          content="一段很长很长的内容文字"
          ellipsis="2"
        >
        </ct-ui-list>
      </ct-demo-card>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {}
  },
  onLoad() {},
  methods: {}
}
</script>

<style lang="scss">
.demo {
  padding: 30rpx;
  padding-bottom: 100rpx;
  background: #ffffff;
}
</style>
```

### [禁用显示](http://mid.chinatowercom.cn:18080/appGuide/ui/list.html#禁用显示)

- 通过`disabled`参数设置是否禁用

```vue
<template>
  <view class="demo">
    <view>
      <ct-demo-card title="禁用显示">
        <ct-ui-list
          title="禁用"
          content="一段很长很长的内容文字"
          :disabled="true"
        >
        </ct-ui-list>
      </ct-demo-card>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {}
  },
  onLoad() {},
  methods: {}
}
</script>

<style lang="scss">
.demo {
  padding: 30rpx;
  padding-bottom: 100rpx;
  background: #ffffff;
}
</style>
```

### [右侧带箭头](http://mid.chinatowercom.cn:18080/appGuide/ui/list.html#右侧带箭头)

- 通过`showArrow`参数设置是否右侧带箭头
- 通过`link`参数点击跳转方式自动添加箭头

```vue
<template>
  <view class="demo">
    <view>
      <ct-demo-card title="右侧带箭头">
        <ct-ui-list
          title="右侧带箭头"
          content="一段很长很长的内容文字"
          :showArrow="true"
        >
        </ct-ui-list>
        <ct-ui-list
          title="右侧带箭头"
          content="一段很长很长的内容文字"
          link="navigateTo"
        >
        </ct-ui-list>
      </ct-demo-card>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {}
  },
  onLoad() {},
  methods: {}
}
</script>

<style lang="scss">
.demo {
  padding: 30rpx;
  padding-bottom: 100rpx;
  background: #ffffff;
}
</style>
```

### [左侧显示缩略图](http://mid.chinatowercom.cn:18080/appGuide/ui/list.html#左侧显示缩略图)

- 通过`imgUrl`参数设置缩略图地址
- 通过`thumbSize`参数设置缩略图尺寸
- 通过`avatarCircle`参数设置缩略图是否为圆角

```vue
<template>
  <view class="demo">
    <view>
      <ct-demo-card title="左侧缩略图">
        <ct-ui-list
          title="左侧缩略图"
          content="一段很长很长的内容文字"
          imgUrl="../../static/images/ct_list_icon.png"
          thumbSize="lg"
        >
        </ct-ui-list>
        <ct-ui-list
          title="左侧缩略图"
          content="一段很长很长的内容文字"
          imgUrl="../../static/images/ct_list_icon.png"
          thumbSize="medium"
        >
        </ct-ui-list>
        <ct-ui-list
          title="左侧圆角缩略图"
          content="一段很长很长的内容文字"
          imgUrl="../../static/logo.png"
          :avatarCircle="true"
        >
        </ct-ui-list>
      </ct-demo-card>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {}
  },
  onLoad() {},
  methods: {}
}
</script>

<style lang="scss">
.demo {
  padding: 30rpx;
  padding-bottom: 100rpx;
  background: #ffffff;
}
</style>
```

### [左侧显示扩展图标](http://mid.chinatowercom.cn:18080/appGuide/ui/list.html#左侧显示扩展图标)

- 通过`showExtraIcon`参数设置是否显示扩展图标
- 通过`extraIcon`参数设置扩展图标样式

```vue
<template>
  <view class="demo">
    <view>
      <ct-demo-card title="左侧缩略图">
        <ct-ui-list
          title="左侧扩展图标"
          content="一段很长很长的内容文字"
          :showExtraIcon="true"
          :extraIcon="{
            color: '#000000',
            size: '30rpx',
            name: 'homefill'
          }"
        ></ct-ui-list>
      </ct-demo-card>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {}
  },
  onLoad() {},
  methods: {}
}
</script>

<style lang="scss">
.demo {
  padding: 30rpx;
  padding-bottom: 100rpx;
  background: #ffffff;
}
</style>
```

### [显示数字角标](http://mid.chinatowercom.cn:18080/appGuide/ui/list.html#显示数字角标)

- 通过`showHeadBadge`参数设置是否显示图标上的数字角标
- 通过`headBadgeAttribute`参数设置图标上的数字角标样式
- 通过`showBadge`参数设置是否显示右侧数字角标
- 通过`badgeAttribute`参数设置是否显示右侧数字角标样式

```vue
<template>
  <view class="demo">
    <view>
      <ct-demo-card title="左侧缩略图">
        <ct-ui-list
          title="数字角标"
          content="一段很长很长的内容文字"
          imgUrl="../../static/logo.png"
          thumbSize="lg"
          :showHeadBadge="true"
          :headBadgeAttribute="{
            isDot: false,
            max: '99',
            content: '7',
            show: true
          }"
        ></ct-ui-list>
        <ct-ui-list
          title="数字角标"
          content="一段很长很长的内容文字"
          imgUrl="../../static/logo.png"
          thumbSize="lg"
          :showBadge="true"
          :badgeAttribute="{
            isDot: false,
            max: '99',
            content: '7',
            show: true
          }"
        ></ct-ui-list>
        <ct-ui-list
          title="数字角标"
          content="一段很长很长的内容文字"
          imgUrl="../../static/logo.png"
          thumbSize="lg"
          :showHeadBadge="true"
        ></ct-ui-list>
      </ct-demo-card>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {}
  },
  onLoad() {},
  methods: {}
}
</script>

<style lang="scss">
.demo {
  padding: 30rpx;
  padding-bottom: 100rpx;
  background: #ffffff;
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/list.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/list.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| iconUrl            | icon路径                                                     | string           | —                                             | —                                                    | 1.0.29+已弃用          |
| ------------------ | ------------------------------------------------------------ | ---------------- | --------------------------------------------- | ---------------------------------------------------- | ---------------------- |
| title              | 标题                                                         | string           | —                                             | —                                                    |                        |
| content            | 内容                                                         | string           | —                                             | —                                                    |                        |
| arrow              | 右侧箭头                                                     | Boolean          | false                                         | true:显示，false:隐藏                                | 1.0.29+替换为showArrow |
| stateObj           | 右侧状态数据                                                 | Object           | —                                             | —                                                    | 1.0.29+已弃用          |
| imageType          | icon类型                                                     | string           | default                                       | default:图片与标题和内容并列，small:图片与标题并列   | 1.0.29+已弃用          |
| cornerRadius       | icon圆角                                                     | Number           | 45                                            | 0~45,单位rpx(当imageType为small时,该属性不生效)      | 1.0.29+已弃用          |
| direction          | 内容部分排列方式                                             | string           | row                                           | row \| column                                        | 1.0.29+                |
| ellipsis           | title 是否溢出隐藏，可选值，0:默认全部显示; 1:显示一行; 2:显示两行; | String \| Number | 0                                             | -                                                    | 1.0.29+                |
| disabled           | 是否禁用                                                     | Boolean          | false                                         | -                                                    | 1.0.29+                |
| showArrow          | 是否显示箭头图标                                             | Boolean          | false                                         | -                                                    | 1.0.29+                |
| clickable          | 是否开启点击反馈                                             | Boolean          | false                                         | -                                                    | 1.0.29+                |
| link               | 新页面跳转方式                                               | String           |                                               | switchTab	\| reLaunch \| redirectTo \| navigateTo | 1.0.29+                |
| to                 | 链接跳转路径                                                 | String           |                                               |                                                      | 1.0.29+                |
| showHeadBadge      | 是否显示头像数字角标                                         | Boolean          | false                                         |                                                      | 1.0.29+                |
| headBadgeAttribute | 头像数字角标样式                                             | Object           | {}                                            |                                                      | 1.0.29+                |
| showBadge          | 是否显示右侧数字角标                                         | Boolean          | false                                         |                                                      | 1.0.29+                |
| badgeAttribute     | 右侧数字角标样式                                             | Object           | {}                                            |                                                      | 1.0.29+                |
| rightText          | 右侧文字内容                                                 | String           |                                               |                                                      | 1.0.29+                |
| imgUrl             | 左侧缩略图地址                                               | String           |                                               |                                                      | 1.0.29+                |
| thumbSize          | 缩略图尺寸                                                   | String           | medium                                        | lg:大图 \| medium:一般 \| sm:小图                    | 1.0.29+                |
| avatarCircle       | 是否显示圆角图片(缩略图生效)                                 | Boolean          | false                                         |                                                      | 1.0.29+                |
| showExtraIcon      | 左侧是否显示扩展图标（不显示缩略图时生效）                   | Boolean          | false                                         |                                                      | 1.0.29+                |
| extraIcon          | 左侧是否显示扩展图标（不显示缩略图时生效）                   | Object           | { color: '#000000', size: '30rpx', name: '' } |                                                      | 1.0.29+                |
| border             | 是否显示边框                                                 | Boolean          | false                                         |                                                      | 1.0.29+                |
| customStyle        | 自定义样式                                                   | Object           | {}                                            |                                                      | 1.0.29+                |

#### [stateObj 说明:](http://mid.chinatowercom.cn:18080/appGuide/ui/list.html#stateobj-说明)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| state   | 标签显示文字 | string | —    | —    | 1.0.29+已弃用 |
| ------- | ------------ | ------ | ---- | ---- | ------------- |
| bgColor | 标签背景颜色 | string | —    | —    | 1.0.29+已弃用 |
| color   | 标签字体颜色 | string | —    | —    | 1.0.29+已弃用 |