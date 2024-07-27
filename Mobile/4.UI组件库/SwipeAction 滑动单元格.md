# [SwipeAction 滑动单元格](http://mid.chinatowercom.cn:18080/appGuide/ui/swipeAction.html#swipeaction-滑动单元格)

该组件

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/swipeAction.html#基本使用)

- 通过`text`参数设置滑块的文字内容
- 通过`options`参数设置单元格内容

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-swipe-action
        ref="swipeAction"
        text="单个按钮"
        :options="options1"
      />
      <ct-ui-swipe-action
        ref="swipeAction"
        text="多个按钮"
        :options="options2"
      />
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'swipeAction',
  data() {
    return {
      options1: [
        {
          text: '删除',
          style: {
            backgroundColor: '#ff2f2f'
          }
        }
      ],
      options2: [
        {
          text: '收藏',
          style: {
            backgroundColor: '#2a75ff'
          }
        },
        {
          text: '删除',
          style: {
            backgroundColor: '#ff2f2f'
          }
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [按钮位置](http://mid.chinatowercom.cn:18080/appGuide/ui/swipeAction.html#按钮位置)

- 通过`direction`属性设置单元格的所在位置

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="按钮位置">
         
      <ct-ui-swipe-action
        ref="swipeAction"
        text="左按钮，右滑动"
        :options="options"
        direction="left"
      />
      <ct-ui-swipe-action
        ref="swipeAction"
        text="右按钮，左滑动"
        :options="options"
        direction="right"
      />
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'swipeAction',
  data() {
    return {
      options: [
        {
          text: '收藏',
          style: {
            backgroundColor: '#2a75ff'
          }
        },
        {
          text: '删除',
          style: {
            backgroundColor: '#ff2f2f'
          }
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [设置 icon](http://mid.chinatowercom.cn:18080/appGuide/ui/swipeAction.html#设置-icon)

- 通过`options`对象数组中设置`icon`属性设置字体图标

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置icon">
      <ct-ui-swipe-action
        ref="swipeAction"
        text="设置icon"
        :options="options"
      />
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'swipeAction',
  data() {
    return {
      options: [
        {
          text: '收藏',
          style: {
            backgroundColor: '#2a75ff'
          },
          icon: {
            name: 'star',
            size: 17
          }
        },
        {
          text: '删除',
          style: {
            backgroundColor: '#ff2f2f'
          },
          icon: {
            name: 'delete',
            size: 17
          }
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [滑动阈值与时间](http://mid.chinatowercom.cn:18080/appGuide/ui/swipeAction.html#滑动阈值与时间)

- 通过`threshold`属性设置滑动阈值，滑动距离大于等于阈值则自动完成滑动操作，单位 px
- 通过`showTime`属性设置滑动打开单元格的时间，单位 ms
- 通过`hideTime`属性设置滑动关闭单元格的时间，单位 ms

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="滑动阈值与时间">
         
      <ct-ui-swipe-action
        ref="swipeAction"
        text="滑动大于20显示"
        :options="options"
        :threshold="20"
      />
      <ct-ui-swipe-action
        ref="swipeAction"
        text="滑动大于100显示"
        :options="options"
        :threshold="100"
      />
      <ct-ui-swipe-action
        ref="swipeAction"
        text="滑动时间为10ms"
        :options="options"
        :showTime="10"
        :hideTime="10"
      />
      <ct-ui-swipe-action
        ref="swipeAction"
        text="滑动时间为400ms"
        :options="options"
        :showTime="400"
        :hideTime="400"
      />
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'swipeAction',
  data() {
    return {
      options: [
        {
          text: '收藏',
          style: {
            backgroundColor: '#2a75ff'
          }
        },
        {
          text: '删除',
          style: {
            backgroundColor: '#ff2f2f'
          }
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [再确认提示框](http://mid.chinatowercom.cn:18080/appGuide/ui/swipeAction.html#再确认提示框)

- 通过`reconfirm`属性设置是否出现再确认提示框
- 通过`options`对象数组中设置`reconfirm`属性单独设置是否出现确认提示框
- 通过`options`对象数组中设置`tips`属性设置提示文字

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="再确认提示框">
      <ct-ui-swipe-action
        ref="swipeAction"
        text="显示提示框"
        :reconfirm="true"
        :options="options"
        :threshold="20"
      />
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'swipeAction',
  data() {
    return {
      options: [
        {
          text: '收藏',
          reconfirm: false,
          style: {
            backgroundColor: '#2a75ff'
          }
        },
        {
          text: '删除',
          reconfirm: true,
          tips: '确认删除吗',
          style: {
            backgroundColor: '#ff2f2f'
          }
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [使用插槽](http://mid.chinatowercom.cn:18080/appGuide/ui/swipeAction.html#使用插槽)

- 通过`slot`插槽，设置插槽内容自行进行使用
- 匿名插槽自定义设置滑动的文字内容
- 通过`section`自定义设置单元格的内容

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="使用插槽">
         
      <ct-ui-swipe-action>
        <view class="slot-text">使用插槽</view>
        <template slot="section">
          <view class="slot-section">
            <ct-ui-icon name="home"></ct-ui-icon>
          </view>
        </template>
      </ct-ui-swipe-action>
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'swipeAction',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss">
.slot-text {
  line-height: 40px;
  background-color: #f56c6c;
}
.slot-section {
  display: flex;
  flex-direction: column;
  justify-content: center;
  background-color: #007aff;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  margin: 0 5px;
  color: #ffffff;
}
</style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/swipeAction.html#事件监听)

`slideStart`事件可以监听开始滑动时触发，`click`事件可以监听单元格点击时触发，`opening`事件可以监听滑块打开前触发，`open`事件可以监听滑块打开时触发，`closing`事件可以监听滑块关闭前触发

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="事件监听">
      <ct-ui-swipe-action
        ref="swipeAction"
        text="单个按钮"
        :reconfirm="true"
        :options="options"
        @slideStart="slideStart"
        @open="open"
        @close="close"
        @closing="closing"
        @opening="opening"
        @click="click"
        @confirm="confirm"
      />
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'swipeAction',
  data() {
    return {
      options: [
        {
          text: '收藏',
          style: {
            backgroundColor: '#2a75ff'
          }
        },
        {
          text: '删除',
          style: {
            backgroundColor: '#ff2f2f'
          }
        }
      ]
    }
  },
  methods: {
    slideStart(item) {
      console.log(item)
    },
    click(e, i) {
      console.log(e, i)
    },
    open() {
      console.log('打开')
    },
    close() {
      console.log('关闭')
    },
    opening() {
      console.log('打开前')
    },
    closing() {
      console.log('关闭前')
    },
    confirm(e, item, i) {
      console.log('确认')
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/swipeAction.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/swipeAction.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| text      | 文字内容             | [String,Numebr] |       | -          |
| --------- | -------------------- | --------------- | ----- | ---------- |
| options   | 单元格内容           | Array           | []    | -          |
| disabled  | 是否禁用             | Boolean         | false | true/false |
| direction | 单元格所在位置       | String          | right | left/right |
| threshold | 滑动阈值，单位px     | Number          | 30    | -          |
| showTime  | 显示滑动时间，单位ms | Number          | 100   | -          |
| hideTime  | 隐藏滑动时间，单位ms | Number          | 100   | -          |
| reconfirm | 是否出现再确认提示框 | Boolean         | false | true/false |
| bgColor   | 背景色               | String          | #FFF  | -          |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/swipeAction.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| slideStart | 开始滑动时触发           | -                     |
| ---------- | ------------------------ | --------------------- |
| click      | 单元格点击时触发         | item,index            |
| opening    | 滑块打开前触发           | -                     |
| open       | 滑块打开时触发           | -                     |
| closing    | 滑块关闭前触发           | -                     |
| close      | 滑块关闭时触发           | -                     |
| confirm    | 确认提示框点击确认时触发 | 执行结果，item，index |

#### [Methods](http://mid.chinatowercom.cn:18080/appGuide/ui/swipeAction.html#methods)

| 名称 | 说明 | 所需参数 |
| ---- | ---- | -------- |
|      |      |          |

| close | 关闭单元格 |      |
| ----- | ---------- | ---- |
|       |            |      |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/swipeAction.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

|         | 滑块内容   |      |
| ------- | ---------- | ---- |
| section | 单元格内容 |      |