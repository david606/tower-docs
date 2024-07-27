# [Draw 刷新列表](http://mid.chinatowercom.cn:18080/appGuide/ui/draw.html#draw-刷新列表)

该组件主要用于可刷新列表数据的展示。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/draw.html#基本使用)

- 通过`bgColor`参数设置背景色
- 通过`defaultPageSize`参数设置每页显示多少条
- 通过`refresherEnabled`参数控制是否开启头部下拉刷新
- 通过`loadingMoreEnabled`参数控制是否启用底部加载更多数据

```vue
<template>
  <view class="demo">
    <ct-ui-draw
      ref="ctDraw"
      class="sk-draw"
      bgColor="#FFFFFF"
      :drawTop="10"
      :drawBottom="10"
      v-model="list"
      :defaultPageSize="10"
      :refresherEnabled="true"
      :loadingMoreEnabled="true"
      loadingMoreNoMoreText="没有更多的数据了呀～"
      @ctDrawQueryList="ctDrawQueryList"
      @click="click"
    >
    </ct-ui-draw>
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {
      list: []
    }
  },
  onLoad() {
    _self = this
  },
  methods: {
    ctDrawQueryList(pageNo, pageSize) {
      console.log('页面', pageNo, pageSize)
      if (pageNo == 1) {
        _self.list = []
      }

      // 模拟请求数据
      setTimeout(function () {
        let addDatas = []
        for (let i = 0; i < 10; i++) {
          addDatas.push({
            title: '标题' + (i + 1 + (pageNo - 1) * 10),
            content: '2021.10.14 11:26:33',
            iconUrl: '../../static/images/ct_list_icon.png',
            descImgUrl: '../../static/images/ct_list_time.png',
            stateObj: {
              state: i % 2 == 0 ? '通过' : '不通过',
              bgColor: i % 2 == 0 ? '#ecf9de' : '#fddce7',
              color: i % 2 == 0 ? '#6dd000' : '#f0175d'
            }
          })
        }
        _self.$refs.ctDraw.concatDatas(addDatas)
      }, 100)
    },
    click(e) {
      _self.$ctmobile.dialog.alertConfirm({
        title: '默认列表样式的点击事件',
        content: e.title
      })
    },
    pageItemClick(e) {
      _self.$ctmobile.dialog.alertConfirm({
        title: '页面列表样式的点击事件',
        content: e.title
      })
    }
  }
}
</script>

<style lang="scss">
.demo {
  width: 100vw;
  height: 100vh;
  position: relative;

  .sk-draw {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;

    .item {
      width: 100vw;
      height: 200rpx;
      line-height: 200rpx;
      font-size: 40rpx;
      text-align: center;
      border-bottom: 1rpx solid #808080;
    }
  }
}
</style>
```

### [自定义列表内容](http://mid.chinatowercom.cn:18080/appGuide/ui/draw.html#自定义列表内容)

通过`slot`插槽，设置自定义的列表内容及排版

```vue
<template>
  <view class="demo">
    <ct-ui-draw
      ref="ctDraw"
      class="sk-draw"
      bgColor="#FFFFFF"
      :drawTop="10"
      :drawBottom="10"
      v-model="list"
      :defaultPageSize="10"
      :refresherEnabled="true"
      :loadingMoreEnabled="true"
      loadingMoreNoMoreText="没有更多的数据了呀～"
      @ctDrawQueryList="ctDrawQueryList"
      @click="click"
    >
      <view slot="drawItem">
        <view>
          <view
            class="item"
            v-for="(item, index) in list"
            :key="index"
            @click.stop="pageItemClick(item)"
          >
            {{ item.title }}
          </view>
        </view>
      </view>
    </ct-ui-draw>
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {
      list: []
    }
  },
  onLoad() {
    _self = this
  },
  methods: {
    ctDrawQueryList(pageNo, pageSize) {
      console.log('页面', pageNo, pageSize)
      if (pageNo == 1) {
        _self.list = []
      }

      // 模拟请求数据
      setTimeout(function () {
        let addDatas = []
        for (let i = 0; i < 10; i++) {
          addDatas.push({
            title: '标题' + (i + 1 + (pageNo - 1) * 10),
            content: '2021.10.14 11:26:33',
            iconUrl: '../../static/images/ct_list_icon.png',
            descImgUrl: '../../static/images/ct_list_time.png',
            stateObj: {
              state: i % 2 == 0 ? '通过' : '不通过',
              bgColor: i % 2 == 0 ? '#ecf9de' : '#fddce7',
              color: i % 2 == 0 ? '#6dd000' : '#f0175d'
            }
          })
        }
        _self.$refs.ctDraw.concatDatas(addDatas)
      }, 100)
    },
    click(e) {
      _self.$ctmobile.dialog.alertConfirm({
        title: '默认列表样式的点击事件',
        content: e.title
      })
    },
    pageItemClick(e) {
      _self.$ctmobile.dialog.alertConfirm({
        title: '页面列表样式的点击事件',
        content: e.title
      })
    }
  }
}
</script>

<style lang="scss">
.demo {
  width: 100vw;
  height: 100vh;
  position: relative;

  .sk-draw {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;

    .item {
      width: 100vw;
      height: 200rpx;
      line-height: 200rpx;
      font-size: 40rpx;
      text-align: center;
      border-bottom: 1rpx solid #808080;
    }
  }
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/draw.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/draw.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| bgColor               | 背景色                   | string  | #FFFFFF      | —          |
| --------------------- | ------------------------ | ------- | ------------ | ---------- |
| drawTop               | 上方内边距高度，单位px   | number  | 0            | —          |
| drawBottom            | 上方内边距高度，单位px   | number  | 0            | —          |
| defaultPageSize       | 每页显示多少条           | number  | 10           | —          |
| loadingMoreEnabled    | 是否启用底部加载更多数据 | boolean | true         | true/false |
| refresherEnabled      | 是否开启头部下拉刷新     | boolean | true         | true/false |
| loadingMoreNoMoreText | 滑动到底部"没有更多"文字 | String  | 没有更多数据 | —          |
| value                 | 数据                     | array   | —            | —          |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/draw.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| ctDrawQueryList | 下拉刷新或滚动到底部时会自动触发 | -    |
| --------------- | -------------------------------- | ---- |
| click           | 默认列表样式的点击事件           | -    |

### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/draw.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

| drawItem | 自定义列表内容 | -    |
| -------- | -------------- | ---- |
|          |                |      |