# [Drag 拖拽排序](http://mid.chinatowercom.cn:18080/appGuide/ui/drag.html#drag-拖拽排序)

该组件通过长按拖拽操作，让用户能够自主对数组顺序自行调整

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/drag.html#基本使用)

- 通过`list`属性设置数据列表

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
       
      <ct-ui-drag :list="list">
        <template v-slot="{item}">
          <view class="demo-drag">
            {{ item.title }}
          </view>
        </template>
      </ct-ui-drag>
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      list: []
    }
  },
  created() {
    for (let i = 1; i < 6; i++) {
      this.list.push({
        nodeName: i,
        title: i
      })
    }
  }
}
</script>
<style lang="scss">
.demo-page {
  .demo-row-title {
    padding: 20rpx;
  }
  .demo-drag {
    border-radius: 28rpx;
    text-align: center;
    font-size: 26px;
    background-color: rgb(235, 75, 75);
    margin: 8rpx;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 150rpx;

    &__text {
      color: #fff;
    }
  }
}
</style>
```

### [拖拽模式](http://mid.chinatowercom.cn:18080/appGuide/ui/drag.html#拖拽模式)

- 通过`mode`属性设置拖拽排序的模式，分别为`list`列表模式、`grid`宫格模式
- 通过`column`属性设置`grid`宫格模式下的每行数量

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="列表模式">
      <ct-ui-drag :list="list" mode="list">
        <template v-slot="{item}">
          <view class="demo-drag">
            {{ item.title }}
          </view>
        </template>
      </ct-ui-drag>
      <view class="demo-row-title">宫格模式</view>
      <ct-ui-drag :list="grid" mode="grid">
        <template v-slot="{item}">
          <view class="demo-drag">
            {{ item.title }}
          </view>
        </template>
      </ct-ui-drag>
         
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      list: [],
      grid: []
    }
  },
  created() {
    for (let i = 1; i < 4; i++) {
      this.list.push({
        nodeName: i,
        title: i
      })
    }
    for (let i = 1; i < 13; i++) {
      this.grid.push({
        nodeName: i,
        title: i
      })
    }
  }
}
</script>
<style lang="scss">
.demo-page {
  .demo-row-title {
    padding: 20rpx;
  }
  .demo-drag {
    border-radius: 28rpx;
    text-align: center;
    font-size: 26px;
    background-color: rgb(235, 75, 75);
    margin: 8rpx;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 150rpx;

    &__text {
      color: #fff;
    }
  }
}
</style>
```

### [拖拽抖动效果](http://mid.chinatowercom.cn:18080/appGuide/ui/drag.html#拖拽抖动效果)

- 通过`shaking`属性设置`grid`宫格模式下开启拖拽抖动效果

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="拖拽抖动效果">
           
      <ct-ui-drag :list="list" mode="grid" shaking>
        <template v-slot="{item}">
          <view class="demo-drag">
            {{ item.title }}
          </view>
        </template>
      </ct-ui-drag>
         
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      list: []
    }
  },
  created() {
    for (let i = 1; i < 13; i++) {
      this.list.push({
        nodeName: i,
        title: i
      })
    }
  }
}
</script>
<style lang="scss">
.demo-page {
  .demo-row-title {
    padding: 20rpx;
  }
  .demo-drag {
    border-radius: 28rpx;
    text-align: center;
    font-size: 26px;
    background-color: rgb(235, 75, 75);
    margin: 8rpx;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 150rpx;

    &__text {
      color: #fff;
    }
  }
}
</style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/drag.html#事件监听)

-`open`事件监听拖拽时触发 -`close`事件监听停止时触发 -`move`事件监听停止时触发并返回移动后列表 -`disabled`事件监听移动禁用的对象时触发

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="事件监听">
           
      <ct-ui-drag
        :list="list"
        mode="grid"
        shaking
        @open="open"
        @close="close"
        @move="move"
        @disabled="disabled"
      >
        <template v-slot="{item}">
          <view class="demo-drag">
            {{ item.title }}
          </view>
        </template>
      </ct-ui-drag>
         
    </ct-demo-card>
  </view>
</template>
<script>
export default {
  data() {
    return {
      list: []
    }
  },
  created() {
    for (let i = 1; i < 13; i++) {
      this.list.push({
        nodeName: i,
        title: i
      })
    }
  },
  methods: {
    open() {
      console.log('开始移动')
    },
    close() {
      console.log('停止移动')
    },
    move(list) {
      console.log('移动后的数组', list)
    },
    disabled(e) {
      console.log('禁用对象', e)
    }
  }
}
</script>
<style lang="scss">
.demo-page {
  .demo-row-title {
    padding: 20rpx;
  }
  .demo-drag {
    border-radius: 28rpx;
    text-align: center;
    font-size: 26px;
    background-color: rgb(235, 75, 75);
    margin: 8rpx;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 150rpx;

    &__text {
      color: #fff;
    }
  }
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/drag.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/drag.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| list    | 数据列表                     | Array         | []    | -            |
| ------- | ---------------------------- | ------------- | ----- | ------------ |
| mode    | 拖拽模式，分为列表\|宫格模式 | String        | list  | list \| grid |
| column  | mode=grid，每行宫格数量      | Number        | 4     | -            |
| shaking | mode=grid，拖拽抖动效果      | Number,String |       | -            |
| disable | 是否禁用                     | Boolean       | false | true/false   |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/drag.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| open     | 开始移动时触发       | -          |
| -------- | -------------------- | ---------- |
| close    | 停止移动时触发       | -          |
| move     | 停止移动时触发       | 移动后列表 |
| disabled | 移动禁用的对象时触发 | 移动的对象 |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/drag.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

|      | 自定义列表内容 | item, index |
| ---- | -------------- | ----------- |
|      |                |             |