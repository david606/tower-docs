# [Mylist 个人中心](http://mid.chinatowercom.cn:18080/appGuide/ui/mylist.html#mylist-个人中心)

该组件主要用于通用列表数据的展示。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/mylist.html#基本使用)

- 通过`title`参数设置标题
- 通过`titleStyle`参数设置标题样式
- 通过`desc`参数设置描述信息(二级标题)
- 通过`descStyle`描述信息样式
- 通过`height`参数设置 item 整行高度，单位是 rpx
- 通过`border`参数设置是否显示下边框
- 通过`padding`参数设置 item 整行内边距。字符串格式以数字+','形式隔开，例：'12,16'。单位是 rpx
- 通过`showRightIcon`参数设置是否显示右侧图标
- 通过`rightIcon`参数设置右侧图标
- 通过`leftIcon`参数设置左侧图标

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="单行标题">
      <ct-ui-mylist title="单行标题1" @click="click"></ct-ui-mylist>
    </ct-demo-card>
    <ct-demo-card title="设置描述信息与样式">
      <ct-ui-mylist
        title="多行标题1"
        desc="峰会上看见技返回空"
        :height="70"
        :titleStyle="titleStyle"
      ></ct-ui-mylist>
    </ct-demo-card>
    <ct-demo-card title="自定义右侧图标">
      <ct-ui-mylist
        title="单行标题2"
        :padding="padding"
        :rightIcon="rightIcon"
      ></ct-ui-mylist>
    </ct-demo-card>
    <ct-demo-card title="自定义左侧图标">
      <ct-ui-mylist
        title="单行标题3"
        :border="false"
        :leftIcon="leftIcon"
      ></ct-ui-mylist>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      titleStyle: {color: '#ee0a24', borderRadius: '10rpx'},
      padding: [12, 5, 8],
      rightIcon: {name: 'chevrons-right', color: '#ee0a24'},
      leftIcon: {name: 'star-fill', color: '#3cfffb'}
    }
  },
  methods: {
    click(e) {
      console.log(e)
    }
  }
}
</script>

<style lang="scss"></style>
```

### [右侧扩展内容](http://mid.chinatowercom.cn:18080/appGuide/ui/mylist.html#右侧扩展内容)

- 通过`extraType`参数设置右侧扩展类型
- 通过`extraStyle`参数设置右侧扩展属性

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义右侧扩展内容text类型">
      <ct-ui-mylist
        title="单行标题4"
        extraType="text"
        :extraStyle="extraStyle1"
      ></ct-ui-mylist>
    </ct-demo-card>
    <ct-demo-card title="自定义右侧扩展内容badge类型">
      <ct-ui-mylist
        title="多行标题5"
        desc="badge类型"
        extraType="badge"
        :extraStyle="extraStyle2"
      ></ct-ui-mylist>
    </ct-demo-card>
    <ct-demo-card title="自定义右侧扩展内容tag类型">
      <ct-ui-mylist
        title="单行标题6"
        extraType="tag"
        :extraStyle="extraStyle3"
      ></ct-ui-mylist>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      extraStyle1: {
        content: 'text类型',
        size: 14,
        type: 'primary',
        mode: 'text'
      },
      extraStyle2: {
        content: 123,
        type: 'success',
        isDot: false,
        max: 99
      },
      extraStyle3: {
        type: 'danger',
        icon: 'edit',
        text: 'tag类型'
      }
    }
  }
}
</script>

<style lang="scss"></style>
```

### [自定义插槽](http://mid.chinatowercom.cn:18080/appGuide/ui/mylist.html#自定义插槽)

- 通过`left`参数设置左侧插槽。若同时设置了`leftIcon`属性，则`leftIcon`不生效
- 通过`right`参数设置右侧扩展属性。若同时设置了`extraType`属性，则`extraType`不生效，右侧扩展会被右侧插槽覆盖
- 通过默认插槽（`default`）自定义设置标题及描述信息内容

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义插槽">
      <ct-ui-mylist title="单行标题7">
        <template v-slot:left>
          <view class="left">
            <ct-ui-button
              :customStyle="customStyle"
              data-name="custom"
              style="font-size: 14px;"
              >左侧插槽</ct-ui-button
            >
          </view>
        </template>
        <view class="content">
          单行标题
          <ct-ui-rate v-model="rate" notColor="#909399" :size="16"></ct-ui-rate>
        </view>
        <template v-slot:right>
          <ct-ui-switch v-model="swit" type="primary"></ct-ui-switch>
        </template>
      </ct-ui-mylist>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      customStyle: {
        width: '120rpx',
        height: '40rpx',
        marginRight: '20rpx',
        fontSize: '14px'
      },
      rate: 2,
      swit: true
    }
  }
}
</script>

<style lang="scss">
.left {
  display: flex;
  flex-direction: row;
  align-items: center;
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/mylist.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/mylist.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| height        | item整行高度           | Number \| String          | —                                                       | —              |
| ------------- | ---------------------- | ------------------------- | ------------------------------------------------------- | -------------- |
| title         | 标题内容               | String                    | —                                                       | —              |
| titleStyle    | 标题样式               | Object                    | {color: 'black', fontSize: '28rpx', fontWeight: 'bold'} | —              |
| desc          | 描述信息(二级标题)内容 | String                    | —                                                       | —              |
| descStyle     | 描述信息样式           | Object                    | {color: '#969799', fontSize: '24rpx'}                   | —              |
| extraType     | 右侧扩展类型           | String                    | —                                                       | text/badge/tag |
| extraStyle    | 右侧扩展属性           | Object                    | —                                                       | —              |
| border        | 是否显示下边框         | Boolean                   | true                                                    | true/false     |
| padding       | item内边距             | String \| Array \| Number | 12px 16px                                               | —              |
| showRightIcon | 是否显示右侧图标       | Boolean                   | true                                                    | true/false     |
| rightIcon     | 右侧图标属性           | Object                    | —                                                       | —              |
| leftIcon      | 左侧图标属性           | Object                    | —                                                       | —              |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/mylist.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| click | 点击事件 | 点击的item元素 |
| ----- | -------- | -------------- |
|       |          |                |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/mylist.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

| left    | 自定义左侧部分的内容     | —    |
| ------- | ------------------------ | ---- |
| default | 自定义标题和描述信息内容 | —    |
| right   | 自定义右侧扩展内容       | —    |