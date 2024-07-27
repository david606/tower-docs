# 

该组件主要在数据进行展示，图片高度不同时的场景下时使用

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/waterfalls.html#基本使用)

- 通过`list`参数设置传入展示数据
- 通过`gutter`参数设置间距

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
             
      <ct-ui-waterfalls :list="list" gutter="4">
        <template v-slot="{item}">
          <view class="demo-row-waterfalls" :class="item.class">
            {{ item.id }}
          </view>
        </template>
      </ct-ui-waterfalls>
             
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      list: [
        {id: 1, class: 'h4'},
        {id: 2, class: 'h2'},
        {id: 3, class: 'h1'},
        {id: 4, class: 'h3'},
        {id: 5, class: 'h2'},
        {id: 6, class: 'h5'},
        {id: 7, class: 'h6'},
        {id: 8, class: 'h1'},
        {id: 9, class: 'h4'},
        {id: 10, class: 'h2'}
      ]
    }
  }
}
</script>

<style lang="scss">
.demo-row-waterfalls {
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 24px;
  font-weight: bold;
  color: #fff;
}
@for $i from 1 through 9 {
  .h#{$i} {
    height: $i * 100 + rpx;
    background-color: rgb(235, 75, 75);
  }
}
</style>
```

### [设置行数](http://mid.chinatowercom.cn:18080/appGuide/ui/waterfalls.html#设置行数)

- 通过`col`参数设置行数量

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置行数">
             
      <ct-ui-waterfalls :list="list" gutter="4" :col="3">
        <template v-slot="{item}">
          <view class="demo-row-waterfalls" :class="item.class">
            {{ item.id }}
          </view>
        </template>
      </ct-ui-waterfalls>
             
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      list: [
        {id: 1, class: 'h4'},
        {id: 2, class: 'h2'},
        {id: 3, class: 'h1'},
        {id: 4, class: 'h3'},
        {id: 5, class: 'h2'},
        {id: 6, class: 'h5'},
        {id: 7, class: 'h6'},
        {id: 8, class: 'h1'},
        {id: 9, class: 'h4'},
        {id: 10, class: 'h2'}
      ]
    }
  }
}
</script>

<style lang="scss">
.demo-row-waterfalls {
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 24px;
  font-weight: bold;
  color: #fff;
}
@for $i from 1 through 9 {
  .h#{$i} {
    height: $i * 100 + rpx;
    background-color: rgb(235, 75, 75);
  }
}
</style>
```

### [设置宽度](http://mid.chinatowercom.cn:18080/appGuide/ui/waterfalls.html#设置宽度)

- 通过`colWidth`参数设置每行宽度，优先级大于`col`

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置宽度">
             
      <ct-ui-waterfalls :list="list" gutter="4" :col="3" colWidth="50">
        <template v-slot="{item}">
          <view class="demo-row-waterfalls" :class="item.class">
            {{ item.id }}
          </view>
        </template>
      </ct-ui-waterfalls>
             
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      list: [
        {id: 1, class: 'h4'},
        {id: 2, class: 'h2'},
        {id: 3, class: 'h1'},
        {id: 4, class: 'h3'},
        {id: 5, class: 'h2'},
        {id: 6, class: 'h5'},
        {id: 7, class: 'h6'},
        {id: 8, class: 'h1'},
        {id: 9, class: 'h4'},
        {id: 10, class: 'h2'}
      ]
    }
  }
}
</script>

<style lang="scss">
.demo-row-waterfalls {
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 24px;
  font-weight: bold;
  color: #fff;
}
@for $i from 1 through 9 {
  .h#{$i} {
    height: $i * 100 + rpx;
    background-color: rgb(235, 75, 75);
  }
}
</style>
```

### [自定义插槽](http://mid.chinatowercom.cn:18080/appGuide/ui/waterfalls.html#自定义插槽)

通过插槽自定义设置内容

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义插槽">
             
      <ct-ui-waterfalls :list="list" gutter="4" :scrollTop="scrollTop" :col="2">
        <template v-slot="{item}">
          <view class="demo-box">
            <view class="demo-waterfalls" :class="item.class">
              <view class=""></view>
            </view>
            <view class="demo-content">
              <view class="demo-title">
                {{ item.id }}
              </view>
              <view class="demo-introduce"><view></view></view>
              <view class="demo-introduce"><view></view></view>
              <view class="demo-introduce"><view></view></view>
            </view>
          </view>
        </template>
      </ct-ui-waterfalls>
             
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      scrollTop: 0,
      list: [
        {id: 1, class: 'h4'},
        {id: 2, class: 'h2'},
        {id: 3, class: 'h1'},
        {id: 4, class: 'h3'},
        {id: 5, class: 'h2'},
        {id: 6, class: 'h5'},
        {id: 7, class: 'h6'},
        {id: 8, class: 'h1'},
        {id: 9, class: 'h4'},
        {id: 10, class: 'h2'}
      ]
    }
  },
  onPageScroll(e) {
    this.scrollTop = e.scrollTop
  },
  onReachBottom() {
    this.list.push(
      {id: this.list.length, class: 'h2'},
      {id: this.list.length + 1, class: 'h4'},
      {id: this.list.length + 2, class: 'h1'},
      {id: this.list.length + 3, class: 'h3'}
    )
  }
}
</script>

<style lang="scss">
.demo-box {
  background-color: #e3e3e3;
  border-radius: 14rpx;
  overflow: hidden;
  .demo-waterfalls {
    padding: 16rpx;
    background-color: #e3e3e3;
    view {
      width: 100%;
      height: 100%;
      border-radius: 8rpx;
      background-color: #c6c6c6;
    }
  }
  .demo-content {
    .demo-title {
      color: #fff;
      text-align: center;
      width: 40%;
      margin: 6rpx 10rpx;
      border-radius: 14rpx;
      background-color: #adadad;
    }
    .demo-introduce {
      width: 100%;
      box-sizing: border-box;
      padding: 10rpx;
      view {
        height: 30rpx;
        border-radius: 14rpx;
        background-color: #adadad;
      }
    }
  }
}
@for $i from 1 through 9 {
  .h#{$i} {
    height: $i * 100 + rpx;
    background-color: rgb(235, 75, 75);
  }
}
</style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/waterfalls.html#事件监听)

- `refresh`事件数据更新时触发
- `append`事件数据新增时触发
- `clear`事件数据清空时触发

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="事件监听">
             
      <ct-ui-waterfalls
        :list="list"
        gutter="4"
        @refresh="refresh"
        @append="append"
        @clear="clear"
      >
        <template v-slot="{item}">
          <view class="demo-row-waterfalls" :class="item.class">
            {{ item.id }}
          </view>
        </template>
      </ct-ui-waterfalls>
             
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      list: [
        {id: 1, class: 'h4'},
        {id: 2, class: 'h2'},
        {id: 3, class: 'h1'},
        {id: 4, class: 'h3'},
        {id: 5, class: 'h2'},
        {id: 6, class: 'h5'},
        {id: 7, class: 'h6'},
        {id: 8, class: 'h1'},
        {id: 9, class: 'h4'},
        {id: 10, class: 'h2'}
      ]
    }
  },
  onReachBottom() {
    this.list.push(
      {id: this.list.length + 1, class: 'h3'},
      {id: this.list.length + 2, class: 'h4'}
    )
  },
  methods: {
    refresh() {
      console.log('refresh')
    },
    append(add) {
      console.log('append', add)
    },
    clear() {
      console.log('clear')
    }
  }
}
</script>

<style lang="scss">
.demo-row-waterfalls {
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 24px;
  font-weight: bold;
  color: #fff;
}
@for $i from 1 through 9 {
  .h#{$i} {
    height: $i * 100 + rpx;
    background-color: rgb(235, 75, 75);
  }
}
</style>
```

### [注意事项](http://mid.chinatowercom.cn:18080/appGuide/ui/waterfalls.html#注意事项)

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

### [加载优化](http://mid.chinatowercom.cn:18080/appGuide/ui/waterfalls.html#加载优化)

- 通过`scrollTop`参数设置当前滚动的距离，对长列表进行按需加载，缓解数据量过大加载慢，若不传入该参数，则直接渲染整个列表数据

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="加载优化">
             
      <ct-ui-waterfalls :list="list" gutter="4" :scrollTop="scrollTop" :col="2">
        <template v-slot="{item}">
          <view class="demo-box" @click="del(item.id)">
            <view class="demo-waterfalls">
              <view class="">
                <img :src="item.src" alt="" srcset="" />
              </view>
            </view>
            <view class="demo-content">
              <view class="demo-title">
                {{ item.id }}
              </view>
              <view class="demo-introduce"><view></view></view>
              <view class="demo-introduce"><view></view></view>
              <view class="demo-introduce"><view></view></view>
            </view>
          </view>
        </template>
      </ct-ui-waterfalls>
             
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      scrollTop: 0,
      list: [
        {
          id: 1,
          class: 'h2',
          src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fdingyue.ws.126.net%2F2020%2F0515%2F465567a6j00qadpfz001cc000hs00b4c.jpg&refer=http%3A%2F%2Fdingyue.ws.126.net&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657850597&t=44b39a43093f3e3cd679ae9ede0c7d2d'
        },
        {
          id: 2,
          class: 'h5',
          src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg.redocn.com%2Fsheying%2F20160718%2Fhaibianrichu_6697627.jpg&refer=http%3A%2F%2Fimg.redocn.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657850597&t=84a7a78a504e601781c4fee4b66222e5'
        },
        {
          id: 3,
          class: 'h4',
          src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fpic73.nipic.com%2Ffile%2F20150721%2F20518690_171315872000_2.jpg&refer=http%3A%2F%2Fpic73.nipic.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657850598&t=3f3e7d62763bf995b9600bb5e94093da'
        },
        {
          id: 4,
          class: 'h3',
          src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg.jj20.com%2Fup%2Fallimg%2Ftp05%2F1910021221064F5-0-lp.jpg&refer=http%3A%2F%2Fimg.jj20.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657850598&t=a0b710cc3eb7f75d10068999e1411a4b'
        },
        {
          id: 5,
          class: 'h5',
          src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg.jj20.com%2Fup%2Fallimg%2Ftp05%2F1Z930193913G04-0-lp.jpg&refer=http%3A%2F%2Fimg.jj20.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657850598&t=3f1a4455ae1600acbeeae3719691ceaa'
        },
        {
          id: 6,
          class: 'h3',
          src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Ftupian.qqjay.com%2Fu%2F2017%2F1020%2F1_14136_2.jpg&refer=http%3A%2F%2Ftupian.qqjay.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657850598&t=0ab8302e0359ed2da9fc1dd73d696b87'
        },
        {
          id: 7,
          class: 'h2',
          src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fdingyue.ws.126.net%2F2020%2F0515%2F465567a6j00qadpfz001cc000hs00b4c.jpg&refer=http%3A%2F%2Fdingyue.ws.126.net&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657850597&t=44b39a43093f3e3cd679ae9ede0c7d2d'
        },
        {
          id: 8,
          class: 'h5',
          src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg.redocn.com%2Fsheying%2F20160718%2Fhaibianrichu_6697627.jpg&refer=http%3A%2F%2Fimg.redocn.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657850597&t=84a7a78a504e601781c4fee4b66222e5'
        },
        {
          id: 9,
          class: 'h4',
          src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fpic73.nipic.com%2Ffile%2F20150721%2F20518690_171315872000_2.jpg&refer=http%3A%2F%2Fpic73.nipic.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657850598&t=3f3e7d62763bf995b9600bb5e94093da'
        },
        {
          id: 10,
          class: 'h3',
          src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg.jj20.com%2Fup%2Fallimg%2Ftp05%2F1910021221064F5-0-lp.jpg&refer=http%3A%2F%2Fimg.jj20.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657850598&t=a0b710cc3eb7f75d10068999e1411a4b'
        }
      ],
      id: 10
    }
  },
  onPageScroll(e) {
    this.scrollTop = e.scrollTop
  },
  onReachBottom() {
    this.list.push(
      {
        id: this.id + 1,
        class: 'h3',
        src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg.jj20.com%2Fup%2Fallimg%2Ftp05%2F1910021221064F5-0-lp.jpg&refer=http%3A%2F%2Fimg.jj20.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657850598&t=a0b710cc3eb7f75d10068999e1411a4b'
      },
      {
        id: this.id + 2,
        class: 'h4',
        src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Ftupian.qqjay.com%2Fu%2F2017%2F1020%2F1_14136_2.jpg&refer=http%3A%2F%2Ftupian.qqjay.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657850598&t=0ab8302e0359ed2da9fc1dd73d696b87'
      },
      {
        id: this.id + 3,
        class: 'h4',
        src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fdingyue.ws.126.net%2F2020%2F0515%2F465567a6j00qadpfz001cc000hs00b4c.jpg&refer=http%3A%2F%2Fdingyue.ws.126.net&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657850597&t=44b39a43093f3e3cd679ae9ede0c7d2d'
      },
      {
        id: this.id + 4,
        class: 'h4',
        src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fpic73.nipic.com%2Ffile%2F20150721%2F20518690_171315872000_2.jpg&refer=http%3A%2F%2Fpic73.nipic.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1657850598&t=3f3e7d62763bf995b9600bb5e94093da'
      }
    )
    this.id += 4
  }
}
</script>

<style lang="scss">
.demo-box {
  background-color: #e3e3e3;
  border-radius: 14rpx;
  overflow: hidden;
  .demo-waterfalls {
    padding: 16rpx;
    background-color: #e3e3e3;
    view {
      width: 100%;
      img {
        border-radius: 8rpx;
        overflow: hidden;
        width: 100%;
      }
    }
  }
  .demo-content {
    .demo-title {
      color: #fff;
      text-align: center;
      width: 40%;
      margin: 6rpx 10rpx;
      border-radius: 14rpx;
      background-color: #adadad;
    }
    .demo-introduce {
      width: 100%;
      box-sizing: border-box;
      padding: 10rpx;
      view {
        height: 30rpx;
        border-radius: 14rpx;
        background-color: #adadad;
      }
    }
  }
}
@for $i from 1 through 9 {
  .h#{$i} {
    height: $i * 100 + rpx;
    background-color: rgb(235, 75, 75);
  }
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/waterfalls.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/waterfalls.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| list               | 展示数据                           | Array         | []    | -          |
| ------------------ | ---------------------------------- | ------------- | ----- | ---------- |
| col                | 行数                               | Number        | 2     | -          |
| colWidth           | 自定义每行宽度，优先级大于col      | String,Number |       | —          |
| scrollTop          | 滑动事件传递的距离                 | Number        |       | —          |
| slideSize          | 滑动图片大小，单位px（mode=image） | String,Number | 50px  | —          |
| gutter             | 间距                               | Number,String |       | -          |
| transitionDuration | 过渡时间，单位ms                   | Number,String | 1000  | —          |
| fill               | 是否填充整个屏幕                   | Boolean       | false | true/false |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/waterfalls.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| refresh | 数组更新时触发 | -    |
| ------- | -------------- | ---- |
| append  | 数组增加时触发 | -    |
| clear   | 清除数据时触发 | -    |

### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/waterfalls.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

|      | 自定义内容 | item |
| ---- | ---------- | ---- |
|      |            |      |