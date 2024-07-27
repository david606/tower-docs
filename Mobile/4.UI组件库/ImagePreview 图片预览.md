# [ImagePreview 图片预览](http://mid.chinatowercom.cn:18080/appGuide/ui/imagePreview.html#imagepreview-图片预览)

该组件主要对图片预览功能进行封装,使图片预览有更好的展示效果。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/imagePreview.html#基本使用)

- 通过`imagesList`参数传入需要展示的图片列表
- 通过 `show`参数通知预览组件是否显示
- 接收一个`close`方法,表示关闭按钮点击事件

```vue
<template>
  <view>
    <ct-ui-image-preview :imagesList="imagesList" :show="show" @close="close">
    </ct-ui-image-preview>
  </view>
</template>

<script>
export default {
  data() {
    return {
      imagesList: [
        {
          url: 'https://image.photocnc.com/aoaodcom/2019-10/17/2019101708354324cd0c32d48a16c86c49512d75c2e10c.jpg.h700.webp',
          href: '/pages/demo/request',
          desc: '第一张图片'
        },
        {
          url: '/static/images/ct_advertisement.jpeg',
          href: '',
          desc: ''
        }
      ],
      show: true
    }
  },
  methods: {
    close() {
      this.show = false
    }
  }
}
</script>

<style></style>
```

### [图片展示功能](http://mid.chinatowercom.cn:18080/appGuide/ui/imagePreview.html#图片展示功能)

- 通过 `index`参数设置图片预览初始位置的索引
- 通过`rotate `参数开启图片的旋转功能
- 通过`zoom`参数开启图片的放大缩小功能
- 通过`closeable`参数显示关闭图标
- 通过`closeIcon`参数设置关闭按钮的图标
- 通过`showTip`参数设置图片描述是否显示
- 通过 `showIndex`参数设置图片当前页码是否显示
- 通过`tipStyle`参数设置图片描述和页码的文字样式
- 通过`opacity`参数设置图片的透明度
- 通过`downable`参数设置下载按钮是否显示

```vue
<template>
  <view>
    <ct-ui-image-preview
      :imagesList="imagesList"
      :show="show"
      index="1"
      :rotate="false"
      :zoom="false"
      :closeable="false"
      :showTip="false"
      :showIndex="false"
      :opacity="0.6"
      @close="close"
    >
    </ct-ui-image-preview>
  </view>
</template>

<script>
export default {
  data() {
    return {
      imagesList: [
        {
          url: 'https://image.photocnc.com/aoaodcom/2019-10/17/2019101708354324cd0c32d48a16c86c49512d75c2e10c.jpg.h700.webp',
          href: '/pages/demo/request',
          desc: '第一张图片'
        },
        {
          url: '/static/images/ct_advertisement.jpeg',
          href: '',
          desc: ''
        }
      ],
      show: true
    }
  },
  methods: {
    close() {
      this.show = false
    }
  }
}
</script>

<style></style>
```

### [图片展示功能](http://mid.chinatowercom.cn:18080/appGuide/ui/imagePreview.html#图片展示功能-1)

- 通过`closeaIcon`参数设置关闭按钮的图标
- 通过`tipStyle`参数设置图片描述和页码的文字样式

```vue
<template>
  <view>
    <ct-ui-image-preview
      :imagesList="imagesList"
      :show="show"
      closeaIcon="arrow-left"
      :tipStyle="tipStyle"
      @close="close"
    >
    </ct-ui-image-preview>
  </view>
</template>

<script>
export default {
  data() {
    return {
      imagesList: [
        {
          url: 'https://image.photocnc.com/aoaodcom/2019-10/17/2019101708354324cd0c32d48a16c86c49512d75c2e10c.jpg.h700.webp',
          href: '/pages/demo/request',
          desc: '第一张图片'
        },
        {
          url: '/static/images/ct_advertisement.jpeg',
          href: '',
          desc: ''
        }
      ],
      show: true,
      tipStyle: {
        color: 'red'
      }
    }
  },
  methods: {
    close() {
      this.show = false
    }
  }
}
</script>

<style></style>
```

### [图片展示弹窗模式](http://mid.chinatowercom.cn:18080/appGuide/ui/imagePreview.html#图片展示弹窗模式)

- 通过`mode`参数设置组件的模式（遮罩层、弹窗）
- 通过`drawerClass`参数设置弹出层的 class

```vue
<template>
  <view>
    <ct-ui-image-preview
      :imagesList="imagesList"
      :show="show"
      mode="drawer"
      drawerClass="drawer-box"
      @close="close"
    >
    </ct-ui-image-preview>
  </view>
</template>

<script>
export default {
  data() {
    return {
      imagesList: [
        {
          url: 'https://image.photocnc.com/aoaodcom/2019-10/17/2019101708354324cd0c32d48a16c86c49512d75c2e10c.jpg.h700.webp',
          href: '/pages/demo/request',
          desc: '第一张图片'
        },
        {
          url: '/static/images/ct_advertisement.jpeg',
          href: '',
          desc: ''
        }
      ],
      show: true
    }
  },
  methods: {
    close() {
      this.show = false
    }
  }
}
</script>

<style>
>>> .drawer-box {
  background-color: antiquewhite;
}
</style>
```

### [图片预览轮播图](http://mid.chinatowercom.cn:18080/appGuide/ui/imagePreview.html#图片预览轮播图)

- 通过`circulate`参数设置是否开启轮播模式
- 通过`showIndicators`参数设置是否展示轮播指示器
- 通过`duration`参数设置轮播切换时长

```vue
<template>
  <view>
    <ct-ui-image-preview
      :imagesList="imagesList"
      :show="show"
      :circulate="true"
      :showIndicators="true"
      :duration="6000"
      drawerClass="drawer-box"
      @close="close"
    >
    </ct-ui-image-preview>
  </view>
</template>

<script>
export default {
  data() {
    return {
      imagesList: [
        {
          url: 'https://image.photocnc.com/aoaodcom/2019-10/17/2019101708354324cd0c32d48a16c86c49512d75c2e10c.jpg.h700.webp',
          href: '/pages/demo/request',
          desc: '第一张图片'
        },
        {
          url: '/static/images/ct_advertisement.jpeg',
          href: '',
          desc: ''
        }
      ],
      show: true
    }
  },
  methods: {
    close() {
      this.show = false
    }
  }
}
</script>

<style></style>
```

### [插槽方式修改图标](http://mid.chinatowercom.cn:18080/appGuide/ui/imagePreview.html#插槽方式修改图标)

- 通过`slot`插槽可任意修改图标（back：上一张,next：下一张,amplify：放大,reduce：缩小,rotate：旋转,download：下载）

```vue
<template>
  <view>
    <ct-ui-image-preview :imagesList="imagesList" :show="show" @close="close">
      <!-- 修改前一张按钮图标为前一张三个字 -->
      <view slot="back">
        <view> 前一张 </view>
      </view>
    </ct-ui-image-preview>
  </view>
</template>

<script>
export default {
  data() {
    return {
      imagesList: [
        {
          url: 'https://image.photocnc.com/aoaodcom/2019-10/17/2019101708354324cd0c32d48a16c86c49512d75c2e10c.jpg.h700.webp',
          href: '/pages/demo/request',
          desc: '第一张图片'
        },
        {
          url: '/static/images/ct_advertisement.jpeg',
          href: '',
          desc: ''
        }
      ],
      show: true
    }
  },
  methods: {
    close() {
      this.show = false
    },
    download(image) {
      console.log(image)
    }
  }
}
</script>

<style></style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/imagePreview.html#事件监听)

点击下载按钮,会在父组件触发`download`方法,返回预览图片的基本信息

```vue
<template>
  <view>
    <ct-ui-image-preview
      :imagesList="imagesList"
      :show="show"
      @close="close"
      @download="download"
    >
    </ct-ui-image-preview>
  </view>
</template>

<script>
export default {
  data() {
    return {
      imagesList: [
        {
          url: 'https://image.photocnc.com/aoaodcom/2019-10/17/2019101708354324cd0c32d48a16c86c49512d75c2e10c.jpg.h700.webp',
          href: '/pages/demo/request',
          desc: '第一张图片'
        },
        {
          url: '/static/images/ct_advertisement.jpeg',
          href: '',
          desc: ''
        }
      ],
      show: true
    }
  },
  methods: {
    close() {
      this.show = false
    },
    download(image) {
      console.log(image)
    }
  }
}
</script>

<style></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/imagePreview.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/imagePreview.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本号 |
| ---- | ---- | ---- | ------ | ------ | ------ |
|      |      |      |        |        |        |

| mode           | 预览图片的模式                           | String           | mask              | mask(遮罩层) \| drawer(弹框模式) | v1.0.23+ |
| -------------- | ---------------------------------------- | ---------------- | ----------------- | -------------------------------- | -------- |
| drawerClass    | 弹出框的class【在弹框模式下生效】        | String           |                   | -                                | v1.0.23+ |
| show           | 图片预览组件是否显示                     | Boolean          | true              | true \| false                    | v1.0.23+ |
| imagesList     | 预览图片的列表                           | Array            |                   | [{url: '', href: '',desc: ''}]   | v1.0.23+ |
| index          | 初始预览时的图片索引                     | Number           | 0                 | -                                | v1.0.23+ |
| showIndex      | 图片页码是否显示                         | Boolean          | true              | true \| false                    | v1.0.23+ |
| rotate         | 旋转功能                                 | Boolean          | true              | true \| false                    | v1.0.23+ |
| zoom           | 缩放功能                                 | Boolean          | true              | true \| false                    | v1.0.23+ |
| closeable      | 关闭图标是否显示                         | Boolean          | true              | true \| false                    | v1.0.23+ |
| closeIcon      | 关闭图标的图标（可使用数据参考icon组件） | String           | close-circle-fill | -                                | v1.0.23+ |
| showTip        | 图片描述是否显示                         | Boolean          | true              | true \| false                    | v1.0.23+ |
| tipStyle       | 图片描述与页码的样式                     | Object           | {}                | -                                | v1.0.23+ |
| opacity        | 图片的透明度                             | Number \| String | 1                 | -                                | v1.0.23+ |
| downable       | 下载功能                                 | Boolean          | true              | true \| false                    | v1.0.23+ |
| circulate      | 是否开启轮播                             | Boolean          | false             | true \| false                    | v1.0.23+ |
| showIndicators | 是否显示轮播指示器                       | Boolean          | true              | true \| false                    | v1.0.23+ |
| duration       | 轮播切换时长                             | Number           | 1000              | -                                | v1.0.23+ |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/imagePreview.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
| NoData |      |        |

