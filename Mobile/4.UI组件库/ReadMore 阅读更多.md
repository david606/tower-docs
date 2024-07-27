# [ReadMore 阅读更多](http://mid.chinatowercom.cn:18080/appGuide/ui/readMore.html#readmore-阅读更多)

该该组件一般用于内容较长，预先收起一部分，点击展开全部内容的场景。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/readMore.html#基本使用)

- 通过`slot` 自定义内容
- 通过`position` 设置展开/收起的按钮位置
- 通过`openText`、`closeText`、`size`、`color` 参数设置展开/收起文字内容、大小、颜色等
- 通过`openIcon`、`closeIcon`、`iconSize`、`iconColor` 参数设置展开/收起 icon、大小、颜色等
- 通过`transition`设置是否启动动画
- 通过`shadowStyle`参数设置阴影样式（*只有在 position 为 bottom 有效*）

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
       
      <ct-ui-read-more>
        <rich-text :nodes="content"></rich-text>
      </ct-ui-read-more>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ReadMore',
  data() {
    return {
      content:
        '1月15日，中国铁塔党委召开党史学习教育总结会议，认真学习贯彻落实习近平总书记重要指示和中央党史学习教育总结会议精神,对公司党史学习教育进行全面总结，对巩固拓展党史学习教育成果作出部署。中央企业党史学习教育第四指导组副组长王学军出席会议并讲话。中国铁塔党委书记、董事长、党史学习教育领导小组组长张志勇作党史学习教育总结讲话，党委副书记、总经理、党史学习教育领导小组副组长顾晓敏主持会议，公司领导班子成员出席会议。'
    }
  }
}
</script>

<style lang="scss" scoped></style>
```

### [自定义图标，展开/收起句尾](http://mid.chinatowercom.cn:18080/appGuide/ui/readMore.html#自定义图标-展开-收起句尾)

通过`position`设置展开/收起显示的位置，`showIcon`设置是否显示 icon，`openIcon` `closeIcon`设置展开/收起的图标。**句尾只能使用文本内容，否则无效**

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义图标，展开/收起句尾">
       
      <ct-ui-read-more
        show-icon
        open-icon="chevrons-down"
        close-icon="chevrons-up"
        position="textend"
      >
        {{ content }}
      </ct-ui-read-more>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ReadMore',
  props: {},
  data() {
    return {
      content:
        '1月15日，中国铁塔党委召开党史学习教育总结会议，认真学习贯彻落实习近平总书记重要指示和中央党史学习教育总结会议精神,对公司党史学习教育进行全面总结，对巩固拓展党史学习教育成果作出部署。中央企业党史学习教育第四指导组副组长王学军出席会议并讲话。中国铁塔党委书记、董事长、党史学习教育领导小组组长张志勇作党史学习教育总结讲话，党委副书记、总经理、党史学习教育领导小组副组长顾晓敏主持会议，公司领导班子成员出席会议。'
    }
  }
}
</script>
<style lang="scss" scoped></style>
```

### [展开/收起句尾，只有自定义图标](http://mid.chinatowercom.cn:18080/appGuide/ui/readMore.html#展开-收起句尾-只有自定义图标)

通过`position`设置展开/收起显示的位置，`showIcon`设置是否显示 icon，`openIcon` `closeIcon`设置展开/收起的图标，`openText` `closeText`设置展开/收起的文字

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="展开/收起句尾，只有自定义图标">
      <ct-ui-read-more
        show-icon
        open-text=""
        close-text=""
        open-icon="chevrons-right"
        close-icon="chevrons-up"
        position="textend"
      >
        {{ content }}
      </ct-ui-read-more>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ReadMore',
  props: {},
  data() {
    return {
      content:
        '1月15日，中国铁塔党委召开党史学习教育总结会议，认真学习贯彻落实习近平总书记重要指示和中央党史学习教育总结会议精神,对公司党史学习教育进行全面总结，对巩固拓展党史学习教育成果作出部署。中央企业党史学习教育第四指导组副组长王学军出席会议并讲话。中国铁塔党委书记、董事长、党史学习教育领导小组组长张志勇作党史学习教育总结讲话，党委副书记、总经理、党史学习教育领导小组副组长顾晓敏主持会议，公司领导班子成员出席会议。'
    }
  }
}
</script>
<style lang="scss" scoped></style>
```

### [展开/收起句尾，只有自定义图标+展开/收起背景色](http://mid.chinatowercom.cn:18080/appGuide/ui/readMore.html#展开-收起句尾-只有自定义图标-展开-收起背景色)

通过`position`设置展开/收起显示的位置，`showIcon`设置是否显示 icon，`openIcon` `closeIcon`设置展开/收起的图标，`openText` `closeText`设置展开/收起的文字，`bgColor` `color` 设置按钮背景色及文字颜色

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="展开/收起句尾，只有自定义图标">
       
      <ct-ui-read-more
        show-icon
        open-text=""
        close-text=""
        open-icon="chevrons-right"
        close-icon="chevrons-up"
        position="textend"
        bgColor="#EB4B4B"
        color="#ffffff"
      >
        {{ content }}
      </ct-ui-read-more>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ReadMore',
  props: {},
  data() {
    return {
      content:
        '1月15日，中国铁塔党委召开党史学习教育总结会议，认真学习贯彻落实习近平总书记重要指示和中央党史学习教育总结会议精神,对公司党史学习教育进行全面总结，对巩固拓展党史学习教育成果作出部署。中央企业党史学习教育第四指导组副组长王学军出席会议并讲话。中国铁塔党委书记、董事长、党史学习教育领导小组组长张志勇作党史学习教育总结讲话，党委副书记、总经理、党史学习教育领导小组副组长顾晓敏主持会议，公司领导班子成员出席会议。'
    }
  }
}
</script>
<style lang="scss" scoped></style>
```

### [自定义展开/收起背景色](http://mid.chinatowercom.cn:18080/appGuide/ui/readMore.html#自定义展开-收起背景色)

通过`bgColor` `color` 设置按钮背景色及文字颜色

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义展开/收起背景色">
       
      <ct-ui-read-more bgColor="#EB4B4B" color="#ffffff">
        <rich-text :nodes="content"></rich-text>
      </ct-ui-read-more>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ReadMore',
  props: {},
  data() {
    return {
      content:
        '1月15日，中国铁塔党委召开党史学习教育总结会议，认真学习贯彻落实习近平总书记重要指示和中央党史学习教育总结会议精神,对公司党史学习教育进行全面总结，对巩固拓展党史学习教育成果作出部署。中央企业党史学习教育第四指导组副组长王学军出席会议并讲话。中国铁塔党委书记、董事长、党史学习教育领导小组组长张志勇作党史学习教育总结讲话，党委副书记、总经理、党史学习教育领导小组副组长顾晓敏主持会议，公司领导班子成员出席会议。'
    }
  }
}
</script>
<style lang="scss" scoped></style>
```

### [自定义设置 Icon](http://mid.chinatowercom.cn:18080/appGuide/ui/readMore.html#自定义设置-icon)

通过绑定`openIcon` `closeIcon`进行设置 Icon，支持 icon 图标及 http 图标地址

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义设置Icon">
       
      <ct-ui-read-more
        show-icon
        open-icon="chevrons-down"
        close-icon="chevrons-up"
      >
        <rich-text :nodes="content"></rich-text>
      </ct-ui-read-more>
       
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  name: 'ReadMore',
  props: {},
  data() {
    return {
      content:
        '1月15日，中国铁塔党委召开党史学习教育总结会议，认真学习贯彻落实习近平总书记重要指示和中央党史学习教育总结会议精神,对公司党史学习教育进行全面总结，对巩固拓展党史学习教育成果作出部署。中央企业党史学习教育第四指导组副组长王学军出席会议并讲话。中国铁塔党委书记、董事长、党史学习教育领导小组组长张志勇作党史学习教育总结讲话，党委副书记、总经理、党史学习教育领导小组副组长顾晓敏主持会议，公司领导班子成员出席会议。'
    }
  }
}
</script>

<style lang="scss" scoped></style>
```

### [自定义样式](http://mid.chinatowercom.cn:18080/appGuide/ui/readMore.html#自定义样式)

此组件上边部分有一个白色虚化的阴影，用以将点击区域与文字内容进行融合，如果您不想要这个阴影，可以调整 shadowStyle 对象，此对象内部如下：

```json
{
  // #ifndef APP-NVUE
  "backgroundImage": "linear-gradient(-180deg, rgba(255, 255, 255, 0) 0%, #fff 80%)",
  // #endif
  // #ifdef APP-NVUE
  // nvue上不支持设置复杂的backgroundImage属性
  "backgroundImage": "linear-gradient(to top, #fff, rgba(255, 255, 255, 0.5))",
  // #endif
  "paddingTop": "250rpx",
  "marginTop": "-250rpx"
}
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/readMore.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/readMore.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| position     | 展开/收起位置                                | String         | bottom       | bottom｜textend |
| ------------ | -------------------------------------------- | -------------- | ------------ | --------------- |
| contentColor | 文本内容颜色                                 | String         | -            | -               |
| openText     | 展开文字                                     | String         | 展开阅读全文 | -               |
| closeText    | 收起文字                                     | String         | 收起         | -               |
| size         | 展开/收起文字大小                            | String｜Number | -            | -               |
| color        | 展开/收起颜色                                | String         | #EB4B4B      | -               |
| showIcon     | 是否显示展开/收起图标                        | Boolean        | false        | true\|false     |
| openIcon     | 展开图标，支持网络图标及本地icon             | String         | -            | -               |
| closeIcon    | 收起图标，支持网络图标及本地icon             | String         | -            | -               |
| iconSize     | icon 大小                                    | String         | -            | -               |
| iconColor    | icon 颜色，未设置，则与text的颜色一致        | String         | -            | -               |
| toggle       | 展开后是否显示收起按钮                       | Boolean        | true         | true｜false     |
| showHeight   | 内容超出此高度才会显示展开全文按钮，单位px   | String｜Number | 180          | -               |
| bgColor      | 按钮背景颜色，如果设置，则会出现椭圆形的按钮 | String         | -            | -               |
| transition   | 过渡动画时间（ms)                            | String｜Number | 500          | -               |
| shadowStyle  | 自定义阴影样式                               | String｜Number | 见自定义样式 | -               |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/readMore.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| open  | 内容被展开时触发 | -    |
| ----- | ---------------- | ---- |
| close | 内容被收起时触发 | -    |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/readMore.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

| default | 自定义文字内容          | -    |
| ------- | ----------------------- | ---- |
| toggle  | 自定义展开/收起按钮内容 | -    |