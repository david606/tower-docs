# [AvatarGroup 头像组](http://mid.chinatowercom.cn:18080/appGuide/ui/avatarGroup.html#avatargroup-头像组)

该组件一般用于点赞、评价列表的头像展示。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/avatarGroup.html#基本使用)

- 通过`posX`参数设置头像偏移位置，默认单位 rpx
- 通过`max`参数设置最多显示多少个头像，不设置默认显示全部
- 通过`data`参数设置显示的头像列表，值为数组对象，必须有 url 或 label，url 为图片地址，label 为文字，url 和 label 同时有参数时 url 优先级最高
- 通过`size`参数设置头像大小，默认单位 rpx
- 通过`labelColor`参数设置更多或收起的字体颜色
- 通过`labelSize`参数设置更多或收起字体的大小，默认单位 rpx

```vue
<template>
  <view class="avatar-group-page">
    <ct-demo-card title="基础使用">
      <ct-ui-avatar-group
        posX="-10px"
        :max="3"
        @showMore="showMores"
        :data="imgList"
        size="50px"
        labelSize="16"
      >
      </ct-ui-avatar-group>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      imgList: [
        {
          url: '../../../../../static/images/ct_logo.png'
        },
        {
          url: '../../../../../static/images/ct_logo.png'
        },
        {
          url: ''
        },
        {
          url: ''
        },
        {
          url: ''
        },
        {
          url: ''
        },
        {
          url: ''
        }
      ]
    }
  },
  methods: {
    // 更多点击事件
    showMores(e) {
      console.log(e, '---e---')
    }
  }
}
</script>

<style lang="scss">
.avatar-group-page {
  padding: 12px;
}
</style>
```

### [图片、文字头像组](http://mid.chinatowercom.cn:18080/appGuide/ui/avatarGroup.html#图片、文字头像组)

- 通过`data`参数设置显示的头像列表，值为数组对象，必须有 url 或 label，url 为图片地址，label 为文字，url 和 label 同时有参数时 url 优先级最高

```vue
<template>
  <view class="avatar-group-page">
    <ct-demo-card title="图片、文字头像组">
      <ct-ui-avatar-group
        posX="-10px"
        :max="3"
        @showMore="showMores"
        :data="imgLists"
        size="50px"
        labelSize="16"
      >
      </ct-ui-avatar-group>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      imgLists: [
        {
          url: '../../../../../static/images/ct_logo.png'
        },
        {
          url: '../../../../../static/images/ct_logo.png',
          label: '杨'
        },
        {
          url: '',
          label: '杨'
        },
        {
          url: ''
        },
        {
          url: ''
        },
        {
          url: ''
        },
        {
          url: ''
        }
      ]
    }
  },
  methods: {
    // 更多点击事件
    showMores(e) {
      console.log(e, '---e---')
    }
  }
}
</script>

<style lang="scss">
.avatar-group-page {
  padding: 12px;
}
</style>
```

### [文字头像背景色、字体大小、字体颜色](http://mid.chinatowercom.cn:18080/appGuide/ui/avatarGroup.html#文字头像背景色、字体大小、字体颜色)

- 通过`data`参数设置显示的头像列表，值为数组对象，必须有 url 或 label，url 为图片地址，label 为文字，url 和 label 同时有参数时 url 优先级最高
- 通过`headLabelColor`参数设置文字头像字体颜色
- 通过`headLabelSize`参数设置文字头像字体大小，默认单位 rpx
- 通过`bgColor`参数设置文字头像背景色

```vue
<template>
  <view class="avatar-group-page">
    <ct-demo-card title="文字头像背景色、字体大小、字体颜色">
      <ct-ui-avatar-group
        posX="-10px"
        :max="3"
        @showMore="showMores"
        :data="imgListc"
        size="50px"
        labelSize="16"
        bgColor="#eb4b4b"
        headLabelColor="#fff"
        headLabelSize="20px"
      >
      </ct-ui-avatar-group>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      imgListc: [
        {
          url: '',
          label: '头'
        },
        {
          url: '',
          label: '像'
        },
        {
          url: '',
          label: '组'
        },
        {
          url: ''
        },
        {
          url: ''
        },
        {
          url: ''
        },
        {
          url: ''
        }
      ]
    }
  },
  methods: {
    // 更多点击事件
    showMores(e) {
      console.log(e, '---e---')
    }
  }
}
</script>

<style lang="scss">
.avatar-group-page {
  padding: 12px;
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/avatarGroup.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/avatarGroup.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| posX           | 头像偏移位           | String \| Number | -       | -    |
| -------------- | -------------------- | ---------------- | ------- | ---- |
| max            | 头像组最大显示数量   | Number           | 0       | -    |
| data           | 头像列表             | Array            | []      | -    |
| size           | 头像大小             | String \| Number | -       | -    |
| labelColor     | 更多字体颜色修改     | String           | #eb4b4b | -    |
| labelSize      | 更多字体大小修改     | Number \| String | -       | -    |
| headLabelColor | 设置文字头像字体颜色 | String           | -       | -    |
| headLabelSize  | 设置文字头像字体大小 | Number \| String | -       | -    |
| bgColor        | 设置文字头像背景色   | String           | -       | -    |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/avatarGroup.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| showMore | 点击组件更多或收起时触发 | -    |
| -------- | ------------------------ | ---- |
|          |                          |      |