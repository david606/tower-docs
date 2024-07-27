# [Text 文本组件](http://mid.chinatowercom.cn:18080/appGuide/ui/text.html#text-文本组件)

该组件主要是对文本内容进行封装改造，使用户更加方便的对文本进行想要的展示效果

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/text.html#基本使用)

- 通过`content`参数传入文本内容
- 通过`type`参数设置文本颜色类型

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
          <ct-ui-text :content="content" />
      <ct-ui-text :content="content + '(primary)'" type="primary" />
      <ct-ui-text :content="content + '(success)'" type="success" />
      <ct-ui-text :content="content + '(warning)'" type="warning" />
      <ct-ui-text :content="content + '(info)'" type="info" />
      <ct-ui-text :content="content + '(error)'" type="error" />
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ctText',
  data() {
    return {
      content: '文本内容'
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [自定义样式](http://mid.chinatowercom.cn:18080/appGuide/ui/text.html#自定义样式)

- 通过`color`参数设置字体的颜色；
- 通过`size`参数设置字体的大小，单位 px；
- 通过`lingHeight`参数设置字体行高，单位 px；
- 通过`bold`设置是否开启字体加粗；
- 通过`letterSpacing`设置字体之间的间距，单位 px；

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
          <ct-ui-text :content="content" />
      <ct-ui-text :content="content" color="#F00" />
      <ct-ui-text :content="content" color="#F00" :size="24" />
      <ct-ui-text :content="content" color="#F00" :size="24" :lineHeight="48" />
      <ct-ui-text
        :content="content"
        color="#F00"
        :size="24"
        :lineHeight="48"
        :bold="true"
      />
      <ct-ui-text
        :content="content"
        color="#F00"
        :size="24"
        :lineHeight="48"
        :bold="true"
        :letterSpacing="15"
      />
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ctText',
  data() {
    return {
      content: '文本内容'
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [文本类型](http://mid.chinatowercom.cn:18080/appGuide/ui/text.html#文本类型)

- 通过`mode`参数设置文本类型，**text**为默认的文本类型、**phone**为手机号码，**url**为网络地址，**price**为金额类型，**date**为时间类型，**name**为姓名类型
- 通过`preg`参数传入正则表达式，自定义格式化文本
- 通过`format`参数传入函数，自定义格式化文本

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
         
      <view class="row">
        文本类型
        <ct-ui-text type="primary" :content="text" mode="text" />
      </view>
      <view class="row">
        手机号码
        <ct-ui-text type="primary" :content="phone" mode="phone" />
      </view>
      <view class="row">
        url类型
        <ct-ui-text type="primary" :content="url" mode="url" href="/" />
      </view>
      <view class="row">
        金额类型
        <ct-ui-text type="primary" :content="price" mode="price" />
      </view>
      <view class="row">
        时间类型
        <ct-ui-text type="primary" :content="date" mode="date" />
      </view>
      <view class="row">
        姓名类型
        <ct-ui-text type="primary" :content="name" mode="name" />
      </view>
      <view class="row">
        自定义正则表达式格式化文本
        <ct-ui-text type="primary" content="abc" :preg="preg" />
      </view>
      <view class="row">
        自定义函数格式化文本
        <ct-ui-text type="primary" content="abc" :format="format" />
      </view>
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ctText',
  data() {
    return {
      text: '文本类型',
      phone: '13300003333',
      url: 'url类型，设置href属性传入地址',
      price: '13300003333',
      date: '1646296691582',
      name: '王大锤',
      preg: [/^a+|a+$/g, 'A']
    }
  },
  methods: {
    format(item) {
      return item.toUpperCase()
    }
  }
}
</script>

<style scoped lang="scss">
.row {
  font-weight: 300;
  margin: 5px;
}
</style>
```

### [溢出处理](http://mid.chinatowercom.cn:18080/appGuide/ui/text.html#溢出处理)

通过`line`参数设置文本内容设置显示行数；通过`textOverflow`参数设置溢出文本处理方式，**clip**设置为裁剪，**ellipsis**设置为省略号

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="溢出处理">
         
      <view class="row">
        溢出裁剪
        <ct-ui-text :content="content" :line="2" textOverflow="clip" />
      </view>
      <view class="row">
        溢出省略号显示
        <ct-ui-text :content="content" :line="2" textOverflow="ellipsis" />
      </view>
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ctText',
  data() {
    return {
      content:
        '文本内容文本内容文本内容文本内容文本内容文本内容文本内容文本内容文本内容文本内容文本内容文本内容文本内容文本内容文本内容文本内容文本内容文本内容文本内容文本内容文本内容'
    }
  }
}
</script>

<style scoped lang="scss">
.row {
  font-weight: bold;
  margin: 5px;
}
</style>
```

### [文本图标](http://mid.chinatowercom.cn:18080/appGuide/ui/text.html#文本图标)

通过`prefixIcon`参数文本前图标，通过`suffixIcon`参数文本前图标，具体参数参考**Icon**组件

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="文本图标">
          <ct-ui-text content="文本前图标" :prefixIcon="prefixIcon" />
      <ct-ui-text content="文本后图标" :suffixIcon="suffixIcon" />
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ctText',
  data() {
    return {
      prefixIcon: {
        name: 'home',
        size: 24
      },
      suffixIcon: {
        name: 'home-fill',
        size: 24
      }
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [自定义打开方式](http://mid.chinatowercom.cn:18080/appGuide/ui/text.html#自定义打开方式)

通过`openType`设置自定义打开方式（仅小程序支持），**getPhoneNumber**：获取用户手机号回调，**getuserinfo**：返回获取到的用户信息，**error**：当使用开放能力时，发生错误的回调，**opensetting**：在打开授权设置页并关闭后回调，**launchapp**：从小程序打开 App 成功的回调

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义打开方式">
          <ct-ui-text content="打开“意见反馈”页面" openType="feedback" />
      <ct-ui-text content="触发用户转发" openType="share" />
      <ct-ui-text
        content="获取用户手机号"
        openType="getPhoneNumber"
        @getPhoneNumber="getPhoneNumber"
      />
      <ct-ui-text
        content="返回获取到的用户信息，"
        openType="getuserinfo"
        @getuserinfo="getuserinfo"
      />
      <ct-ui-text content="发生错误的回调" openType="error" @error="error" />
      <ct-ui-text
        content="打开授权设置页并关闭后回调，"
        openType="opensetting"
        @opensetting="opensetting"
      />
      <ct-ui-text
        content="从小程序打开 App 成功的回调"
        openType="launchapp"
        @launchapp="launchapp"
      />
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'ctText',
  data() {
    return {
      prefixIcon: {
        name: 'home',
        size: 24
      },
      suffixIcon: {
        name: 'home-fill',
        size: 24
      }
    }
  },
  methods: {
    getPhoneNumber(item) {
      console.log(item)
    },
    getuserinfo(item) {
      console.log(item)
    },
    error(item) {
      console.log(item)
    },
    opensetting(item) {
      console.log(item)
    },
    launchapp(item) {
      console.log(item)
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/text.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/text.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| *content（必传） | 文本内容                       | String\|Number |          | -                                              |                         |
| ---------------- | ------------------------------ | -------------- | -------- | ---------------------------------------------- | ----------------------- |
| type             | 颜色类型                       | String         |          | primary \| success \| warning \| info \| error |                         |
| color            | 自定义颜色                     | String         |          |                                                |                         |
| size             | 字体大小，单位px               | Number\|String | 14       | -                                              | v1.0.14+ 支持String类型 |
| mode             | 自定义文本类型                 | String         | text     | text \| phone \| url \| price \| date \| name  |                         |
| href             | 当mode为url的时候的跳转地址    | String         |          | -                                              |                         |
| whiteSpace       | 开启不换行                     | Boolean        | false    | true/false                                     |                         |
| bold             | 开启加粗                       | Boolean        | false    | true/false                                     |                         |
| textAlign        | 对齐方式                       | String         | left     | left \| center \| right                        |                         |
| margin           | 间距，单位px                   | Array\|Number  |          | -                                              |                         |
| lineHeight       | 字体行高，单位px               | Number\|String | 28       | -                                              | v1.0.14+ 支持String类型 |
| line             | 显示行数                       | Number         |          | -                                              |                         |
| textOverflow     | 溢出文本处理方式               | String         | ellipsis | clip（裁剪），ellipsis（省略号）               |                         |
| letterSpacing    | 字体间距，单位px               | Number         |          | -                                              |                         |
| precision        | 保留几位小数                   | Number         | 2        | -                                              |                         |
| rounding         | 小数是否开启四舍五入           | Boolean        | false    | true\|false                                    |                         |
| unit             | 单位                           | String         |          | -                                              |                         |
| unitPosition     | 单位显示位置                   | String         |          | prefix \| suffix                               |                         |
| format           | 使用函数自定义格式文本         | Function       |          | -                                              |                         |
| preg             | 使用正则表达式自定义格式文本   | Array          | []       | -                                              |                         |
| prefixIcon       | 文本前图标                     | Object         | {}       | -                                              |                         |
| suffixIcon       | 文本后图标                     | Object         | {}       | -                                              |                         |
| openType         | 自定义打开方式（仅小程序至此） | String         |          | -                                              |                         |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/text.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| click           | 文本点击时触发                         | 文本内容                         |
| --------------- | -------------------------------------- | -------------------------------- |
| prefixIconClick | 前图标点击时触发                       | -                                |
| suffixIconClick | 后图标点击时触发                       | -                                |
| getPhoneNumber  | openType设置为getPhoneNumber时点击触发 | 获取用户手机号回调               |
| getuserinfo     | openType设置为getuserinfo时点击触发    | 返回获取到的用户信息             |
| error           | openType设置为error时点击触发          | 当使用开放能力时，发生错误的回调 |
| opensetting     | openType设置为opensetting时点击触发    | 在打开授权设置页并关闭后回调     |
| launchapp       | openType设置为launchapp时点击触发      | 从小程序打开 App 成功的回调      |