# [Selector 城市选择器](http://mid.chinatowercom.cn:18080/appGuide/ui/selector.html#selector-城市选择器)

该组件主要用于选择各地区，有单列选择和多列选择两种形式。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/selector.html#基本使用)

- 通过`title`参数设置选择器标题
- 通过`mode`参数设置选择器类型

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="单列选择">
      <ct-ui-button @click="sel('single')">打开</ct-ui-button>
      <view class="demo-selector">{{ singleValue }}</view>
    </ct-demo-card>
    <ct-demo-card title="多列选择">
      <ct-ui-button @click="sel('mutil')">打开</ct-ui-button>
      <view class="demo-selector">{{ mutilValue }}</view>
    </ct-demo-card>
    <ct-demo-card title="多列联动选择">
      <ct-ui-button @click="sel('auto')">打开</ct-ui-button>
      <view class="demo-selector">{{ autoValue }}</view>
    </ct-demo-card>
    <ct-ui-selector
      ref="selector"
      :mode="selector.mode"
      :title="selector.title"
      :datas="selector.datas"
      @ctSelectorConfirm="ctSelectorConfirm"
    />
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {
      singleValue: '',
      mutilValue: '',
      autoValue: '',
      selector: {
        mode: '',
        title: '',
        datas: []
      }
    }
  },
  onLoad() {
    _self = this
  },
  methods: {
    sel(e) {
      _self.selector.mode = e
      if (e == 'single') {
        _self.selector.title = '单列选择'
        let arr = []
        for (let i = 0; i < 10; i++) {
          arr.push({
            value: i + 1,
            label: '【' + (i + 1) + '】',
            extra: '这是单列【' + (i + 1) + '】的拓展属性【extra】，也可以传{}'
          })
        }
        _self.selector.datas = arr
      } else if (e == 'mutil') {
        _self.selector.title = '多列选择'
        let arr = []
        for (let i = 0; i < 3; i++) {
          arr.push([])
          for (let j = 0; j < 10; j++) {
            arr[i].push({
              value: i + 1 + '-' + (j + 1),
              label: '【' + (i + 1) + '-' + (j + 1) + '】',
              extra:
                '这是多列【' +
                (i + 1) +
                '-' +
                (j + 1) +
                '】的拓展属性【extra】，也可以传{}'
            })
          }
        }
        _self.selector.datas = arr
      } else if (e == 'auto') {
        _self.selector.title = '多列联动选择'
        let arr = []
        for (let i = 0; i < 3; i++) {
          arr.push({
            value: i + 1,
            label: '【' + (i + 1) + '】',
            children: [],
            extra:
              '这是多列联动【' + (i + 1) + '】的拓展属性【extra】，也可以传{}'
          })
          for (let j = 0; j < 4; j++) {
            arr[i].children.push({
              value: i + 1 + '-' + (j + 1),
              label: '【' + (i + 1) + '-' + (j + 1) + '】',
              children: [],
              extra:
                '这是多列联动【' +
                (i + 1) +
                '-' +
                (j + 1) +
                '】的拓展属性【extra】，也可以传{}'
            })
            for (let z = 0; z < 5; z++) {
              arr[i].children[j].children.push({
                value: i + 1 + '-' + (j + 1) + '-' + (z + 1),
                label: '【' + (i + 1) + '-' + (j + 1) + '-' + (z + 1) + '】',
                extra:
                  '这是多列联动【' +
                  (i + 1) +
                  '-' +
                  (j + 1) +
                  '-' +
                  (z + 1) +
                  '】的拓展属性【extra】，也可以传{}'
              })
            }
          }
        }
        _self.selector.datas = arr
      }
      _self.$refs.selector.show()
    },
    ctSelectorConfirm(e) {
      if (_self.selector.mode == 'single') {
        _self.singleValue = e.result
      } else if (_self.selector.mode == 'mutil') {
        let result = ''
        for (let i = 0; i < e.data.length; i++) {
          const item = e.data[i]
          if (result.length == 0) {
            result += item.label
          } else {
            result += '、' + item.label
          }
        }
        _self.mutilValue = result
      } else if (_self.selector.mode == 'auto') {
        _self.autoValue = e.result
      }
    }
  }
}
</script>

<style>
.demo-selector {
  text-align: center;
  margin: 20rpx;
  font-size: 20px;
}
</style>
```

### [设置标题](http://mid.chinatowercom.cn:18080/appGuide/ui/selector.html#设置标题)

通过`title`参数设置选择器标题

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="单列选择">
      <ct-ui-button @click="sel('single')">打开</ct-ui-button>
      <view class="demo-selector">{{ singleValue }}</view>
    </ct-demo-card>
    <ct-demo-card title="多列选择">
      <ct-ui-button @click="sel('mutil')">打开</ct-ui-button>
      <view class="demo-selector">{{ mutilValue }}</view>
    </ct-demo-card>
    <ct-demo-card title="多列联动选择">
      <ct-ui-button @click="sel('auto')">打开</ct-ui-button>
      <view class="demo-selector">{{ autoValue }}</view>
    </ct-demo-card>
    <ct-ui-selector
      ref="selector"
      :mode="selector.mode"
      :title="selector.title"
      :datas="selector.datas"
      @ctSelectorConfirm="ctSelectorConfirm"
    />
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {
      singleValue: '',
      mutilValue: '',
      autoValue: '',
      selector: {
        mode: '',
        title: '',
        datas: []
      }
    }
  },
  onLoad() {
    _self = this
  },
  methods: {
    sel(e) {
      _self.selector.mode = e
      if (e == 'single') {
        _self.selector.title = '自定义单列选择'
        let arr = []
        for (let i = 0; i < 10; i++) {
          arr.push({
            value: i + 1,
            label: '【' + (i + 1) + '】',
            extra: '这是单列【' + (i + 1) + '】的拓展属性【extra】，也可以传{}'
          })
        }
        _self.selector.datas = arr
      } else if (e == 'mutil') {
        _self.selector.title = '自定义多列选择'
        let arr = []
        for (let i = 0; i < 3; i++) {
          arr.push([])
          for (let j = 0; j < 10; j++) {
            arr[i].push({
              value: i + 1 + '-' + (j + 1),
              label: '【' + (i + 1) + '-' + (j + 1) + '】',
              extra:
                '这是多列【' +
                (i + 1) +
                '-' +
                (j + 1) +
                '】的拓展属性【extra】，也可以传{}'
            })
          }
        }
        _self.selector.datas = arr
      } else if (e == 'auto') {
        _self.selector.title = '自定义多列联动选择'
        let arr = []
        for (let i = 0; i < 3; i++) {
          arr.push({
            value: i + 1,
            label: '【' + (i + 1) + '】',
            children: [],
            extra:
              '这是多列联动【' + (i + 1) + '】的拓展属性【extra】，也可以传{}'
          })
          for (let j = 0; j < 4; j++) {
            arr[i].children.push({
              value: i + 1 + '-' + (j + 1),
              label: '【' + (i + 1) + '-' + (j + 1) + '】',
              children: [],
              extra:
                '这是多列联动【' +
                (i + 1) +
                '-' +
                (j + 1) +
                '】的拓展属性【extra】，也可以传{}'
            })
            for (let z = 0; z < 5; z++) {
              arr[i].children[j].children.push({
                value: i + 1 + '-' + (j + 1) + '-' + (z + 1),
                label: '【' + (i + 1) + '-' + (j + 1) + '-' + (z + 1) + '】',
                extra:
                  '这是多列联动【' +
                  (i + 1) +
                  '-' +
                  (j + 1) +
                  '-' +
                  (z + 1) +
                  '】的拓展属性【extra】，也可以传{}'
              })
            }
          }
        }
        _self.selector.datas = arr
      }
      _self.$refs.selector.show()
    },
    ctSelectorConfirm(e) {
      if (_self.selector.mode == 'single') {
        _self.singleValue = e.result
      } else if (_self.selector.mode == 'mutil') {
        let result = ''
        for (let i = 0; i < e.data.length; i++) {
          const item = e.data[i]
          if (result.length == 0) {
            result += item.label
          } else {
            result += '、' + item.label
          }
        }
        _self.mutilValue = result
      } else if (_self.selector.mode == 'auto') {
        _self.autoValue = e.result
      }
    }
  }
}
</script>

<style>
.demo-selector {
  text-align: center;
  margin: 20rpx;
  font-size: 20px;
}
</style>
```

### [设置选择器类型](http://mid.chinatowercom.cn:18080/appGuide/ui/selector.html#设置选择器类型)

通过`mode`参数设置选择器标题

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="单列选择">
      <ct-ui-button @click="sel('single')">打开</ct-ui-button>
      <view class="demo-selector">{{ singleValue }}</view>
    </ct-demo-card>
    <ct-demo-card title="多列选择">
      <ct-ui-button @click="sel('mutil')">打开</ct-ui-button>
      <view class="demo-selector">{{ mutilValue }}</view>
    </ct-demo-card>
    <ct-demo-card title="多列联动选择">
      <ct-ui-button @click="sel('auto')">打开</ct-ui-button>
      <view class="demo-selector">{{ autoValue }}</view>
    </ct-demo-card>
    <ct-ui-selector
      ref="selector"
      :mode="selector.mode"
      :title="selector.title"
      :datas="selector.datas"
      @ctSelectorConfirm="ctSelectorConfirm"
    />
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {
      singleValue: '',
      mutilValue: '',
      autoValue: '',
      selector: {
        mode: '',
        title: '',
        datas: []
      }
    }
  },
  onLoad() {
    _self = this
  },
  methods: {
    sel(e) {
      _self.selector.mode = e
      if (e == 'single') {
        _self.selector.title = '单列选择'
        let arr = []
        for (let i = 0; i < 10; i++) {
          arr.push({
            value: i + 1,
            label: '【' + (i + 1) + '】',
            extra: '这是单列【' + (i + 1) + '】的拓展属性【extra】，也可以传{}'
          })
        }
        _self.selector.datas = arr
      } else if (e == 'mutil') {
        _self.selector.title = '多列选择'
        let arr = []
        for (let i = 0; i < 3; i++) {
          arr.push([])
          for (let j = 0; j < 10; j++) {
            arr[i].push({
              value: i + 1 + '-' + (j + 1),
              label: '【' + (i + 1) + '-' + (j + 1) + '】',
              extra:
                '这是多列【' +
                (i + 1) +
                '-' +
                (j + 1) +
                '】的拓展属性【extra】，也可以传{}'
            })
          }
        }
        _self.selector.datas = arr
      } else if (e == 'auto') {
        _self.selector.title = '多列联动选择'
        let arr = []
        for (let i = 0; i < 3; i++) {
          arr.push({
            value: i + 1,
            label: '【' + (i + 1) + '】',
            children: [],
            extra:
              '这是多列联动【' + (i + 1) + '】的拓展属性【extra】，也可以传{}'
          })
          for (let j = 0; j < 4; j++) {
            arr[i].children.push({
              value: i + 1 + '-' + (j + 1),
              label: '【' + (i + 1) + '-' + (j + 1) + '】',
              children: [],
              extra:
                '这是多列联动【' +
                (i + 1) +
                '-' +
                (j + 1) +
                '】的拓展属性【extra】，也可以传{}'
            })
            for (let z = 0; z < 5; z++) {
              arr[i].children[j].children.push({
                value: i + 1 + '-' + (j + 1) + '-' + (z + 1),
                label: '【' + (i + 1) + '-' + (j + 1) + '-' + (z + 1) + '】',
                extra:
                  '这是多列联动【' +
                  (i + 1) +
                  '-' +
                  (j + 1) +
                  '-' +
                  (z + 1) +
                  '】的拓展属性【extra】，也可以传{}'
              })
            }
          }
        }
        _self.selector.datas = arr
      }
      _self.$refs.selector.show()
    },
    ctSelectorConfirm(e) {
      if (_self.selector.mode == 'single') {
        _self.singleValue = e.result
      } else if (_self.selector.mode == 'mutil') {
        let result = ''
        for (let i = 0; i < e.data.length; i++) {
          const item = e.data[i]
          if (result.length == 0) {
            result += item.label
          } else {
            result += '、' + item.label
          }
        }
        _self.mutilValue = result
      } else if (_self.selector.mode == 'auto') {
        _self.autoValue = e.result
      }
    }
  }
}
</script>

<style>
.demo-selector {
  text-align: center;
  margin: 20rpx;
  font-size: 20px;
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/selector.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/selector.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| mode                 | 类型                                  | string           | single-column                             | single-column/mutil-column/mutil-column-auto |          |
| -------------------- | ------------------------------------- | ---------------- | ----------------------------------------- | -------------------------------------------- | -------- |
| title                | 标题                                  | string           | —                                         | —                                            |          |
| datas                | 数据                                  | array            | —                                         | —                                            |          |
| itemHeight           | 项目的高度(单位：px)                  | Number \| String | 56                                        | -                                            | v1.0.33+ |
| visibleItemCount     | 每列中可见选项的数量                  | Number \| String | 5                                         | -                                            | v1.0.33+ |
| optionFontSize       | 字体大小，单位rpx                     | Number ｜ String | 32                                        | -                                            | v1.0.33+ |
| activeOptionFontSize | 选中的字体大小，单位rpx               | Number ｜ String | 36                                        | -                                            | v1.0.33+ |
| color                | 未选中的颜色                          | String           | #262F40                                   | -                                            | v1.0.33+ |
| activeColor          | 选中的颜色                            | String           | #3860f5                                   | -                                            | v1.0.33+ |
| radius               | 圆角，单位rpx                         | Number ｜ String | 16                                        | -                                            | v1.0.33+ |
| position             | 工具条显示位置，top 顶部、bottom 底部 | String           | top                                       | top \| bottom                                | v1.0.33+ |
| title                | 中间/左上角的标题                     | String           | 选择                                      | -                                            | v1.0.33+ |
| titleSize            | 标题文字大小，单位rpx                 | Number ｜ String | 32                                        | -                                            | v1.0.33+ |
| titleColor           | 标题文字颜色                          | String           | #262F40                                   | -                                            | v1.0.33+ |
| subTitle             | 副标题，position = top 起效           | String           | -                                         | -                                            | v1.0.33+ |
| titleSize            | 副标题文字大小，position = top 起效   | Number ｜ String | 24                                        | -                                            | v1.0.33+ |
| showConfirmButton    | 是否显示确认按钮                      | Boolean          | true                                      | true \| false                                | v1.0.33+ |
| confirmText          | 确定按钮文字                          | String           | 确定                                      | -                                            | v1.0.33+ |
| confirmTextSize      | 确定按钮文字大小                      | Number\|String   | 14                                        | -                                            | v1.0.33+ |
| confirmTextColor     | 確定按钮文字颜色                      | String           | #3164F6                                   | -                                            | v1.0.20+ |
| confirmButtonWidth   | 确定按钮的宽度(单位：%)               | Number\|String   | 50                                        | -                                            | v1.0.33+ |
| showCancelButton     | 是否显示取消按钮                      | Boolean          | true                                      | true \| false                                | v1.0.33+ |
| cancelText           | 取消按钮文字                          | String           | 取消                                      | -                                            | v1.0.33+ |
| cancelTextSize       | 取消按钮文字大小                      | Number\|String   | 14                                        | -                                            | v1.0.33+ |
| cancelTextColor      | 取消按钮文字颜色                      | String           | #505C73                                   | -                                            | v1.0.20+ |
| cancelButtonWidth    | 取消按钮的宽度(单位：%)               | Number\|String   | 50                                        | -                                            | v1.0.33+ |
| btnColor             | btn 颜色，只针对confirm有效           | String           | #3164F6                                   | -                                            | v1.0.33+ |
| btnSize              | 按钮高度(单位：px)                    | Number\|String   | 40                                        | -                                            | v1.0.33+ |
| btnShape             | 按钮形状(见按钮组件)                  | Number\|String   | 8                                         | -                                            | v1.0.33+ |
| disabled             | 确定按钮是否禁用                      | Boolean          | false                                     | -                                            | v1.0.33+ |
| reverse              | 按钮反转                              | Boolean          | false                                     | true \| false                                | v1.0.33+ |
| overlay              | 是否打开蒙版                          | Boolean          | true                                      | true \| false                                | v1.0.33+ |
| overLayOpacity       | 透明度                                | String ｜ Number | 0.7                                       | -                                            | v1.0.33+ |
| overLayClassName     | 自定义遮罩层样式名称                  | String           | -                                         | -                                            | v1.0.33+ |
| overlayStyle         | 自定义遮罩层样式                      | Object           | -                                         | -                                            | v1.0.33+ |
| closeOnClickOverLay  | 是否允许通过点击遮罩关闭              | Boolean          | true                                      | -                                            | v1.0.33+ |
| zIndex               | 弹出的z-index值                       | String ｜ Number | 0                                         | -                                            | v1.0.33+ |
| safeAreaInsetTop     | 是否为留出顶部安全距离                | Boolean          | true                                      | true \| false                                | v1.0.33+ |
| safeAreaInsetBottom  | 是否为留出底部安全距离                | Boolean          | true                                      | true \| false                                | v1.0.33+ |
| border               | 是否显示边框                          | Boolean          | true                                      | true \| false                                | v1.0.33+ |
| value                | 通过双向绑定控制组件的弹出与收起      | Boolean          | false                                     | true \| false                                | v1.0.33+ |
| defaultValue         | 提供的默认选中的下标                  | Array            | [0]                                       | -                                            | v1.0.33+ |
| valueName            | 自定义value属性名                     | string           | value                                     | —                                            |          |
| labelName            | 自定义label属性名                     | label            | value                                     | —                                            |          |
| childName            | 自定义children属性名                  | string           | children                                  | —                                            |          |
| emptyTip             | datas 为空时，显示的提示信息          | string           | 暂无数据                                  | —                                            | v1.0.16+ |
| emptyImage           | datas 为空时，显示的提示图片          | string           | https://s1.ax1x.com/2022/12/21/zOWL4O.png | —                                            | v1.0.16+ |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/selector.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| confirm           | 确定点击事件         | -                                        |
| ----------------- | -------------------- | ---------------------------------------- |
| ctSelectorConfirm | 确定点击事件(将弃用) | -                                        |
| change            | 列滚动选择事件       | value 选中的值，changeIndex 操作的列索引 |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/selector.html#slots)

| name | 说明 | 作用域 | 版本 |
| ---- | ---- | ------ | ---- |
|      |      |        |      |

| empty | 自定义的提示内容 | -    | v1.0.16+ |
| ----- | ---------------- | ---- | -------- |
|       |                  |      |          |