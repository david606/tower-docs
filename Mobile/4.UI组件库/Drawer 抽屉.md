# [Drawer 抽屉](http://mid.chinatowercom.cn:18080/appGuide/ui/drawer.html#drawer-抽屉)

该组件组要对于需要临时展示内容，通过侧边栏的方式进行展示。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/drawer.html#基本使用)

- 通过`visible`参数设置是否显示*Drawer*，支持 **.sync** 修饰符
- 通过`size`参数设置*Drawer*大小

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
           
      <ct-ui-drawer :visible.sync="visible" size="50%">
        <view class="drawer-title">基本使用</view>
      </ct-ui-drawer>
      <ct-ui-button :btnWidth="120" @click="visible = true">打开</ct-ui-button>
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      visible: false
    }
  }
}
</script>

<style lang="scss">
.demo-page {
  .drawer-title {
    height: 60px;
    line-height: 60px;
    text-align: center;
    font-weight: bold;
  }
}
</style>
```

### [设置方向](http://mid.chinatowercom.cn:18080/appGuide/ui/drawer.html#设置方向)

- 通过`direction`参数设置抽屉打开方向

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="方向">
           
      <ct-ui-drawer :visible.sync="visible" :direction="direction">
        <view class="drawer-title">方向</view>
      </ct-ui-drawer>
      <ct-ui-checkbox
        :list="list"
        :choice="false"
        @checkboxClick="checkboxClick"
      ></ct-ui-checkbox>
      <ct-ui-button :btnWidth="120" @click="visible = true">打开</ct-ui-button>
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      visible: false,
      direction: 'left',
      list: [
        {
          title: '从左往右',
          id: 'left'
        },
        {
          title: '从右往左',
          id: 'right'
        },
        {
          title: '从上往下',
          id: 'top'
        },
        {
          title: '从下往上',
          id: 'bottom'
        }
      ]
    }
  },
  methods: {
    checkboxClick(list) {
      this.direction = list.id
    }
  }
}
</script>

<style lang="scss">
.demo-page {
  .drawer-title {
    height: 60px;
    line-height: 60px;
    text-align: center;
    font-weight: bold;
  }
}
</style>
```

### [嵌套使用](http://mid.chinatowercom.cn:18080/appGuide/ui/drawer.html#嵌套使用)

- 通过`visible`参数设置是否显示 Drawer，支持 **.sync** 修饰符

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="嵌套使用">
           
      <ct-ui-drawer :visible.sync="visible" size="70%">
        <view class="drawer-title">外层</view>
        <ct-ui-drawer :visible.sync="visible2" size="40%">
          <view class="drawer-title">内层</view>
        </ct-ui-drawer>
        <ct-ui-button :btnWidth="120" @click="visible2 = true"
          >打开</ct-ui-button
        >
      </ct-ui-drawer>
      <ct-ui-button :btnWidth="120" @click="visible = true">打开</ct-ui-button>
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      visible: false,
      visible2: false
    }
  }
}
</script>

<style lang="scss">
.demo-page {
  .drawer-title {
    height: 60px;
    line-height: 60px;
    text-align: center;
    font-weight: bold;
  }
}
</style>
```

### [自定义样式](http://mid.chinatowercom.cn:18080/appGuide/ui/drawer.html#自定义样式)

- 通过`drawerStyle`参数自定义*Drawer*样式

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义样式">
      <ct-ui-drawer
        :visible.sync="visible"
        :drawerStyle="drawerStyle"
      ></ct-ui-drawer>
      <ct-ui-button :btnWidth="120" @click="visible = true">打开</ct-ui-button>
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      visible: false,
      drawerStyle: {
        background: 'rgb(235, 75, 75)',
        width: '80px',
        borderRadius: '80px 0  0 80px'
      }
    }
  }
}
</script>

<style lang="scss">
.demo-page {
  .drawer-title {
    height: 60px;
    line-height: 60px;
    text-align: center;
    font-weight: bold;
  }
}
</style>
```

### [自定义遮罩层](http://mid.chinatowercom.cn:18080/appGuide/ui/drawer.html#自定义遮罩层)

- 通过`mask`参数设置是否打开遮罩层
- 通过`maskBgColor`参数设置遮罩层背景色
- 通过`maskLayer`参数设置是否开启点击遮罩层关闭

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义遮罩层">
           
      <ct-ui-drawer
        :visible.sync="visible"
        mask
        maskLayer
        maskBgColor="rgba(255,255,0,.6)"
      >
        <view class="drawer-title">自定义遮罩层</view>
        <ct-ui-button :btnWidth="120" @click="visible = false"
          >关闭</ct-ui-button
        >
      </ct-ui-drawer>
      <ct-ui-button :btnWidth="120" @click="visible = true">打开</ct-ui-button>
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      visible: false
    }
  }
}
</script>

<style lang="scss">
.demo-page {
  .drawer-title {
    height: 60px;
    line-height: 60px;
    text-align: center;
    font-weight: bold;
  }
}
</style>
```

### [动画曲线、时间](http://mid.chinatowercom.cn:18080/appGuide/ui/drawer.html#动画曲线、时间)

- 通过`duration`设置组件动画打开的时间
- 通过`curve`设置组件动画打开的曲线

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="动画曲线、时间">
           
      <ct-ui-drawer
        :visible.sync="visible"
        :duration="600"
        curve="cubic-bezier(1,.05,.31,1.39)"
      >
      </ct-ui-drawer>
      <ct-ui-button :btnWidth="120" @click="visible = true">打开</ct-ui-button>
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      visible: false
    }
  }
}
</script>

<style lang="scss">
.demo-page {
  .drawer-title {
    height: 60px;
    line-height: 60px;
    text-align: center;
    font-weight: bold;
  }
}
</style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/drawer.html#事件监听)

- 通过`open`事件监听组件打开即时触发
- 通过`opened`组件打开动画完毕后触发
- 通过`close`事件监听组件关闭即时触发
- 通过`closed`组件关闭动画完毕后触发

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="事件监听">
           
      <ct-ui-drawer
        :visible.sync="visible"
        @close="close"
        @closed="closed"
        @open="open"
        @opened="opened"
      >
      </ct-ui-drawer>
      <ct-ui-button :btnWidth="120" @click="visible = true">打开</ct-ui-button>
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      visible: false
    }
  },
  methods: {
    close() {
      console.log('close')
    },
    closed() {
      console.log('closed')
    },
    open() {
      console.log('open')
    },
    opened() {
      console.log('opened')
    }
  }
}
</script>

<style lang="scss">
.demo-page {
  .drawer-title {
    height: 60px;
    line-height: 60px;
    text-align: center;
    font-weight: bold;
  }
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/drawer.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/drawer.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| visible     | 是否显示 Drawer，支持 .sync 修饰符 | Boolean          | false          | true/false                     |
| ----------- | ---------------------------------- | ---------------- | -------------- | ------------------------------ |
| direction   | 抽屉方向                           | String           | right          | left \| right \| top \| bottom |
| size        | 大小                               | [String,Number]  | 50%            | -                              |
| duration    | 动画时长                           | Number           | 380            | -                              |
| curve       | 动画曲线                           | String           | ease-out       | -                              |
| drawerStyle | 内容样式                           | Object           | {}             | -                              |
| mask        | 是否开启遮罩层                     | Boolean          | true           | true/false                     |
| maskBgColor | 遮罩层背景色                       | String           | rgba(0,0,0,.2) | -                              |
| maskLayer   | 开启点击遮罩层关闭                 | Boolean          | true           | true/false                     |
| zIndex      | 弹出层的z-index值                  | Number \| String | 10             | -                              |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/drawer.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| open   | 组件打开即时触发       | -    |
| ------ | ---------------------- | ---- |
| opened | 组件打开动画完毕后触发 | -    |
| close  | 组件关闭即时触发       | -    |
| closed | 组件关闭动画完毕后触发 | -    |