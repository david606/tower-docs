# [DropRefresh 下拉刷新上拉加载](http://mid.chinatowercom.cn:18080/appGuide/ui/dropRefresh.html#droprefresh-下拉刷新上拉加载)

该组件组要对于列表数据的刷新以及加载进行优化。。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/dropRefresh.html#基本使用)

- 直接在组件中遍历数据显示

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-drop-refresh>
        <view v-for="(item, index) in list" :key="index">{{ item }}</view>
      </ct-ui-drop-refresh>
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
  onLoad() {
    this.list = [1, 2, 3, 4, 5]
  }
}
</script>

<style lang="scss"></style>
```

### [自定义样式及文字](http://mid.chinatowercom.cn:18080/appGuide/ui/dropRefresh.html#自定义样式及文字)

- 通过`refresherEnabled`参数设置是否开启下拉刷新
- 通过`refresherTriggered`参数表示下拉刷新的当前状态(true 表示下拉刷新已经被触发，false 表示下拉刷新未被触发，同时也表示刷新区域是否显示)
- 通过`trigger`参数设置当前刷新状态(true 表示正在刷新， false 表示刷新完成，用于控制刷新区域文字图标显示)
- 通过`loadingConnect`参数设置刷新区域内容显示（trigger 为 true 时显示）
- 通过`finshConnect`参数设置刷新区域内容显示（trigger 为 false 时显示）
- 通过`idLoadingMore`参数设置上拉加载是否显示
- 通过`pullingText`参数设置上拉加载提示文案（底部）
- 通过`pullingIcon`参数设置上拉加载图标（底部）

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义样式及文字">
      <ct-ui-drop-refresh
        :refresherTriggered="refresherTriggered"
        :trigger="trigger"
        :loadingConnect="loadingConnect"
        :idLoadingMore="idLoadingMore"
        :pullingText="pullingText"
        :pullingIcon="pullingIcon"
        @pulling="refresherpulling"
        @refresh="refresherrefresh"
        @restore="refresherrestore"
        @abort="refresherabort"
        @scrolltolower="scrolltolower"
      >
        <div v-for="(item, index) in list" :key="index">{{ item }}</div>
      </ct-ui-drop-refresh>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      // 第一个下拉框数据
      refresherTriggered: true,
      trigger: true,
      idLoadingMore: false,
      pullingText: '',
      pullingIcon: '',
      pullingColor: '#aaa',
      loadingConnect: {},
      list: [],
      record: true
    }
  },
  onLoad() {
    this.list = [1, 2, 3, 4, 5]
    this.idLoadingMore = true
    this.pullingText = '数据已经全部加载'
  },
  methods: {
    // 下拉组件被下拉事件
    refresherpulling() {
      this.refresherTriggered = true
      this.trigger = true
      this.loadingConnect = {
        shapeType: '',
        color: '#aaa',
        text: '下拉开启刷新'
      }
    },
    // 下拉刷新事件被触发
    refresherrefresh() {
      this.record = true
      this.loadingConnect = {
        shapeType: 'point',
        color: '#aaa',
        text: '正在刷新...'
      }
      // 异步重新加载数据
      setTimeout(() => {
        this.list = [3, 4, 4, 4, 5, 5, 6, 7, 78, 3, 4, 4, 4, 5, 5, 6, 7, 78]
        // 修改当前刷新状态为刷新完成
        this.trigger = false
        // 修改上拉加载是否显示
        this.idLoadingMore = true
        // 延迟关闭下拉刷新区域
        setTimeout(() => {
          this.refresherTriggered = false
        }, 500)
      }, 2000)
    },
    // 下拉刷新被复位
    refresherrestore() {
      console.log('下拉刷新被复位')
    },
    // 下拉刷新被终止
    refresherabort() {
      console.log('下拉刷新被终止')
    },
    // 滚动到底部
    scrolltolower() {
      // 正式使用时应该使用当前展示条数与总条数比较，这里只是示例
      if (this.record) {
        // 修改上拉记载是否显示
        this.idLoadingMore = true
        this.pullingIcon = 'point'
        this.pullingText = '数据加载中'
        // 加一个判断条件
        this.record = false
        setTimeout(() => {
          this.list.push(999)
          // 修改当前刷新状态为刷新完成
          this.pullingIcon = ''
          this.pullingText = '数据已经全部加载'
        }, 1000)
      }
    }
  }
}
</script>

<style lang="scss"></style>
```

### [使用插槽](http://mid.chinatowercom.cn:18080/appGuide/ui/dropRefresh.html#使用插槽)

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="插槽的使用">
      <ct-ui-drop-refresh>
        <view v-for="(item, index) in list" :key="index">{{ item }}</view>
        <view slot="drop-refresher">这是使用插槽的下拉刷新</view>
        <view slot="loadingMore">这是使用插槽的上拉加载</view>
      </ct-ui-drop-refresh>
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
  onLoad() {
    this.list = [1, 2, 3, 4, 5]
  }
}
</script>

<style lang="scss"></style>
```

### [加载失败重新加载](http://mid.chinatowercom.cn:18080/appGuide/ui/dropRefresh.html#加载失败重新加载)

- 通过`pullingColor`参数设置上拉加载提示颜色（底部）
- 通过`loadingMoreClick`方法触发底部加载更多点击事件

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="加载失败重新加载">
      <ct-ui-drop-refresh
        :refresherTriggered="refresherTriggered1"
        :trigger="trigger1"
        :loadingConnect="loadingConnect1"
        :idLoadingMore="idLoadingMore1"
        :pullingText="pullingText1"
        :pullingIcon="pullingIcon1"
        :pullingColor="pullingColor1"
        @pulling="refresherpulling1"
        @refresh="refresherrefresh1"
        @restore="refresherrestore1"
        @abort="refresherabort1"
        @scrolltolower="scrolltolower1"
        @loadingMoreClick="loadingMoreClick"
      >
        <view v-for="(item, index) in list1" :key="index">{{ item }}</view>
      </ct-ui-drop-refresh>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      refresherTriggered1: true,
      trigger1: true,
      idLoadingMore1: false,
      pullingText1: '',
      pullingIcon1: '',
      pullingColor1: '#aaa',
      loadingConnect1: {},
      list1: [],
      record1: true
    }
  },
  onLoad() {
    this.list1 = [1, 2, 3, 4, 5, 1, 2, 3, 4, 5, 1, 2, 3, 4, 5]
    this.idLoadingMore1 = true
    this.pullingText1 = ''
  },
  methods: {
    // 下拉组件被下拉事件
    refresherpulling1() {
      this.refresherTriggered1 = true
      this.trigger1 = true
      this.loadingConnect1 = {
        shapeType: '',
        color: '#aaa',
        text: '下拉开启刷新'
      }
    },
    // 下拉刷新事件被触发
    refresherrefresh1() {
      this.record = true
      this.loadingConnect1 = {
        shapeType: 'point',
        color: '#aaa',
        text: '正在刷新...'
      }
      // 异步重新加载数据
      setTimeout(() => {
        this.list1 = [3, 4, 4, 4, 5, 5, 6, 7, 78, 3, 4, 4, 4, 5, 5, 6, 7, 78]
        // 修改当前刷新状态为刷新完成
        this.trigger1 = false
        // 修改上拉加载是否显示
        this.idLoadingMore1 = true
        // 延迟关闭下拉刷新区域
        setTimeout(() => {
          this.refresherTriggered1 = false
        }, 500)
      }, 2000)
    },
    // 下拉刷新被复位
    refresherrestore1() {
      console.log('下拉刷新被复位')
    },
    // 下拉刷新被终止
    refresherabort1() {
      console.log('下拉刷新被终止')
    },
    // 滚动到底部
    scrolltolower1() {
      // 正式使用时应该使用当前展示条数与总条数比较，这里只是示例
      if (this.record1) {
        // 修改上拉记载是否显示
        this.idLoadingMore1 = true
        this.pullingIcon1 = 'point'
        this.pullingText1 = '数据加载中'
        // 加一个判断条件
        this.record1 = false
        setTimeout(() => {
          // 修改当前刷新状态为刷新完成
          this.pullingIcon1 = ''
          this.pullingColor1 = 'red'
          this.pullingText1 = '数据加载失败，请点击重试'
        }, 1000)
      }
    },
    // 上拉加载报错，点击后重新加载
    loadingMoreClick() {
      // 修改上拉记载是否显示
      this.idLoadingMore1 = true
      this.pullingIcon1 = 'point'
      this.pullingColor1 = '#aaa'
      this.pullingText1 = '数据加载中'
      // 加一个判断条件
      setTimeout(() => {
        this.list1.push(999)
        // 修改当前刷新状态为刷新完成
        this.pullingIcon1 = ''
        this.pullingText1 = '数据已经全部加载'
      }, 1000)
    }
  }
}
</script>

<style lang="scss"></style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/dropRefresh.html#事件监听)

- 通过`pulling`方法触发下拉组件被下拉事件
- 通过`refresh`方法触发下拉刷新事件被触发
- 通过`restore`方法触发下拉刷新被复位
- 通过`abort`方法触发下拉刷新被终止
- 通过`scrolltolower`方法触发滚动到底部

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-drop-refresh
        :refresherTriggered="refresherTriggered"
        :trigger="trigger"
        :loadingConnect="loadingConnect"
        :idLoadingMore="idLoadingMore"
        :pullingText="pullingText"
        :pullingIcon="pullingIcon"
        @pulling="refresherpulling"
        @refresh="refresherrefresh"
        @restore="refresherrestore"
        @abort="refresherabort"
        @scrolltolower="scrolltolower"
      >
        <div v-for="(item, index) in list" :key="index">{{ item }}</div>
      </ct-ui-drop-refresh>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      // 第一个下拉框数据
      refresherTriggered: true,
      trigger: true,
      idLoadingMore: false,
      pullingText: '',
      pullingIcon: '',
      pullingColor: '#aaa',
      loadingConnect: {},
      list: [],
      record: true
    }
  },
  onLoad() {
    this.list = [1, 2, 3, 4, 5]
    this.idLoadingMore = true
    this.pullingText = '数据已经全部加载'
  },
  methods: {
    // 下拉组件被下拉事件
    refresherpulling() {
      this.refresherTriggered = true
      this.trigger = true
      this.loadingConnect = {
        shapeType: '',
        color: '#aaa',
        text: '下拉开启刷新'
      }
    },
    // 下拉刷新事件被触发
    refresherrefresh() {
      this.record = true
      this.loadingConnect = {
        shapeType: 'point',
        color: '#aaa',
        text: '正在刷新...'
      }
      // 异步重新加载数据
      setTimeout(() => {
        this.list = [3, 4, 4, 4, 5, 5, 6, 7, 78, 3, 4, 4, 4, 5, 5, 6, 7, 78]
        // 修改当前刷新状态为刷新完成
        this.trigger = false
        // 修改上拉加载是否显示
        this.idLoadingMore = true
        // 延迟关闭下拉刷新区域
        setTimeout(() => {
          this.refresherTriggered = false
        }, 500)
      }, 2000)
    },
    // 下拉刷新被复位
    refresherrestore() {
      console.log('下拉刷新被复位')
    },
    // 下拉刷新被终止
    refresherabort() {
      console.log('下拉刷新被终止')
    },
    // 滚动到底部
    scrolltolower() {
      // 正式使用时应该使用当前展示条数与总条数比较，这里只是示例
      if (this.record) {
        // 修改上拉记载是否显示
        this.idLoadingMore = true
        this.pullingIcon = 'point'
        this.pullingText = '数据加载中'
        // 加一个判断条件
        this.record = false
        setTimeout(() => {
          this.list.push(999)
          // 修改当前刷新状态为刷新完成
          this.pullingIcon = ''
          this.pullingText = '数据已经全部加载'
        }, 1000)
      }
    }
  }
}
</script>

<style lang="scss"></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/dropRefresh.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/dropRefresh.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| height                | 滚动框高度                                                   | String           | 200px                                                        |      |
| --------------------- | ------------------------------------------------------------ | ---------------- | ------------------------------------------------------------ | ---- |
| refresherEnabled      | 是否开启下拉刷新                                             | Boolean          | true                                                         | -    |
| refresherThreshold    | 下拉刷新的阈值                                               | Number \| String | 45                                                           | -    |
| refresherDefaultStyle | 下拉刷新的默认样式(支持设置black，white，none，none 表示不使用默认样式) | String           | none                                                         | -    |
| refresherBackground   | 下拉刷新区域的背景颜色                                       | String           | #FFF                                                         | -    |
| refresherTriggered    | 下拉刷新的当前状态(true 表示下拉刷新已经被触发，false 表示下拉刷新未被触发，刷新区域是否显示) | Boolean          | false                                                        | -    |
| className             | 下拉区域的类名                                               | String           |                                                              | -    |
| trigger               | 当前刷新状态(true 表示正在刷新， false表示刷新完成，用于控制刷新区域文字图标显示) | Boolean          | false                                                        | -    |
| loadingConnect        | 刷新区域内容显示（trigger为true时显示）                      | Object           | {shapeType: "point" (这个字段的值参考LoadingIcon组件), color: "#aaa", text: "正在刷新..."} | -    |
| finshConnect          | 刷新区域内容显示（trigger为false时显示）                     | Object           | {shapeType: "" (这个字段的值参考LoadingIcon组件), color: "#aaa", text: "刷新成功"} | -    |
| showScrollbar         | 是否显示滚动条                                               | Boolean          | false                                                        | -    |
| scrollTop             | 设置滚动条初始位置                                           | Number \| String | 0                                                            | -    |
| scrollWithAnimation   | 在设置滚动条位置时使用动画过渡                               | Boolean          | false                                                        | -    |
| idLoadingMore         | 上拉加载是否显示                                             | Boolean          | false                                                        | -    |
| pullingText           | 上拉加载提示文案（底部）                                     | String           | 数据加载中                                                   | -    |
| pullingColor          | 上拉加载提示颜色（底部）                                     | String           | #aaa                                                         | -    |
| pullingIcon           | 上拉加载图标（底部  这个字段的值参考Icon组件）               | String           |                                                              | -    |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/dropRefresh.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| pulling          | 下拉组件被下拉事件   | -    |
| ---------------- | -------------------- | ---- |
| refresh          | 下拉刷新事件被触发   | -    |
| restore          | 下拉刷新被复位       | -    |
| abort            | 下拉刷新被终止       | -    |
| scrolltolower    | 滚动到底部           | -    |
| loadingMoreClick | 底部加载更多点击事件 | -    |