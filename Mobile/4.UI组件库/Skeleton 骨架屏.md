# [Skeleton 骨架屏](http://mid.chinatowercom.cn:18080/appGuide/ui/skeleton.html#skeleton-骨架屏)

该组件一般用于页面在请求远程数据尚未完成时，采用灰色块预显示本来的页面结构，给用户更好的体验。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/skeleton.html#基本使用)

- 通过`loading`属性设置是否显示骨架屏
- 通过`rows`属性设置骨架列表数量

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-skeleton loading rows="4" />
             
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
<style lang="scss"></style>
```

### [card 图文模式](http://mid.chinatowercom.cn:18080/appGuide/ui/skeleton.html#card-图文模式)

- 通过`mode`属性设置为`card`设置为图文模式、`cardAction`为图文带按钮模式
- 通过`position`属性设置图片显示位置

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="card图文模式">
      <ct-ui-skeleton loading rows="4" mode="card" position="left" />
             
    </ct-demo-card>
    <ct-demo-card title="cardAction图文带按钮模式">
      <ct-ui-skeleton loading rows="4" mode="cardAction" position="left" />
             
    </ct-demo-card>
    <ct-demo-card title="设置图片位置">
      <ct-ui-skeleton loading rows="4" mode="cardAction" position="top" />
             
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
<style lang="scss"></style>
```

### [avatr 头像模式](http://mid.chinatowercom.cn:18080/appGuide/ui/skeleton.html#avatr-头像模式)

- 通过`mode`属性设置为`avatr`设置为头像模式、`userInfo`为用户信息卡
- 通过`avatrSize`属性设置图片、头像大小

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="avatr头像模式">
      <ct-ui-skeleton loading rows="4" mode="avatr" />
             
    </ct-demo-card>
    <ct-demo-card title="userInfo为用户信息卡">
      <ct-ui-skeleton loading rows="4" mode="userInfo" />
             
    </ct-demo-card>
    <ct-demo-card title="userInfo为用户信息卡">
      <ct-ui-skeleton loading rows="4" mode="userInfo" avatrSize="68" />
             
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
<style lang="scss"></style>
```

### [grid 宫格模式](http://mid.chinatowercom.cn:18080/appGuide/ui/skeleton.html#grid-宫格模式)

- 通过`mode`属性设置为`grid`设置为宫格模式
- 通过`column`属性设置宫格每行数量
- 通过`span`属性设置宫格间距

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="grid宫格模式">
      <ct-ui-skeleton loading rows="2" mode="grid" />
             
    </ct-demo-card>
    <ct-demo-card title="每行数量">
      <ct-ui-skeleton loading rows="1" mode="grid" column="3" />
             
    </ct-demo-card>
    <ct-demo-card title="宫格间距">
      <ct-ui-skeleton loading rows="1" mode="grid" column="3" span="4" />
             
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
<style lang="scss"></style>
```

### [自定义样式](http://mid.chinatowercom.cn:18080/appGuide/ui/skeleton.html#自定义样式)

- 通过`width`属性设置列表宽度
- 通过`height`属性设置列表高度
- 通过`radius`属性设置列表圆角大小
- 通过`color`属性设置列表背景色

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-skeleton
        loading
        :rows="4"
        mode="card"
        position="right"
        width="300"
        avatrSize="110"
        radius="16"
        color="#b8feff"
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
<style lang="scss"></style>
```

### [插槽](http://mid.chinatowercom.cn:18080/appGuide/ui/skeleton.html#插槽)

- 通过写入插槽，当请求完成，将`loading`设置为`false`，则隐藏骨架显示插槽内容

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="切换状态">
             
      <view style="padding: 0 0 10px 10px;">
        <ct-ui-switch v-model="loading"></ct-ui-switch>
      </view>
      <ct-ui-skeleton
        :loading="loading"
        mode="userInfo"
        rows="4"
        :animation="false"
      >
        <view class="demo-skeleton" v-show="!loading">
          <view class="demo-skeleton-image">
            <ct-ui-image class="demo_image" :image="image"></ct-ui-image>
          </view>
          <view class="demo-skeleton-row">
            <view class="demo-skeleton-row-title">中国铁塔移动端组件库</view>
            <view class="demo-skeleton-row-conter"
              >兼容多端开发，开发者编写一套代码即可发布到IOS、Android、H5、以及各种小程序等多个平台</view
            >
          </view>
        </view>
      </ct-ui-skeleton>
             
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      loading: true,
      image: {
        src: '/static/images/ct_list_icon.png',
        style: {
          width: '46px',
          height: '46px'
        },
        mode: 'scaleToFill',
        lazyLoad: true
      }
    }
  }
}
</script>
<style lang="scss">
.demo-skeleton {
  display: flex;
  flex-direction: row;
  height: 110px;
  &-image {
    width: 46px;
    height: 46px;
    border-radius: 50%;
    margin-right: 20rpx;
  }
  &-row {
    flex: 1;
    display: flex;
    flex-direction: column;
    &-title {
      font-weight: bold;
      margin: 2px 0;
      line-height: 30rpx;
      margin-bottom: 20rpx;
    }
    &-conter {
      color: #acacac;
      flex: 1;
      margin: 2px 0;
    }
  }
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/skeleton.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/skeleton.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| loading   | 是否显示骨架屏          | Boolean       | false   | -                                               |
| --------- | ----------------------- | ------------- | ------- | ----------------------------------------------- |
| mode      | 模式                    | String        | card    | card \| cardAction \| avatr \| userInfo \| grid |
| position  | 图片位置                | String        |         | top \| left                                     |
| avatrSize | 图片、头像大小          | Number,String |         | -                                               |
| rows      | 骨架行数                | Numebr,String | 4       | -                                               |
| span      | mode=grid时设置间距     | Number,String | 10px    | -                                               |
| column    | mode=grid每行数量       | Numebr,String | 4       | -                                               |
| justify   | mode=grid宫格内对齐方式 | String        |         | -                                               |
| radius    | 圆角值                  | Numebr,String | 4px     | -                                               |
| animation | 是否开启动画            | Boolean       | true    | true/false                                      |
| duration  | 动画时间，单位ms        | String,Number | 2000    | -                                               |
| amount    | 渲染数量                | Number        | 1       | -                                               |
| color     | 列表颜色                | String        | #e7e7e7 | -                                               |
| width     | 宽度                    | String,Number |         | -                                               |
| height    | 高度                    | String,Number |         | -                                               |