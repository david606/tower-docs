# [foldList 折叠面板](http://mid.chinatowercom.cn:18080/appGuide/ui/foldList.html#foldlist-折叠面板)

该组件通常用于内容展开收起。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/foldList.html#基本使用)

- 通过`items`参数设置数据*(必填)

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <ct-ui-foldlist :items="items" />
    </ct-demo-card>
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {
      items: [
        {
          id: 0,
          head: '销售|客服|市场',
          headFontSize: '30rpx',
          headColor: '#2ebbfe',
          content:
            '软件/互联网开发/系统集成软件/互联网开发/系统集成软件/互联网开发/系统集成软件/互联网开发/系统集成',
          upimg: '/static/images/shang.png',
          downimg: '/static/images/xia.png'
        },
        {
          id: 1,
          head: 'IT|互联网|通信',
          headColor: '#2ebbfe',
          content: '软件/互联网开发/系统集成',
          expandContentBg: '#299988',
          upimg: '/static/images/shang.png',
          downimg: '/static/images/xia.png',
          disable: true
        },
        {
          id: 2,
          head: '微分|积分|级数',
          content:
            '微分/导数/中值定理/不定积分/定积分/反常积分/常数项级数/幂级数/傅里叶级数',
          iconColor: '#eb4b4b',
          showArrow: true
        },
        {
          id: 3,
          head: '函数|极限|连续',
          content: '单调性/连续性/无穷小',
          upimg: '/static/images/shang.png'
        }
      ]
    }
  }
}
</script>

<style lang="scss"></style>
```

### [默认展开](http://mid.chinatowercom.cn:18080/appGuide/ui/foldList.html#默认展开)

- 通过`current`参数设置默认展开某个 item，默认为都不展开，如果开启`onlyExpand`，则默认显示数组中第一个。

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="默认展开第3和4个item">
      <ct-ui-foldlist
        :items="items"
        :current="current"
        :onlyExpand="onlyExpand"
      />
    </ct-demo-card>
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {
      items: [
        {
          id: 0,
          head: '销售|客服|市场',
          headFontSize: '30rpx',
          headColor: '#2ebbfe',
          content:
            '软件/互联网开发/系统集成软件/互联网开发/系统集成软件/互联网开发/系统集成软件/互联网开发/系统集成',
          upimg: '/static/images/shang.png',
          downimg: '/static/images/xia.png'
        },
        {
          id: 1,
          head: 'IT|互联网|通信',
          headColor: '#2ebbfe',
          content: '软件/互联网开发/系统集成',
          expandContentBg: '#299988',
          upimg: '/static/images/shang.png',
          downimg: '/static/images/xia.png',
          disable: true
        },
        {
          id: 2,
          head: '微分|积分|级数',
          content:
            '微分/导数/中值定理/不定积分/定积分/反常积分/常数项级数/幂级数/傅里叶级数',
          iconColor: '#eb4b4b',
          showArrow: true
        },
        {
          id: 3,
          head: '函数|极限|连续',
          content: '单调性/连续性/无穷小',
          upimg: '/static/images/shang.png'
        }
      ],
      current: [-1, 2, 3],
      onlyExpand: false
    }
  }
}
</script>

<style lang="scss"></style>
```

### [仅展开一个](http://mid.chinatowercom.cn:18080/appGuide/ui/foldList.html#仅展开一个)

- 通过`onlyExpand`参数设置设定是否只能有一个 item 展开。当展开其他 item 时，已展开的 item 自动收起。

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="设置只能展开一个">
      <ct-ui-foldlist :items="items" :current="current" :onlyExpand="true" />
    </ct-demo-card>
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {
      items: [
        {
          id: 0,
          head: '销售|客服|市场',
          headFontSize: '30rpx',
          headColor: '#2ebbfe',
          content:
            '软件/互联网开发/系统集成软件/互联网开发/系统集成软件/互联网开发/系统集成软件/互联网开发/系统集成',
          upimg: '/static/images/shang.png',
          downimg: '/static/images/xia.png'
        },
        {
          id: 1,
          head: 'IT|互联网|通信',
          headColor: '#2ebbfe',
          content: '软件/互联网开发/系统集成',
          expandContentBg: '#299988',
          upimg: '/static/images/shang.png',
          downimg: '/static/images/xia.png',
          disable: true
        },
        {
          id: 2,
          head: '微分|积分|级数',
          content:
            '微分/导数/中值定理/不定积分/定积分/反常积分/常数项级数/幂级数/傅里叶级数',
          iconColor: '#eb4b4b',
          showArrow: true
        },
        {
          id: 3,
          head: '函数|极限|连续',
          content: '单调性/连续性/无穷小',
          upimg: '/static/images/shang.png'
        }
      ],
      current: [-1, 2, 3]
    }
  }
}
</script>

<style lang="scss"></style>
```

### [自定义插槽](http://mid.chinatowercom.cn:18080/appGuide/ui/foldList.html#自定义插槽)

- 通过`foldList-{index}`可以自定义内容显示。

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义插槽使用">
      <ct-ui-foldlist
        :items="items"
        :current="current"
        :onlyExpand="onlyExpand"
      >
        <template v-slot:foldList-0>
          <ct-ui-form
            labelPosition="left"
            starPosition="after"
            labelAlign="left"
            errorType="message"
            :model="model"
            ref="form"
            :labelStyle="labelStyle"
            contentAlign="right"
          >
            <ct-ui-form-item
              label="活动名称"
              labelSplit=""
              borderBottom
              required
              prop="user.name"
              ref="item1"
            >
              <ct-ui-input
                :customStyle="customStyle"
                inputAlign="right"
                v-model="model.user.name"
                border="none"
              ></ct-ui-input>
            </ct-ui-form-item>
            <ct-ui-form-item
              label="活动编号"
              labelSplit=""
              borderBottom
              prop="user.number"
              ref="item1"
            >
              <ct-ui-input
                inputAlign="right"
                :customStyle="customStyle"
                v-model="model.user.number"
                border="none"
              ></ct-ui-input>
            </ct-ui-form-item>
            <ct-ui-form-item
              label="所属组织"
              labelSplit=""
              borderBottom
              required
              prop="user.organization"
              ref="item1"
            >
              <ct-ui-input
                inputAlign="right"
                :customStyle="customStyle"
                v-model="model.user.organization"
                border="none"
              ></ct-ui-input>
            </ct-ui-form-item>
            <ct-ui-form-item
              label="负责人"
              labelSplit=""
              borderBottom
              required
              prop="user.head"
              ref="item2"
            >
              <ct-ui-input
                inputAlign="right"
                :customStyle="customStyle"
                v-model="model.user.head"
                border="none"
              ></ct-ui-input>
            </ct-ui-form-item>
          </ct-ui-form>
        </template>
      </ct-ui-foldlist>
    </ct-demo-card>
  </view>
</template>

<script>
var _self
export default {
  data() {
    return {
      model: {
        user: {
          name: '换电业务全国营销活动',
          number: 'HD20232545412315',
          organization: '中国铁塔股份有限公司',
          head: '张三(zhangsan)'
        }
      },
      labelStyle: {
        color: '#50573',
        fontSize: '16px'
      },
      customStyle: {
        color: '#262f40'
      },
      items: [
        {
          id: 0,
          head: '销售|客服|市场',
          headFontSize: '30rpx',
          headColor: '#2ebbfe',
          content: '',
          upimg: '/static/images/shang.png',
          downimg: '/static/images/xia.png'
        },
        {
          id: 1,
          head: 'IT|互联网|通信',
          headColor: '#2ebbfe',
          content: '软件/互联网开发/系统集成',
          expandContentBg: '#299988',
          upimg: '/static/images/shang.png',
          downimg: '/static/images/xia.png',
          disable: true
        },
        {
          id: 2,
          head: '微分|积分|级数',
          content: '',
          iconColor: '#eb4b4b',
          showArrow: true
        },
        {
          id: 3,
          head: '函数|极限|连续',
          content: '',
          upimg: '/static/images/shang.png'
        }
      ],
      current: [-1, 2, 3],
      onlyExpand: false
    }
  }
}
</script>

<style lang="scss"></style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/foldList.html#事件监听)

`click`事件可以监听当前点击事件 `change`事件可以监听当前展开/收起的 item 的 index

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="事件监听">
      <ct-ui-foldlist :items="items" @click="click" @change="change" />
         
    </ct-demo-card>
  </view>
</template>

<script>
var _self;
export default {
	data() {
		return {
			items: [{
				id: 0,
				head: "销售|客服|市场",
				headFontSize:'30rpx',
				headColor:'#2ebbfe',
				content:"软件/互联网开发/系统集成软件/互联网开发/系统集成软件/互联网开发/系统集成软件/互联网开发/系统集成",
				contentFontSize:'28rpx',
				contentColor:'#333',
				upimg:'../../static/images/shang.png',
				downimg:'../../static/images/xia.png',
				showArrow: false
			},{
				id: 1,
				head: "IT|互联网|通信",
				content:"软件/互联网开发/系统集成",
				upimg:'../../static/images/shang.png',
				downimg:'../../static/images/xia.png',
				disable: false
			},{
				id: 2,
				head: "微分|积分|级数",
				content:"微分/导数/中值定理/不定积分/定积分/反常积分/常数项级数/幂级数/傅里叶级数",
				iconColor:'#eb4b4b',
				showArrow: true
			},{
				id: 3,
				head: "函数|极限|连续",
				expandHeadBg:'#a6d6eb',
				content:"单调性/连续性/无穷小",
				expandContentBg:'#abf5e3',
				upimg:'../../static/images/shang.png'
			}]
		}
	},
	methods: {
		click(e){
			console.log(e)
		}
		change(e, bool){
			console.log(e, bool);
		}
	}
}
</script>

<style lang="scss"></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/foldList.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/foldList.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| *items     | 数据(必填)           | Array           | []    | —    |
| ---------- | -------------------- | --------------- | ----- | ---- |
| current    | 默认展开某个item     | Array \| string | -1    | —    |
| onlyExpand | 是否只能展开一个item | Boolean         | false | —    |

#### [items 元素说明:](http://mid.chinatowercom.cn:18080/appGuide/ui/foldList.html#items-元素说明)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| head            | 数据中标题                  | string  | —           | —    |
| --------------- | --------------------------- | ------- | ----------- | ---- |
| content         | 数据中内容                  | string  | —           | —    |
| headFontSize    | 数据中标题文字大小，单位rpx | string  | 32rpx       | —    |
| headColor       | 数据中标题文字颜色          | string  | #000000     | —    |
| contentFontSize | 数据中内容文字大小，单位rpx | string  | 28rpx       | —    |
| contentColor    | 数据中内容文字颜色          | string  | #333333     | —    |
| expandHeadBg    | 数据中展开的标题背景色      | string  | —           | —    |
| expandContentBg | 数据中展开的内容背景色      | string  | transparent | —    |
| disable         | 设置是否禁止展开            | Boolean | false       | —    |
| showArrow       | 是否展示右侧图标            | Boolean | true        | —    |
| iconColor       | 右侧图标颜色                | string  | —           | —    |
| upimg           | 数据中图片向上箭头          | string  | —           | —    |
| downimg         | 数据中图片向下箭头          | string  | —           | —    |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/foldList.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| click  | 点击事件                                |                               |
| ------ | --------------------------------------- | ----------------------------- |
| change | 事件可以监听当前展开/收起的item 的index | 点击的item的index & 展开/收起 |