# [Line 进度条](http://mid.chinatowercom.cn:18080/appGuide/ui/line.html#line-进度条)

该组件主要对内容、模块起到一个上下图文分割的作用

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/line.html#基本使用)

- 通过`color`参数定义分割线条的颜色
- 通过`length`参数定义线条的长度
- 通过`layer`参数定义线条的粗细

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
        <ct-ui-line />
      <ct-ui-line color="#224b8f" />
      <ct-ui-line color="#224b8f" :length="200" />
      <ct-ui-line color="#224b8f" :length="200" :layer="6" />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ctLine',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss"></style>
```

### [线条类型](http://mid.chinatowercom.cn:18080/appGuide/ui/line.html#线条类型)

通过`type`参数设置线条的类型，**solid**为实线、**dotted**为点状、**dashed**为虚线

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="线条类型">
        <ct-ui-line type="solid" :layer="6" />
      <ct-ui-line type="dotted" :layer="6" />
      <ct-ui-line type="dashed" :layer="6" />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ctLine',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss"></style>
```

### [方向](http://mid.chinatowercom.cn:18080/appGuide/ui/line.html#方向)

通过`direction`参数设置线条的方向，**trans**为横向、**vert**为竖向

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="方向">
      <ct-ui-line direction="trans" />
      <ct-ui-line direction="vert" :length="200" />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ctLine',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss"></style>
```

### [文本内容](http://mid.chinatowercom.cn:18080/appGuide/ui/line.html#文本内容)

通过`content`参数设置线条文本内容，通过`fontColor`和`fontSize`分别设置字体颜色和字体大小

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="文本内容">
        <ct-ui-line content="分割线条" />
      <ct-ui-line content="分割线条" fontColor="#00ff00" />
      <ct-ui-line content="分割线条" fontColor="#00ff00" :fontSize="24" />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ctLine',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss"></style>
```

### [文本位置](http://mid.chinatowercom.cn:18080/appGuide/ui/line.html#文本位置)

通过`place`参数设置文本的显示位置

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="文本位置">
        <ct-ui-line :padding="20" content="上分割线条" place="top" />
      <ct-ui-line :padding="20" content="下分割线条" place="bottom" />
      <ct-ui-line :padding="20" content="中间分割线条" place="center" />
      <ct-ui-line :padding="20" content="左分割线条" place="left" />
      <ct-ui-line :padding="20" content="右分割线条" place="right" />
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ctLine',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss"></style>
```

### [使用插槽](http://mid.chinatowercom.cn:18080/appGuide/ui/line.html#使用插槽)

通过设置插槽内容自行进行使用

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="使用插槽">
       
      <ct-ui-line place="center" content="自定义插槽">
        <template v-slot:content>
          <view class="slotContent">
            <text>自定义插槽</text>
          </view>
        </template>
      </ct-ui-line>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ctLine',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss">
.slotContent {
  padding: 10px;
  background-color: #c8c7cc3d;
  border-radius: 8px;
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/line.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/line.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| type      | 选择的分割线条样式   | String       | solid    | solid（实线） \| dotted（点状） \| dashed（虚线） |
| --------- | -------------------- | ------------ | -------- | ------------------------------------------------- |
| color     | 线条颜色             | String       | #EB4B4B  | -                                                 |
| length    | 长度，单位px         | Number       | 屏幕宽度 | -                                                 |
| layer     | 粗细，单位px         | Number       | 2        | -                                                 |
| direction | 方向                 | String       | trans    | vert（竖） \| trans（横）                         |
| padding   | 间距                 | Array,Number | 8        | -                                                 |
| content   | 文本内容             | String       |          | -                                                 |
| place     | 文字显示位置         | String       | top      | center \| top \| bottom \| left \| right          |
| fontColor | 文本字体颜色         | String       | #000     | -                                                 |
| fontSize  | 文本字体大小，单位px | Number       |          | -                                                 |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/line.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

| content | 自定义线条上文本内容 | -    |
| ------- | -------------------- | ---- |
|         |                      |      |