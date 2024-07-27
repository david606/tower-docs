# [ActionSheet 操作菜单](http://mid.chinatowercom.cn:18080/appGuide/ui/actionSheet.html#actionsheet-操作菜单)

该组件一般用于底部列表选项、底部分享收藏。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/actionSheet.html#基本使用)

- 通过`show`参数设置是否隐藏显示
- 通过`title`参数设置顶部标题
- 通过`description`参数设置顶部描述文字
- 通过`actions`参数设置操作面板选项列表
- 通过`overlay`参数设置是否显示遮罩层
- 通过`closeOnClickOverlay`参数设置是否可以点击遮罩层关闭
- 通过`selectedIndex`参数设置默认选中项索引
- 通过`showCancel`参数设置是否显示取消按钮
- 通过`closeable`参数设置是否显示关闭按钮

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <view class="bubble-reference">
        <ct-ui-button @click="show = !show">基本使用</ct-ui-button>
      </view>

      <ct-ui-action-sheet
        :show.sync="show"
        title="提示"
        description="这是标题描述"
        :actions="actions"
        overlay
        closeOnClickOverlay
        :selectedIndex="selectedIndex"
        @choose="select"
        @cancel="cancel"
        @close="close"
        @open="open"
      >
      </ct-ui-action-sheet>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      show: false,
      selectedIndex: 1,
      actions: [
        {
          icon: '',
          value: '1',
          title: '选项一',
          subTitle: '',
          color: '',
          disabled: false,
          loading: false
        },
        {
          icon: '',
          value: '2',
          title: '选项二',
          iconColor: '',
          subTitle: '描述',
          color: '',
          disabled: false,
          loading: false
        },
        {
          icon: '',
          iconSize: '',
          value: '3',
          title: '选项三',
          subTitle: '',
          color: '',
          disabled: false,
          loading: false
        }
      ]
    }
  },
  methods: {
    // 选项点击事件
    select(e) {
      this.selectedIndex = e.index
      console.log(e, '选中目标')
    },
    // 取消按钮事件
    cancel() {
      uni.showToast({
        title: '取消按钮事件',
        icon: 'none'
      })
    },
    // 关闭按钮事件
    close() {
      uni.showToast({
        title: '关闭按钮事件',
        icon: 'none'
      })
    },
    // 外部打开事件
    open() {
      uni.showToast({
        title: '打开操作菜单',
        icon: 'none'
      })
    }
  }
}
</script>
```

### [展示取消按钮、关闭按钮](http://mid.chinatowercom.cn:18080/appGuide/ui/actionSheet.html#展示取消按钮、关闭按钮)

- 通过`closeable`参数设置是否显示关闭图标
- 通过`closeIcon`参数设置关闭 icon 图标
- 通过`showCancel`参数设置是否显示取消按钮
- 通过`cancelText`参数设置取消按钮文字

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="展示取消按钮、关闭按钮">
      <view class="bubble-reference">
        <ct-ui-button @click="shows = !shows"
          >展示取消按钮、关闭按钮</ct-ui-button
        >
      </view>

      <ct-ui-action-sheet
        :show.sync="show"
        title="提示"
        description="这是标题描述"
        :actions="actions"
        overlay
        closeOnClickOverlay
        :selectedIndex="selectedIndex"
        showCancel
        closeable
        @choose="select"
        @cancel="cancel"
        @close="close"
        @open="open"
      >
      </ct-ui-action-sheet>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      shows: false,
      actions: [
        {
          icon: '',
          value: '1',
          title: '选项一',
          subTitle: '',
          color: '',
          disabled: false,
          loading: false
        },
        {
          icon: '',
          value: '2',
          title: '选项二',
          iconColor: '',
          subTitle: '',
          color: '',
          disabled: false,
          loading: false
        },
        {
          icon: '',
          iconSize: '',
          value: '3',
          title: '选项三',
          subTitle: '',
          color: '',
          disabled: false,
          loading: false
        }
      ]
    }
  },
  methods: {
    // 选项点击事件
    select(e) {
      this.selectedIndex = e.index
      console.log(e, '选中目标')
    },
    // 取消按钮事件
    cancel() {
      uni.showToast({
        title: '取消按钮事件',
        icon: 'none'
      })
    },
    // 关闭按钮事件
    close() {
      uni.showToast({
        title: '关闭按钮事件',
        icon: 'none'
      })
    },
    // 外部打开事件
    open() {
      uni.showToast({
        title: '打开操作菜单',
        icon: 'none'
      })
    }
  }
}
</script>
```

### [选项状态](http://mid.chinatowercom.cn:18080/appGuide/ui/actionSheet.html#选项状态)

- 通过 `disabled` 参数设置选项是否禁用
- 通过 `loading` 参数设置选项加载状态
- 通过 `icon` 参数设置选项 icon 图标
- 通过 `iconSize`参数设置选项 icon 图标大小
- 通过 `iconColor`参数设置选项 icon 图标颜色
- 通过 `value`参数设置选项 value 值
- 通过 `color`参数设置选项标题文字颜色

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="选项状态">
      <view class="bubble-reference">
        <ct-ui-button @click="show = !show">选项状态</ct-ui-button>
      </view>

      <ct-ui-action-sheet
        :show="show"
        title="提示"
        :actions="actions"
        closeable
        @select="select"
        @cancel="cancel"
        @close="close"
        @open="open"
      >
      </ct-ui-action-sheet>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      show: false,
      actions: [
        {
          icon: '',
          value: '1',
          title: '选项一',
          subTitle: '',
          color: 'red',
          disabled: false,
          loading: false
        },
        {
          icon: 'information-fill',
          value: '2',
          title: '选项二',
          iconColor: '#ff3678',
          subTitle: '描述',
          color: 'red',
          disabled: true,
          loading: false
        },
        {
          icon: 'shield-keyhole-fill',
          iconSize: '15px',
          value: '3',
          title: '选项三',
          subTitle: '描述',
          color: 'red',
          disabled: false,
          loading: true
        }
      ]
    }
  },
  methods: {
    // 选项点击事件
    select(e) {
      this.selectedIndex = e.index
      console.log(e, '选中目标')
    },
    // 取消按钮事件
    cancel() {
      uni.showToast({
        title: '取消按钮事件',
        icon: 'none'
      })
    },
    // 关闭按钮事件
    close() {
      uni.showToast({
        title: '关闭按钮事件',
        icon: 'none'
      })
    },
    // 外部打开事件
    open() {
      uni.showToast({
        title: '打开操作菜单',
        icon: 'none'
      })
    }
  }
}
</script>
```

### [自定义顶部标题、顶部描述文字](http://mid.chinatowercom.cn:18080/appGuide/ui/actionSheet.html#自定义顶部标题、顶部描述文字)

- 通过 slot `title`参数设置自定义顶部标题
- 通过 slot `description`参数设置自定义顶部描述

```vue
<template>
	<view class="demo-page">
		<ct-demo-card title="自定义顶部标题、顶部描述文字">
			<view class="bubble-reference">
				<ct-ui-button @click="show = !show">自定义顶部标题、顶部描述文字</ct-ui-button>
			</view>

			<ct-ui-action-sheet
					:show.sync="show"
					:actions="actions"
					:duration="600"
					closeIcon="close-circle-fill"
					closeable
					@choose="select"
					@cancel="cancel"
					@close="close"
					@open="open"
			>
					<template #title>
							<view class="" style="padding: 15px 0; text-align: center">消息</view>
					</template>
					<template #description>
							<view class="" style="padding: 15px 0; text-align: center">这是消息描述</view>
					</template>
			</ct-ui-action-sheet>
	</view>
</template>

<script>
	export default {
		data() {
			return {
        show: false,
				actions: [
					{
						icon: '',
						value: '1',
						title: '选项一',
						subTitle: '',
						color: 'red',
						disabled: false,
						loading: false
					},
					{
						icon: 'information-fill',
						value: '2',
						title: '选项二',
						iconColor: '#ff3678',
						subTitle: '描述',
						color: 'red',
						disabled: true,
						loading: false
					},
					{
						icon: 'shield-keyhole-fill',
						iconSize: '15px',
						value: '3',
						title: '选项三',
						subTitle: '描述',
						color: 'red',
						disabled: false,
						loading: true
					}
        ]
			}
		},
		methods: {
      // 选项点击事件
			select(e) {
				this.selectedIndex = e.index
				console.log(e, '选中目标')
			},
			// 取消按钮事件
			cancel() {
					uni.showToast({
							title: '取消按钮事件',
							icon: 'none',
					})
			},
			// 关闭按钮事件
			close() {
					uni.showToast({
							title: '关闭按钮事件',
							icon: 'none',
					})
			},
			// 外部打开事件
			open() {
					uni.showToast({
							title: '打开操作菜单',
							icon: 'none',
					})
			},
		}
	}
</script>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/actionSheet.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/actionSheet.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| show                | 是否隐藏显示操作面板        | Boolean          | false             | false \| true | v1.0.18+ |
| ------------------- | --------------------------- | ---------------- | ----------------- | ------------- | -------- |
| title               | 顶部标题                    | String           | -                 | -             | v1.0.18+ |
| titleSize           | 顶部标题大小,默认单位px     | String \| Number | 40rpx             | -             | v1.0.18+ |
| titleColor          | 顶部标题颜色                | String           | #262F40           | -             | v1.0.18+ |
| description         | 顶部文字描述                | String           | -                 | -             | v1.0.18+ |
| descriptionSize     | 顶部描述文字大小,默认单位px | String \| Number | 34rpx             | -             | v1.0.18+ |
| descriptionColor    | 顶部描述文字颜色            | String           | #8590a6           | -             | v1.0.18+ |
| color               | 默认选项的颜色              | String           | #262F40           | -             | v1.0.18+ |
| activeColor         | 默认选中项字体颜色          | String           | #EB4B4B           | -             | v1.0.18+ |
| size                | 选项大小                    | String \| Number | 34rpx             | -             | v1.0.18+ |
| actions             | 操作列表数据                | Array            | []                | -             | v1.0.18+ |
| duration            | 隐藏动画时长，默认300ms     | Number           | 300               | -             | v1.0.18+ |
| zIndex              | 操作菜单层级                | String \| Number | 1000              | -             | v1.0.18+ |
| round               | 操作面板圆角值              | Number \| String | 20rpx             | -             | v1.0.18+ |
| overlay             | 是否显示遮罩层              | Boolean          | true              | false \| true | v1.0.18+ |
| overlayBgColor      | 蒙版背景色                  | String           | rgba(0, 0, 0, .2) | false \| true | v1.0.18+ |
| closeOnClickOverlay | 是否可以点击遮罩层关闭      | Boolean          | true              | false \| true | v1.0.18+ |
| selectedIndex       | 默认选中项第几个            | String \| Number | -                 | -             | v1.0.18+ |
| color               | 默认选中项字体颜色          | String           | #000              | -             | v1.0.18+ |
| closeable           | 是否显示关闭图标            | Boolean          | false             | false \| true | v1.0.18+ |
| closeIcon           | 设置关闭图标                | String           | close             | -             | v1.0.18+ |
| showCancel          | 是否显示取消按钮            | Boolean          | false             | false \| true | v1.0.18+ |
| cancelText          | 取消按钮文字                | String           | 取消              | -             | v1.0.18+ |
| safeAreaInsetBottom | 是否为留出底部安全距离      | Boolean          | true              | true \| false | v1.0.18+ |

#### [Action 列表数据结构](http://mid.chinatowercom.cn:18080/appGuide/ui/actionSheet.html#action-列表数据结构)

| 参数 | 说明 | 类型 |
| ---- | ---- | ---- |
|      |      |      |

| icon      | 选项icon图标     | String           |
| --------- | ---------------- | ---------------- |
| iconSize  | icon图标大小     | String           |
| iconColor | icon图标颜色     | String           |
| value     | 选项value        | String \| Number |
| title     | 选项标题         | String           |
| subTitle  | 选项文字描述     | String           |
| color     | 选项标题字体颜色 | String           |
| disabled  | 选项禁用状态     | Boolean          |
| loading   | 选项加载状态     | Boolean          |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/actionSheet.html#events)

| 事件名 | 说明 | 返回值 | 版本 |
| ------ | ---- | ------ | ---- |
|        |      |        |      |

| choose | 点击选项事件         | options | v1.0.18+ |
| ------ | -------------------- | ------- | -------- |
| cancel | 点击取消按钮事件     | -       | v1.0.18+ |
| close  | 点击关闭图标事件     | -       | v1.0.18+ |
| open   | 外部开启操作菜单事件 | -       | v1.0.18+ |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/actionSheet.html#slots)

| 名称 | 说明 | 版本 |
| ---- | ---- | ---- |
|      |      |      |

| title       | 自定义顶部标题     | v1.0.18+ |
| ----------- | ------------------ | -------- |
| description | 自定义顶部标题描述 | v1.0.18+ |