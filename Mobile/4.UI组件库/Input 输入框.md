# [Input 输入框](http://mid.chinatowercom.cn:18080/appGuide/ui/input.html#input-输入框)

该组件通常用于输入账号或密码等信息。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/input.html#基本使用)

- 通过`isPassword`参数设置是否是密码类型
- 通过`height`参数设置输入框高度
- 通过`maxlength`参数设置输入框最大输入长度
- 通过`borderColor`参数设置边框颜色
- 通过`borderStyle`参数设置边框样式

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-input style="margin-top: 40rpx;" v-model="value" />
             
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      value: ''
    }
  }
}
</script>
<style lang="scss"></style>
```

### [设置密码框](http://mid.chinatowercom.cn:18080/appGuide/ui/input.html#设置密码框)

通过`isPassword`参数设置是否是密码类型

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="密码输入框、没有显隐切换">
      <ct-ui-input
        style="margin-top: 40rpx;"
        :isPassword="true"
        :showEyesIcon="false"
        v-model="value"
      />
             
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      value: ''
    }
  }
}
</script>
<style lang="scss"></style>
```

### [设置密码框显隐切换](http://mid.chinatowercom.cn:18080/appGuide/ui/input.html#设置密码框显隐切换)

通过`isPassword`参数设置是否是密码类型

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="有边框、密码输入框、有显隐切换">
      <ct-ui-input
        style="margin-top: 40rpx;"
        borderStyle="border"
        :isPassword="true"
        v-model="value"
      />
             
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      value: ''
    }
  }
}
</script>
<style lang="scss"></style>
```

### [设置大小及边框](http://mid.chinatowercom.cn:18080/appGuide/ui/input.html#设置大小及边框)

- 通过`borderStyle`参数设置输入框边框样式，值为`border`、`bottom`
- 通过`size`参数设置输入框的大小，值为`big`、`middle`、`small`

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置大小及边框">
                 
      <ct-ui-input
        style="margin-top: 40rpx;"
        borderStyle="bottom"
        v-model="value1"
      />
      <ct-ui-input
        style="margin-top: 40rpx;"
        borderStyle="border"
        v-model="value2"
      />
      <ct-ui-input
        style="margin-top: 40rpx;"
        borderStyle="border"
        size="big"
        v-model="value3"
      />
      <ct-ui-input
        style="margin-top: 40rpx;"
        borderStyle="border"
        size="middle"
        v-model="value4"
      />
      <ct-ui-input
        style="margin-top: 40rpx;"
        borderStyle="border"
        size="small"
        v-model="value5"
      />
             
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      value1: '',
      value2: '',
      value3: '',
      value4: '',
      value5: ''
    }
  }
}
</script>

<style lang="scss"></style>
```

### [设置 icon 图标](http://mid.chinatowercom.cn:18080/appGuide/ui/input.html#设置-icon-图标)

- 通过`icon`参数设置 icon 图标，`type`设置图标类型（**icon** | **img**），**img**类型则通过`src`设置图片路径，**icon**类型详细参数参考**icon**组件 通过`cleanIcon`参数设置清除图标，`type`设置图标类型（**icon** | **img**），**img**类型则通过`src`设置图片路径，**icon**类型详细参数参考**icon**组件 通过`showClearIcon`参数设置是否带有清除按钮

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置icon图标">
      <ct-ui-input
        style="margin-top: 40rpx;"
        borderStyle="border"
        :icon="icon"
        :showClearIcon="false"
        v-model="value1"
      />
      <ct-ui-input
        style="margin-top: 40rpx;"
        borderStyle="border"
        :icon="icon2"
        :showClearIcon="false"
        v-model="value2"
      />
      <ct-ui-input
        style="margin-top: 40rpx;"
        borderStyle="border"
        :icon="icon"
        :showClearIcon="true"
        v-model="value3"
      />
      <ct-ui-input
        style="margin-top: 40rpx;"
        borderStyle="border"
        :icon="icon"
        :cleanIcon="cleanIcon"
        :showClearIcon="true"
        v-model="value4"
      />
             
    </ct-demo-card>
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {
      value1: '',
      value2: '',
      value3: '',
      value4: '',
      icon: {
        type: 'icon',
        name: 'home'
      },
      icon2: {
        type: 'img',
        src: '../../static/images/ct_user.png',
        style: {
          width: '36rpx',
          height: '36rpx'
        }
      },
      cleanIcon: {
        type: 'icon',
        name: 'close'
      }
    }
  }
}
</script>

<style lang="scss"></style>
```

### [复合式输入框](http://mid.chinatowercom.cn:18080/appGuide/ui/input.html#复合式输入框)

- 通过`prefix`参数设置前嵌入内容
- 通过`suffix`参数设置后嵌入内容

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="复合式输入框">
                 
      <ct-ui-input
        style="margin-top: 20rpx;"
        borderStyle="border"
        :prefix="prefix"
        v-model="value1"
      />
      <ct-ui-input
        style="margin-top: 20rpx;"
        borderStyle="border"
        :suffix="suffix"
        v-model="value1"
      />
      <ct-ui-input
        style="margin-top: 20rpx;"
        borderStyle="border"
        :prefix="prefix"
        :suffix="suffix"
        v-model="value2"
        @onConfirm="onConfirm"
      />
             
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      value1: '',
      value2: '',
      prefix: {
        hide: false,
        content: 'http://',
        style: {
          width: '120rpx'
        }
      },
      suffix: {
        hide: false,
        content: '.com',
        style: {
          width: '120rpx'
        }
      }
    }
  },
  onLoad() {
    _self = this
  },
  methods: {}
}
</script>

<style lang="scss"></style>
```

### [输入框类型](http://mid.chinatowercom.cn:18080/appGuide/ui/input.html#输入框类型)

- 通过`type`参数设置输入框类型
- `search`事件监听*type*为*search*时的右侧搜索事件
- `precision`事件监听*type*为*price*时的小数点精度
- `separator`事件监听*type*为*price*时的千分符

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="输入框类型">
           
      <ct-ui-input
        style="margin-top: 20rpx;"
        type="text"
        borderStyle="border"
        v-model="value1"
      />
      <ct-ui-input
        style="margin-top: 20rpx;"
        type="phone"
        borderStyle="border"
        v-model="value2"
      />
      <ct-ui-input
        style="margin-top: 20rpx;"
        type="ID"
        borderStyle="border"
        precision="4"
        separator="*"
        v-model="value3"
      />
      <ct-ui-input
        style="margin-top: 20rpx;"
        type="price"
        borderStyle="border"
        v-model="value4"
      />
      <ct-ui-input
        style="margin-top: 20rpx;"
        type="search"
        borderStyle="border"
        v-model="value5"
      />
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      value1: '',
      value2: '',
      value3: '',
      value4: '',
      value5: ''
    }
  }
}
</script>
<style lang="scss"></style>
```

### [自定义插槽](http://mid.chinatowercom.cn:18080/appGuide/ui/input.html#自定义插槽)

- 通过`prefix`name 设置前嵌入插槽
- 通过`suffix`name 设置后嵌入插槽
- 通过`search`name 设置搜索插槽

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义插槽">
      <ct-ui-input
        style="margin-top: 20rpx;"
        type="search"
        borderStyle="border"
        v-model="value"
      >
        <template slot="prefix">
          <view class="prefix">http://</view>
        </template>
        <template slot="suffix">
          <view class="suffix">.com</view>
        </template>
        <template slot="search">
          <view class="search">搜索</view>
        </template>
      </ct-ui-input>
             
    </ct-demo-card>
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {
      value: ''
    }
  }
}
</script>

<style lang="scss">
.demo-page {
  .prefix {
    height: 70rpx;
    line-height: 70rpx;
    padding: 0 20rpx;
    background: #f0f2f3;
  }
  .suffix {
    height: 70rpx;
    line-height: 70rpx;
    padding: 0 20rpx;
    background: #f0f2f3;
  }
  .search {
    height: 70rpx;
    padding: 0 20rpx;
  }
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/input.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/input.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| value                      | 数据                                   | String           | —                   | —                                      |          |
| -------------------------- | -------------------------------------- | ---------------- | ------------------- | -------------------------------------- | -------- |
| type                       | 输入类型                               | String           | text                | text \| ID \| phone \| search \| price |          |
| precision                  | 小数点精确度                           | String \| Number | 2                   | -                                      | 1.0.32+  |
| separator                  | 千分符                                 | String           | ,                   |                                        | 1.0.32+  |
| size                       | 输入框大小                             | String           | big                 | big \| middle \| small                 |          |
| icon                       | icon图标                               | Object           | {}                  | -                                      |          |
| prefix                     | 前嵌入内容                             | Object           | {}                  | -                                      |          |
| suffix                     | 后嵌入内容                             | Object           | {}                  | -                                      |          |
| preg                       | 自定义正则表达式                       | Array            | []                  | -                                      |          |
| isPassword                 | 是否密码类型                           | Boolean          | false               | true \| false                          |          |
| placeholder                | placeholder值                          | String           | -                   | -                                      | v1.0.20+ |
| placeholderStyle           | placeholder的样式                      | String           | color: #999999      | -                                      | v1.0.20+ |
| placeholderClass           | placeholderClass 类名                  | String           | input-placeholder   | -                                      | v1.0.20+ |
| confirmType                | 键盘右下角文字                         | String           | done                | send \| search \| next \| go \| done   |          |
| showConfirmbar             | 是否显示二级键盘                       | Boolean          | true                | true \| false                          |          |
| height                     | 高度，单位px                           | String \| Number | 35                  | —                                      |          |
| customWrapStyle            | 自定义外框样式                         | Object           | —                   | —                                      | v1.0.20+ |
| customStyle                | 输入框的自定义样式                     | Object           | —                   | —                                      |          |
| clearCustomStyle           | 清除按钮自定义样式                     | Object           | —                   | —                                      | v1.0.22+ |
| cleanIcon                  | 右侧清除图标，尺寸16x16                | Object           | 默认图标            | {}                                     |          |
| eyesOnImg                  | 右侧眼睛显示图标，尺寸18x18            | String           | 默认图标            | —                                      |          |
| eyesUnImg                  | 右侧眼睛隐藏图标，尺寸18x18            | String           | 默认图标            | —                                      |          |
| showEyesIcon               | 密码类型时，是否显示右侧的眼睛显隐图标 | Boolean          | true                | true \| false                          |          |
| showClearIcon              | 是否显示右侧的清除图标                 | Boolean          | true                | true \| false                          | v1.0.35+ |
| clearIconNotNullAlwaysShow | 如果不为空，这一直显示清除图标         | Boolean          | false               | true \| false                          |          |
| inputAlign                 | 输入框文字的对齐方式                   | String           | left                | left/center/right                      |          |
| maxlength                  | 输入框的最大可输入长度                 | String \| Number | 140                 | —                                      |          |
| borderStyle                | 边框样式                               | String           | none                | none/border/bottom                     |          |
| borderRadius               | 边框圆角，单位px                       | String \| Number | 4                   | —                                      |          |
| borderColor                | 边框颜色                               | String           | rgba(0, 0, 0, 0.08) | —                                      |          |
| searchIcon                 | 搜索 icon 名称                         | String           | search              | —                                      | v1.0.20+ |
| searchIconSize             | 搜索 icon 大小，单位rpx                | Number \| String | 28                  | —                                      | v1.0.20+ |
| searchIconColor            | 搜索 icon 颜色                         | String           | #262F40             | —                                      | v1.0.20+ |
| searchText                 | 搜索按钮文字                           | String ｜ null   | 搜索                | —                                      | v1.0.20+ |
| searchTextSize             | 搜索按钮文字大小，单位rpx              | Number \| String | 28                  | —                                      | v1.0.20+ |
| searchTextColor            | 搜索按钮文字颜色                       | String           | #262F40             | —                                      | v1.0.20+ |
| searchCustomStyle          | 自定义搜索按钮样式                     | Object           | {}                  | —                                      | v1.0.20+ |
| precision                  | 精确度,type=price类型生效(小数位数)    | Number \| String | 2                   | —                                      | v1.0.32+ |
| separator                  | 千分符,type=price类型下生效            | String           | ,                   | —                                      | v1.0.32+ |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/input.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| blur                 | 输入框失去焦点时触发                                         | 输入后的值 |
| -------------------- | ------------------------------------------------------------ | ---------- |
| confirm              | 点击完成按钮时触发                                           | 输入后的值 |
| clear                | 点击清空触发                                                 | -          |
| input                | 输入时触发                                                   | 输入后的值 |
| focus                | 输入框聚焦时触发                                             | -          |
| search               | type为search时的右侧搜索事件                                 | 输入后的值 |
| keyboardheightchange | 键盘高度发生变化的时候触发此事件,微信小程序基础库2.7.0+、App 3.1.0+ | detail     |