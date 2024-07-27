# [Icon 图标](http://mid.chinatowercom.cn:18080/appGuide/ui/icon.html#icon-图标)

该组件基于字体的图标集，或者网络图标，通过 Icon 组件使用，也可以在其他组件中进行引用。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/icon.html#基本使用)

- 通过`name`参数定义图标名称，或者网络图标地址，自动识别是本地图标还是网络图标
- 通过`color`、`size`、`bold`参数设置图标的大小颜色及宽度
- 通过`hot`、`info`参数设置有上角的小圆点或者内容

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-icon name="home"></ct-ui-icon>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Icon',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss"></style>
```

### [图标颜色](http://mid.chinatowercom.cn:18080/appGuide/ui/icon.html#图标颜色)

通过`color`进行图标颜色，自定义颜色，支持 hex 及 grb。同时可使用系统定义颜色，`main` (主色-铁塔红)，`primary`(蓝色)，`warning`(黄色-警告)， `error`(红色-错误)，`success`(绿色-成功)，`info`(灰色-信息)

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="图标颜色">
          <ct-ui-icon name="home" color="#ff3678"></ct-ui-icon>
      <ct-ui-icon name="home" color="success"></ct-ui-icon>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Icon',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss"></style>
```

### [图标大小](http://mid.chinatowercom.cn:18080/appGuide/ui/icon.html#图标大小)

通过`size`进行图标大小，可以为数字或者带单位的值，默认单位 **px**

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="图标大小">
      <ct-ui-icon name="home" size="40px"></ct-ui-icon>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Icon',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss"></style>
```

### [图标宽度](http://mid.chinatowercom.cn:18080/appGuide/ui/icon.html#图标宽度)

通过`bold`进行图标宽度设置，可以 true/false，默认 false

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="图标宽度">
      <ct-ui-icon name="home" bold size="40px"></ct-ui-icon>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Icon',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss"></style>
```

### [提示信息](http://mid.chinatowercom.cn:18080/appGuide/ui/icon.html#提示信息)

通过`hot`设置右上角小圆点、`info`设置右上角的内容

#### [小圆点](http://mid.chinatowercom.cn:18080/appGuide/ui/icon.html#小圆点)

设置 **hot=true**，即可设置小圆点

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="小圆点">
      <ct-ui-icon name="chat-dots" hot size="40px"></ct-ui-icon>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Icon',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss"></style>
```

#### [信息](http://mid.chinatowercom.cn:18080/appGuide/ui/icon.html#信息)

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="信息">
      <ct-ui-icon name="chat-dots" info="99" size="40px"></ct-ui-icon>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Icon',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss"></style>
```

### [图标切换动画](http://mid.chinatowercom.cn:18080/appGuide/ui/icon.html#图标切换动画)

通过`transition`进行动画持续时长，单位 **ms**

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="图标切换动画">
      <ct-ui-icon
        :name="name"
        transition="300"
        @click="click"
        size="40px"
      ></ct-ui-icon>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Icon',
  data() {
    return {
      name: 'home-fill'
    }
  },
  methods: {
    click(e) {
      this.name = 'home'
      console.log('e::', e)
    }
  }
}
</script>

<style scoped lang="scss">
.box {
  width: 50px;
  height: 50px;
  border-radius: 10px;
  background-color: #999999;
  margin-left: 25px;
}
</style>
```

### [图标集合](http://mid.chinatowercom.cn:18080/appGuide/ui/icon.html#图标集合)



alert



alarm-bold



arrow-left



arrow-right



arrow-right-fill



arrow-drop-down



arrow-left-fill



arrow-drop-up



chevrons-left



chevrons-right



chevrons-down



chevrons-up



chevron-left



chevron-right



chevron-down



chevron-up



circle



camera-video



disabled



eye-line



eye-close-line



eye



eye-close



worklist



timer



timer-count-down



workbench



work-order



phone



customer



filter



voice



success



complete



not_pass



wubao



zhenjing



x-square



x-square-fill



copy



camera



camera-fill



info-fill



checkbox



diamond



envelope-close



bell



bell-fill



gift-fill



diagram



attach-email-twotone



diagram-fill



checkbox-circle-line



envelope-lock



envelope-block



checkbox-blank



info



list



list-check



list-choose



list-ui



list-ol



list-nested



list-task



geo



geo-fill



close



gift



close-circle-fill



checkbox-blank-circle-line



envelope



bell-slash-fill



bell-slash



checkbox-blank-circle-fill



checkbox-blank-fill



check-checked



checkbox-circle-fill



arrow-trending-lines-fill



person-fill



arrowleft



account



link



minus-square



plus-square



minus-circle-fill



minus-square-fill



plus-square-fill



alipay



alipay-outlined



arrow-expand



sunny



verified



minus



power



smartphone-fill



peoples



link-45deg



warning



person1



minus-circle



zoom-in



zoom-out



access-time-fill



access-time



alert-urgent



alert-urgent-fill



arrow-clockwise



arrow-counterclockwise



wifi



wifi-off



wifi-1



wifi-2



user



user-fill



home



homefill



newspaper-line



download



close-circle



delete



delete-fill



edit



overtime



history



home-fill



home1



information-fill



image



information



lock-unlock



lock-unlock-fill



lock-password



lock-password-fill



map-pin



notification-fill



more-line



notification



plus



plus-circle-fill



shield-user-fill



shield-keyhole-fill



shield-keyhole



search



shield-user



star-half



settings



settings-fill



refresh



plus-circle



star



star-fill



share



smartphone



upload



refresh

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/icon.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/icon.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| *name（必须） | icon的名称或者远程url图标地址            | String         | -           | -                   |          |
| ------------- | ---------------------------------------- | -------------- | ----------- | ------------------- | -------- |
| color         | 图标颜色                                 | String         | inherit     | -                   |          |
| size          | 图标大小/远程url图标地址高宽，默认单位px | String\|Number | inherit     | -                   |          |
| bold          | 图标宽度，默认false                      | Boolean        | false       | true\|false         |          |
| imgMode       | 图片裁剪、缩放的模式，image组件原生属性  | String         | scaleToFill | 见image组件原生属性 |          |
| hot           | 右上角小圆点                             | Boolean        | false       | true\|false         |          |
| info          | 右上角的内容                             | String         | -           | -                   |          |
| index         | 图标的索引                               | Number｜String | 0           | -                   |          |
| stop          | 是否阻止事件传播                         | Boolean        | true        | true\|false         | v1.0.13+ |
| transition    | 过渡动画时间（ms)                        | Number｜String | 0           | -                   |          |
| classPrefix   | classPrefix前缀                          | String         | cticon-     | -                   |          |
| customStyle   | 外部自定义样式                           | Object         | -           | -                   |          |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/icon.html#events)

| 事件名 | 说明 | 返回值 | 版本 |
| ------ | ---- | ------ | ---- |
|        |      |        |      |

| click | 点击触发 | 返回图标的索引值 |      |
| ----- | -------- | ---------------- | ---- |
|       |          |                  |      |