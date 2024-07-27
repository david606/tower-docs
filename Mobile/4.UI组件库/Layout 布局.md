# [Layout 布局](http://mid.chinatowercom.cn:18080/appGuide/ui/layout.html#layout-布局)

该组件主要通过 24 分栏，对页面进行快速的划分

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/layout.html#基本使用)

- 通过`span`参数设置栅格占据的列数

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
         
      <ct-ui-row>
        <ct-ui-col :span="8">
          <view class="demo-col-odd"></view>
        </ct-ui-col>
        <ct-ui-col :span="8">
          <view class="demo-col-tow"></view>
        </ct-ui-col>
        <ct-ui-col :span="8">
          <view class="demo-col-odd"></view>
        </ct-ui-col>
      </ct-ui-row>
      <ct-ui-row>
        <ct-ui-col :span="4">
          <view class="demo-col-odd"></view>
        </ct-ui-col>
        <ct-ui-col :span="8">
          <view class="demo-col-tow"></view>
        </ct-ui-col>
        <ct-ui-col :span="12">
          <view class="demo-col-odd"></view>
        </ct-ui-col>
      </ct-ui-row>
      <ct-ui-row>
        <ct-ui-col :span="12">
          <view class="demo-col-odd"></view>
        </ct-ui-col>
        <ct-ui-col :span="8">
          <view class="demo-col-tow"></view>
        </ct-ui-col>
        <ct-ui-col :span="4">
          <view class="demo-col-odd"></view>
        </ct-ui-col>
      </ct-ui-row>
         
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

<style lang="scss">
.demo-col-odd {
  background-color: #e5e5e5;
  height: 30px;
  border-radius: 4px;
  margin: 5px 0;
}
.demo-col-tow {
  background-color: #ababab;
  height: 30px;
  border-radius: 4px;
  margin: 5px 0;
}
</style>
```

### [分栏间隔](http://mid.chinatowercom.cn:18080/appGuide/ui/layout.html#分栏间隔)

- 通过`gutter`参数设置栅格之间的间隔

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="分栏间隔">
         
      <ct-ui-row :gutter="20">
        <ct-ui-col :span="8">
          <view class="demo-col-odd"></view>
        </ct-ui-col>
        <ct-ui-col :span="8">
          <view class="demo-col-tow"></view>
        </ct-ui-col>
        <ct-ui-col :span="8">
          <view class="demo-col-odd"></view>
        </ct-ui-col>
      </ct-ui-row>
         
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

<style lang="scss">
.demo-col-odd {
  background-color: #e5e5e5;
  height: 30px;
  border-radius: 4px;
  margin: 5px 0;
}
.demo-col-tow {
  background-color: #ababab;
  height: 30px;
  border-radius: 4px;
  margin: 5px 0;
}
</style>
```

### [分栏偏移](http://mid.chinatowercom.cn:18080/appGuide/ui/layout.html#分栏偏移)

- 通过`offset`参数设置栅格左侧的间隔格数
- 通过`left`参数设置栅格向左移动格数
- 通过`right`参数设置栅格向右移动格数

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="分栏偏移">
         
      <ct-ui-row :gutter="20">
        <ct-ui-col :span="8" :offset="4">
          <view class="demo-col-odd"></view>
        </ct-ui-col>
        <ct-ui-col :span="8" :offset="4">
          <view class="demo-col-tow"></view>
        </ct-ui-col>
        <ct-ui-col :span="8" :left="0">
          <view class="demo-col-odd"></view>
        </ct-ui-col>
        <ct-ui-col :span="8" :right="4">
          <view class="demo-col-tow"></view>
        </ct-ui-col>
      </ct-ui-row>
         
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

<style lang="scss">
.demo-col-odd {
  background-color: #e5e5e5;
  height: 30px;
  border-radius: 4px;
  margin: 5px 0;
}
.demo-col-tow {
  background-color: #ababab;
  height: 30px;
  border-radius: 4px;
  margin: 5px 0;
}
</style>
```

### [水平方向对齐方式](http://mid.chinatowercom.cn:18080/appGuide/ui/layout.html#水平方向对齐方式)

- 通过`type`参数设置布局方式为**flex**布局
- 通过`justify`参数设置**flex**布局下的水平排列方式

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="水平方向对齐方式">
         
      <ct-ui-row type="flex" justify="start">
        <ct-ui-col :span="8">
          <view class="demo-col-odd"></view>
        </ct-ui-col>
        <ct-ui-col :span="8">
          <view class="demo-col-tow"></view>
        </ct-ui-col>
      </ct-ui-row>
      <ct-ui-row type="flex" justify="end">
        <ct-ui-col :span="8">
          <view class="demo-col-odd"></view>
        </ct-ui-col>
        <ct-ui-col :span="8">
          <view class="demo-col-tow"></view>
        </ct-ui-col>
      </ct-ui-row>
      <ct-ui-row type="flex" justify="center">
        <ct-ui-col :span="8">
          <view class="demo-col-odd"></view>
        </ct-ui-col>
        <ct-ui-col :span="8">
          <view class="demo-col-tow"></view>
        </ct-ui-col>
      </ct-ui-row>
      <ct-ui-row type="flex" justify="space-around">
        <ct-ui-col :span="8">
          <view class="demo-col-odd"></view>
        </ct-ui-col>
        <ct-ui-col :span="8">
          <view class="demo-col-tow"></view>
        </ct-ui-col>
      </ct-ui-row>
      <ct-ui-row type="flex" justify="space-between">
        <ct-ui-col :span="8">
          <view class="demo-col-odd"></view>
        </ct-ui-col>
        <ct-ui-col :span="8">
          <view class="demo-col-tow"></view>
        </ct-ui-col>
      </ct-ui-row>
         
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

<style lang="scss">
.demo-col-odd {
  background-color: #e5e5e5;
  height: 30px;
  border-radius: 4px;
  margin: 5px 0;
}
.demo-col-tow {
  background-color: #ababab;
  height: 30px;
  border-radius: 4px;
  margin: 5px 0;
}
</style>
```

### [垂直方向对齐方式](http://mid.chinatowercom.cn:18080/appGuide/ui/layout.html#垂直方向对齐方式)

- 通过`type`参数设置布局方式为**flex**布局
- 通过`align`参数设置**flex**布局下的垂直排列方式

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="垂直方向对齐方式">
         
      <ct-ui-row type="flex" align="start">
        <ct-ui-col :span="8">
          <view class="demo-col-odd"></view>
        </ct-ui-col>
        <ct-ui-col :span="8">
          <view class="demo-col-tow"></view>
        </ct-ui-col>
        <ct-ui-col :span="8">
          <view class="demo-col-odd"></view>
        </ct-ui-col>
      </ct-ui-row>
      <ct-ui-row type="flex" align="end">
        <ct-ui-col :span="8">
          <view class="demo-col-odd"></view>
        </ct-ui-col>
        <ct-ui-col :span="8">
          <view class="demo-col-tow"></view>
        </ct-ui-col>
        <ct-ui-col :span="8">
          <view class="demo-col-odd"></view>
        </ct-ui-col>
      </ct-ui-row>
      <ct-ui-row type="flex" align="middle">
        <ct-ui-col :span="8">
          <view class="demo-col-odd"></view>
        </ct-ui-col>
        <ct-ui-col :span="8">
          <view class="demo-col-tow"></view>
        </ct-ui-col>
        <ct-ui-col :span="8">
          <view class="demo-col-odd"></view>
        </ct-ui-col>
      </ct-ui-row>
         
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

<style lang="scss">
.demo-col-odd {
  background-color: #e5e5e5;
  height: 20px;
  border-radius: 4px;
  margin: 5px 0;
}
.demo-col-tow {
  background-color: #ababab;
  height: 40px;
  border-radius: 4px;
  margin: 5px 0;
}
</style>
```

### [ROW API](http://mid.chinatowercom.cn:18080/appGuide/ui/layout.html#row-api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/layout.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| type    | 布局模式，可选flex布局   | String         |       | flex                                                    |
| ------- | ------------------------ | -------------- | ----- | ------------------------------------------------------- |
| wrap    | flex布局下开启换行       | Boolean        | false | true/false                                              |
| gutter  | 栅格间隔                 | String\|Number |       | -                                                       |
| justify | flex布局下的水平排列方式 | String         | start | start \| end \| center \| space-around \| space-between |
| align   | flex布局下的垂直排列方式 | String         | start | start \| end \| middle                                  |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/layout.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| click \| tap | 点击组件时触发 | -    |
| ------------ | -------------- | ---- |
|              |                |      |

### [COL API](http://mid.chinatowercom.cn:18080/appGuide/ui/layout.html#col-api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/layout.html#props-1)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| span   | 栅格占据的列数     | Number, String |      | 24   |
| ------ | ------------------ | -------------- | ---- | ---- |
| offset | 栅格左侧的间隔格数 | Number, String |      | —    |
| right  | 栅格向右移动格数   | Number, String |      | —    |
| left   | 栅格向左移动格数   | Number, String |      | —    |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/layout.html#events-1)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| click \| tap | 点击组件时触发 | -    |
| ------------ | -------------- | ---- |
|              |                |      |