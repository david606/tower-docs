# [LoadingIcon 加载动画](http://mid.chinatowercom.cn:18080/appGuide/ui/loadingIcon.html#loadingicon-加载动画)

该组件主要对资源加载未完成时起到过渡效果的加载动画。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/loadingIcon.html#基本使用)

- 通过`shapeType`参数选择的加载动画类型

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
       
      <view class="lodingBox">
        <view>
          <view>cycle</view>
          <ct-ui-loading-icon ref="loadingIcon" shapeType="cycle" />
        </view>
        <view>
          <view>column</view>
          <ct-ui-loading-icon ref="loadingIcon" shapeType="column" />
        </view>
        <view>
          <view>ellipsis</view>
          <ct-ui-loading-icon ref="loadingIcon" shapeType="ellipsis" />
        </view>
        <view>
          <view>ripple</view>
          <ct-ui-loading-icon ref="loadingIcon" shapeType="ripple" />
        </view>
        <view>
          <view>point</view>
          <ct-ui-loading-icon ref="loadingIcon" shapeType="point" />
        </view>
        <view>
          <view>ring</view>
          <ct-ui-loading-icon ref="loadingIcon" shapeType="ring" />
        </view>
        <view>
          <view>tower</view>
          <ct-ui-loading-icon ref="loadingIcon" shapeType="tower" />
        </view>
      </view>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'loadingIcon',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss">
.lodingBox {
  display: flex;
  flex-wrap: wrap;
  & > view {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 80px;
    padding: 5px 20px;
    view {
      padding: 5px 20px;
    }
  }
}
</style>
```

### [设置样式](http://mid.chinatowercom.cn:18080/appGuide/ui/loadingIcon.html#设置样式)

- 通过`type`参数设置样式，可选值为**primary**: 已完成，**success**：成功，**warning**：警告，**danger**：错误
- 通过`size`参数设置加载动画的大小，可选值为**default**: 默认，**large**：大，**small**：小，

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置样式">
       
      <ct-ui-loading-icon ref="loadingIcon" shapeType="point" type="default" />
      <ct-ui-loading-icon ref="loadingIcon" shapeType="point" type="primary" />
      <ct-ui-loading-icon ref="loadingIcon" shapeType="point" type="success" />
      <ct-ui-loading-icon ref="loadingIcon" shapeType="point" type="warning" />
      <ct-ui-loading-icon ref="loadingIcon" shapeType="point" type="danger" />
       
    </ct-demo-card>
    <ct-demo-card title="设置大小">
      <ct-ui-loading-icon ref="loadingIcon" shapeType="tower" size="default" />
      <ct-ui-loading-icon ref="loadingIcon" shapeType="tower" size="large" />
      <ct-ui-loading-icon ref="loadingIcon" shapeType="tower" size="small" />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'loadingIcon',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss"></style>
```

### [文字内容](http://mid.chinatowercom.cn:18080/appGuide/ui/loadingIcon.html#文字内容)

- 通过`fontFlag`参数设置是否显示文字
- 通过`content`参数设置文字内容

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="文字内容">
      <ct-ui-loading-icon ref="loadingIcon" :fontFlag="fontFlag" />
      <ct-ui-loading-icon
        ref="loadingIcon"
        :fontFlag="fontFlag"
        :content="content"
      />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'loadingIcon',
  data() {
    return {
      fontFlag: true,
      content: '自定义'
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [自定义样式](http://mid.chinatowercom.cn:18080/appGuide/ui/loadingIcon.html#自定义样式)

- 通过`color`参数可自定义设置加载动画的颜色；
- 通过`customSize`参数可自定义设置加载动大小；
- 通过`fontSize`参数可自定义设置字体大小；
- 通过`fontColor`参数可自定义设置字体颜色；

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义样式">
       
      <view class="loading">
        <ct-ui-loading-icon
          ref="loadingIcon"
          shapeType="point"
          :fontFlag="fontFlag"
          color="#ffe600"
        />
      </view>
      <view class="loading">
        <ct-ui-loading-icon
          ref="loadingIcon"
          shapeType="point"
          :fontFlag="fontFlag"
          customSize="80px"
        />
      </view>
      <view class="loading">
        <ct-ui-loading-icon
          ref="loadingIcon"
          shapeType="point"
          :fontFlag="fontFlag"
          fontSize="20px"
        />
      </view>
      <view class="loading">
        <ct-ui-loading-icon
          ref="loadingIcon"
          shapeType="point"
          :fontFlag="fontFlag"
          fontColor="#ffe600"
        />
      </view>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'loadingIcon',
  data() {
    return {
      fontFlag: true
    }
  }
}
</script>

<style scoped lang="scss">
.loading {
  padding: 20px 0;
}
</style>
```

### [文字显示位置](http://mid.chinatowercom.cn:18080/appGuide/ui/loadingIcon.html#文字显示位置)

- 通过`place`参数设置文字显示位置，可选值为**top**、**bottom**、**left**、**right**；

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="文字显示位置">
       
      <view class="line">
        <ct-ui-loading-icon
          ref="loadingIcon"
          :shapeType="shapeType"
          :fontFlag="fontFlag"
          content="top"
          place="top"
        />
      </view>
      <view class="line">
        <ct-ui-loading-icon
          ref="loadingIcon"
          :shapeType="shapeType"
          :fontFlag="fontFlag"
          content="bottom"
          place="bottom"
        />
      </view>
      <view class="line">
        <ct-ui-loading-icon
          ref="loadingIcon"
          :shapeType="shapeType"
          :fontFlag="fontFlag"
          content="left"
          place="left"
        />
      </view>
      <view class="line">
        <ct-ui-loading-icon
          ref="loadingIcon"
          :shapeType="shapeType"
          :fontFlag="fontFlag"
          content="right"
          place="right"
        />
      </view>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'loadingIcon',
  data() {
    return {
      fontFlag: true,
      shapeType: 'ripple'
    }
  }
}
</script>

<style scoped lang="scss">
.line {
  padding: 20px 0;
  border-bottom: 1px solid #000;
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/loadingIcon.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/loadingIcon.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| shapeType  | 选择的加载动画类型   | String  | cycle   | cycle \| column \| ellipsis \| ripple \| point \| ring \| tower |
| ---------- | -------------------- | ------- | ------- | ------------------------------------------------------------ |
| type       | 样式类型             | String  | primary | primary：已完成 \| success：成功 \| warning：警告 \| danger：错误 |
| size       | 加载动画大小         | String  | default | default \| large \| small                                    |
| duration   | 加载动画时长，单位ms | Number  | 1200    | -                                                            |
| fontFlag   | 是否显示文字         | Boolean | false   | true/false                                                   |
| place      | 文字显示位置         | String  | bottom  | top \| bottom \| left \| right                               |
| content    | 文字内容             | String  | 请稍等  | -                                                            |
| color      | 自定义加载动画颜色   | String  |         | -                                                            |
| customSize | 自定义大小           | String  |         | -                                                            |
| fontSize   | 自定义字体大小       | String  |         | -                                                            |
| fontColor  | 自定义字体颜色       | String  |         | -                                                            |