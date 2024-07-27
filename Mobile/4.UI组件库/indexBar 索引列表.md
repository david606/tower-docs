# [indexBar 索引列表](http://mid.chinatowercom.cn:18080/appGuide/ui/indexBar.html#indexbar-索引列表)

该组件主要是对列表进行索引分类，可以根据索引快速的滑动到对应的内容模块，类似手机的通讯录。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/indexBar.html#基本使用)

- 通过`list`参数传入需要展示的数组，数组的结构需要按照规定的格式才能正常使用
- 通过`scrollTop`参数传入当前页面活动数值，通过调用页面生命周期 onPageScroll，监听页面滚动，参数为 Object，需要将 scrollTop 属性传递给组件

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-index-bar
        ref="indexBar"
        :list="list"
        :scrollTop="scrollTop"
      ></ct-ui-index-bar>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'indexBar',
  data() {
    return {
      list: [
        {
          letter: 'A',
          data: [
            {id: 'A1', title: '张三'},
            {id: 'A2', title: '李四'},
            {id: 'A3', title: '王五'}
          ]
        },
        {
          letter: 'B',
          data: [
            {id: 'B1', title: '张三'},
            {id: 'B2', title: '李四'},
            {id: 'B3', title: '王五'}
          ]
        },
        {
          letter: 'C',
          data: [
            {id: 'C1', title: '张三'},
            {id: 'C2', title: '李四'},
            {id: 'C3', title: '王五'}
          ]
        },
        {
          letter: 'V',
          data: [
            {id: 'V1', title: '张三'},
            {id: 'V2', title: '李四'},
            {id: 'V3', title: '王五'}
          ]
        },
        {
          letter: 'W',
          data: [
            {id: 'W1', title: '张三'},
            {id: 'W2', title: '李四'},
            {id: 'W3', title: '王五'}
          ]
        },
        {
          letter: 'Z',
          data: [
            {id: 'Z1', title: '张三'},
            {id: 'Z2', title: '李四'},
            {id: 'Z3', title: '王五'}
          ]
        },
        {
          letter: '#',
          data: [
            {id: '#1', title: '张三'},
            {id: '#2', title: '李四'},
            {id: '#3', title: '王五'}
          ]
        }
      ],
      scrollTop: 0
    }
  },
  onPageScroll(e) {
    this.scrollTop = e.scrollTop
  }
}
</script>

<style scoped lang="scss"></style>
```

### [自定义样式](http://mid.chinatowercom.cn:18080/appGuide/ui/indexBar.html#自定义样式)

通过`activeCenStyle`属性设置当前预览内容样式，通过`cenStyle`属性设置基本内容样式，通过`activeBarStyle`属性设置当前阅览对应侧边索引栏样式

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义样式">
      <ct-ui-index-bar
        ref="indexBar"
        :list="list"
        :scrollTop="scrollTop"
        :activeCenStyle="activeCenStyle"
        :cenStyle="cenStyle"
        :activeBarStyle="activeBarStyle"
      ></ct-ui-index-bar>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'indexBar',
  data() {
    return {
      list: [
        {
          letter: 'A',
          data: [
            {id: 'A1', title: '张三'},
            {id: 'A2', title: '李四'},
            {id: 'A3', title: '王五'}
          ]
        },
        {
          letter: 'B',
          data: [
            {id: 'B1', title: '张三'},
            {id: 'B2', title: '李四'},
            {id: 'B3', title: '王五'}
          ]
        },
        {
          letter: 'C',
          data: [
            {id: 'C1', title: '张三'},
            {id: 'C2', title: '李四'},
            {id: 'C3', title: '王五'}
          ]
        },
        {
          letter: 'V',
          data: [
            {id: 'V1', title: '张三'},
            {id: 'V2', title: '李四'},
            {id: 'V3', title: '王五'}
          ]
        },
        {
          letter: 'W',
          data: [
            {id: 'W1', title: '张三'},
            {id: 'W2', title: '李四'},
            {id: 'W3', title: '王五'}
          ]
        },
        {
          letter: 'Z',
          data: [
            {id: 'Z1', title: '张三'},
            {id: 'Z2', title: '李四'},
            {id: 'Z3', title: '王五'}
          ]
        },
        {
          letter: '#',
          data: [
            {id: '#1', title: '张三'},
            {id: '#2', title: '李四'},
            {id: '#3', title: '王五'}
          ]
        }
      ],
      scrollTop: 0,
      activeBarStyle: {
        color: '#aaffff'
      },
      activeCenStyle: {
        backgroundColor: '#27ffd1',
        height: '300px'
      },
      cenStyle: {
        height: '300px'
      }
    }
  },
  onPageScroll(e) {
    this.scrollTop = e.scrollTop
  }
}
</script>

<style scoped lang="scss"></style>
```

### [整体调整](http://mid.chinatowercom.cn:18080/appGuide/ui/indexBar.html#整体调整)

通过`barTop`参数设置索引列表距离顶部的距离，通过`zIndex`参数设置侧边索引栏层级，通过`duration`参数设置点击侧边索引栏时的过渡时间，单位 ms，通过`topDistance`参数设置当前预览内容块离上一个内容部分的距离才会有高亮显示

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="整体调整">
      <ct-ui-index-bar
        ref="indexBar"
        :list="list"
        :scrollTop="scrollTop"
        :activeCenStyle="activeCenStyle"
        :cenStyle="cenStyle"
        barTop="80px"
        :zIndex="1"
        :duration="1000"
        :topDistance="60"
      ></ct-ui-index-bar>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'indexBar',
  data() {
    return {
      list: [
        {
          letter: 'A',
          data: [
            {id: 'A1', title: '张三'},
            {id: 'A2', title: '李四'},
            {id: 'A3', title: '王五'}
          ]
        },
        {
          letter: 'B',
          data: [
            {id: 'B1', title: '张三'},
            {id: 'B2', title: '李四'},
            {id: 'B3', title: '王五'}
          ]
        },
        {
          letter: 'C',
          data: [
            {id: 'C1', title: '张三'},
            {id: 'C2', title: '李四'},
            {id: 'C3', title: '王五'}
          ]
        },
        {
          letter: 'V',
          data: [
            {id: 'V1', title: '张三'},
            {id: 'V2', title: '李四'},
            {id: 'V3', title: '王五'}
          ]
        },
        {
          letter: 'W',
          data: [
            {id: 'W1', title: '张三'},
            {id: 'W2', title: '李四'},
            {id: 'W3', title: '王五'}
          ]
        },
        {
          letter: 'Z',
          data: [
            {id: 'Z1', title: '张三'},
            {id: 'Z2', title: '李四'},
            {id: 'Z3', title: '王五'}
          ]
        },
        {
          letter: '#',
          data: [
            {id: '#1', title: '张三'},
            {id: '#2', title: '李四'},
            {id: '#3', title: '王五'}
          ]
        }
      ],
      scrollTop: 0,
      activeCenStyle: {
        backgroundColor: '#27ffd1',
        height: '300px'
      },
      cenStyle: {
        height: '300px'
      }
    }
  },
  onPageScroll(e) {
    this.scrollTop = e.scrollTop
  }
}
</script>

<style scoped lang="scss"></style>
```

### [调用功能](http://mid.chinatowercom.cn:18080/appGuide/ui/indexBar.html#调用功能)

通过绑定`ref`进行手动调用组件上的功能

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="数组转换">
      <ct-ui-button @click="useSort">点击转换</ct-ui-button>
      <ct-ui-index-bar
        ref="indexBar"
        :list="list"
        :scrollTop="scrollTop"
        :activeCenStyle="activeCenStyle"
        :cenStyle="cenStyle"
      ></ct-ui-index-bar>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'indexBar',
  data() {
    return {
      oList: [
        {id: 'A1', title: '张三'},
        {id: 'A2', title: '李四'},
        {id: 'A3', title: '王五'},
        {id: 'W1', title: '张三'},
        {id: 'W2', title: '李四'},
        {id: 'W3', title: '王五'},
        {id: 'C1', title: '张三'},
        {id: 'C2', title: '李四'},
        {id: 'C3', title: '王五'},
        {id: 'V1', title: '张三'},
        {id: 'V2', title: '李四'},
        {id: 'V3', title: '王五'},
        {id: 'B1', title: '张三'},
        {id: 'B2', title: '李四'},
        {id: 'B3', title: '王五'},
        {id: 'Z1', title: '张三'},
        {id: 'Z2', title: '李四'},
        {id: 'Z3', title: '王五'},
        {id: '#1', title: '张三'},
        {id: '#2', title: '李四'},
        {id: '#3', title: '王五'}
      ],
      list: [],
      scrollTop: 0,
      activeCenStyle: {
        backgroundColor: '#27ffd1',
        height: '300px'
      },
      cenStyle: {
        height: '300px'
      }
    }
  },
  onPageScroll(e) {
    this.scrollTop = e.scrollTop
  },
  methods: {
    useSort() {
      this.list = this.$refs.indexBar.ctSort(this.oList, 'id')
      console.log(this.list)
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/indexBar.html#事件监听)

`cutScroll`事件可以监听索引列表高亮颜色切换时触发，`getScroll`事件可以监听侧边索引栏点击或滑动时触发，`click`事件可以监听内容点击时触发

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="事件监听">
      <ct-ui-index-bar
        ref="indexBar"
        :list="list"
        :scrollTop="scrollTop"
        :activeCenStyle="activeCenStyle"
        :cenStyle="cenStyle"
        @cutScroll="cutScroll"
        @getScroll="getScroll"
        @click="click"
      ></ct-ui-index-bar>
             
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'indexBar',
  data() {
    return {
      list: [
        {
          letter: 'A',
          data: [
            {id: 'A1', title: '张三'},
            {id: 'A2', title: '李四'},
            {id: 'A3', title: '王五'}
          ]
        },
        {
          letter: 'B',
          data: [
            {id: 'B1', title: '张三'},
            {id: 'B2', title: '李四'},
            {id: 'B3', title: '王五'}
          ]
        },
        {
          letter: 'C',
          data: [
            {id: 'C1', title: '张三'},
            {id: 'C2', title: '李四'},
            {id: 'C3', title: '王五'}
          ]
        },
        {
          letter: 'V',
          data: [
            {id: 'V1', title: '张三'},
            {id: 'V2', title: '李四'},
            {id: 'V3', title: '王五'}
          ]
        },
        {
          letter: 'W',
          data: [
            {id: 'W1', title: '张三'},
            {id: 'W2', title: '李四'},
            {id: 'W3', title: '王五'}
          ]
        },
        {
          letter: 'Z',
          data: [
            {id: 'Z1', title: '张三'},
            {id: 'Z2', title: '李四'},
            {id: 'Z3', title: '王五'}
          ]
        },
        {
          letter: '#',
          data: [
            {id: '#1', title: '张三'},
            {id: '#2', title: '李四'},
            {id: '#3', title: '王五'}
          ]
        }
      ],
      scrollTop: 0,
      activeCenStyle: {
        backgroundColor: '#27ffd1',
        height: '300px'
      },
      cenStyle: {
        height: '300px'
      }
    }
  },
  onPageScroll(e) {
    this.scrollTop = e.scrollTop
  },
  methods: {
    cutScroll(item) {
      console.log(item)
    },
    click(item) {
      console.log(item)
    },
    getScroll(letter, event, mode) {
      console.log(letter, event, mode)
    }
  }
}
</script>

<style scoped lang="scss"></style>
```

### [使用插槽](http://mid.chinatowercom.cn:18080/appGuide/ui/indexBar.html#使用插槽)

通过`slot`插槽，设置插槽内容自行进行使用

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="使用插槽">
      <ct-ui-index-bar
        ref="indexBar"
        :list="list"
        :scrollTop="scrollTop"
        :activeCenStyle="activeCenStyle"
      >
        <template v-slot:cenHead="{item}">
          <view class="useCenHead">{{ item.letter }}</view>
        </template>
        <template v-slot:content="{item}">
          <view class="useContent" @click="useClick(item)">{{
            item.title
          }}</view>
        </template>
        <template v-slot:bar="{item}">
          <view class="usebar">{{ item.letter }}</view>
        </template>
      </ct-ui-index-bar>
       
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'indexBar',
  data() {
    return {
      list: [
        {
          letter: 'A',
          data: [
            {id: 'A1', title: '张三'},
            {id: 'A2', title: '李四'},
            {id: 'A3', title: '王五'}
          ]
        },
        {
          letter: 'B',
          data: [
            {id: 'B1', title: '张三'},
            {id: 'B2', title: '李四'},
            {id: 'B3', title: '王五'}
          ]
        },
        {
          letter: 'C',
          data: [
            {id: 'C1', title: '张三'},
            {id: 'C2', title: '李四'},
            {id: 'C3', title: '王五'}
          ]
        },
        {
          letter: 'V',
          data: [
            {id: 'V1', title: '张三'},
            {id: 'V2', title: '李四'},
            {id: 'V3', title: '王五'}
          ]
        },
        {
          letter: 'W',
          data: [
            {id: 'W1', title: '张三'},
            {id: 'W2', title: '李四'},
            {id: 'W3', title: '王五'}
          ]
        },
        {
          letter: 'Z',
          data: [
            {id: 'Z1', title: '张三'},
            {id: 'Z2', title: '李四'},
            {id: 'Z3', title: '王五'}
          ]
        },
        {
          letter: '#',
          data: [
            {id: '#1', title: '张三'},
            {id: '#2', title: '李四'},
            {id: '#3', title: '王五'}
          ]
        }
      ],
      scrollTop: 0,
      activeCenStyle: {
        backgroundColor: '#3C9CFF'
      }
    }
  },
  onPageScroll(e) {
    this.scrollTop = e.scrollTop
  },
  methods: {
    useClick(item) {
      console.log(item)
    }
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  .title {
    padding: 20px;
  }

  .useCenHead {
    padding: 20px 10px;
    background-color: #5ac725;
  }

  .useContent {
    padding: 10px;
    border: 3px solid #000000;
    border-radius: 40rpx;
    margin: 10rpx;
  }

  .usebar {
  }
}
</style>
```

### [注意事项](http://mid.chinatowercom.cn:18080/appGuide/ui/indexBar.html#注意事项)

- 必须要传`scrollTop`参数，由于`scroll-view`的性能优化问题不适合放长列表，所以使用页面生命周期`onPageScroll`监听页面滚动，因为`onPageScroll`为页面生命周期，组件内部无法调用，所以需要将`scrollTop`参数传递给组件，监听页面滚动，参数为**Object**，需要将`scrollTop`属性传递给组件

```vue
<script>
export default {
  name: 'indexBar',
  data() {
    return {
      scrollTop: 0
    }
  },
  onPageScroll(e) {
    this.scrollTop = e.scrollTop
  }
}
</script>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/indexBar.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/indexBar.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| *list（必传）      | 索引列表所需数组                                   | Array  | []              | [{letter:"",data:[]}] |
| ------------------ | -------------------------------------------------- | ------ | --------------- | --------------------- |
| *scrollTop（必传） | 滑动事件传递的距离                                 | Number | 0               | -                     |
| zIndex             | 侧边栏层级                                         | Number | 1               | -                     |
| duration           | 滚动时间，单位ms                                   | Number | 300             | -                     |
| topDistance        | 内容块离上一个内容部分的距离才会有高亮显示，单位px | Number | 40              | -                     |
| activeCenStyle     | 当前预览内容样式                                   | Object | {}              | -                     |
| cenStyle           | 基本内容样式                                       | Object | {}              | -                     |
| activeBarStyle     | 当前阅览对应侧边索引栏样式                         | Object | {color: "#f00"} | -                     |
| barTop             | 索引列表距离顶部的高度                             | String | 0px             | -                     |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/indexBar.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| cutScroll | 索引列表高亮颜色切换时触发 | 索引列表高亮的内容                                           |
| --------- | -------------------------- | ------------------------------------------------------------ |
| getScroll | 侧边索引栏点击或滑动时触发 | letter（当前索引内容对应letter）,event（滚动结束的回调）,mode（触发方式） |
| click     | 事件可以监听内容点击时触发 | 点击的内容对象                                               |

#### [Methods](http://mid.chinatowercom.cn:18080/appGuide/ui/indexBar.html#methods)

| 名称 | 说明 | 所需参数 |
| ---- | ---- | -------- |
|      |      |          |

| ctSort | 将数组改造并返回索引列表所需格式 | list（传入的对象数组）,attr（根据哪个属性的值进行分类） |
| ------ | -------------------------------- | ------------------------------------------------------- |
|        |                                  |                                                         |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/indexBar.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

| cenHead | 自定义列表内容块标题 | item |
| ------- | -------------------- | ---- |
| content | 自定义列表内容       | item |
| bar     | 自定义侧边索引栏     | item |