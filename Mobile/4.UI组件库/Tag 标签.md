# [Tag 标签](http://mid.chinatowercom.cn:18080/appGuide/ui/tag.html#tag-标签)

Tag 组件一般用于标记关键字、标记特殊状态或区分操作，提供了更加丰富的表现形式，能够较全面的涵盖您的使用场景。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/tag.html#基本使用)

- 通过`text`参数定义标签内容
- 通过`type`设置主题，分别是`default`(主题主色),`primary`(蓝色)，`warning`(黄色-警告)， `error`(红色-错误)，`success`(绿色-成功)，`info`(灰色-信息)，默认为`default`
- 通过`size`参数标签大小，分别是`medium`(中), `large`(大)
- 通过`icon`参数图标，支持本地图标/远程 http 图标地址

```vue
<template>
	<view class="demo-page">
		<ct-demo-card title="基本使用">
			<view class="items">
				<view class="item">
					<ct-ui-tag text="已完成"/>
				</view>
				<view class="item">
					<ct-ui-tag text="编辑" icon="edit"/>
				</view>
			</view>
		</ct-demo-card>
    </view>
  </view>
</template>

<script>
	export default {
		name: 'tag',
		data() {
			return {}
		}
	}
</script>

<style scoped lang="scss">
	.demo-page {
		padding: 20px;
		.h2 {
			font-size: 16px;
			font-weight: 600;
			line-height: 40px;
			padding: 6px 0;
		}
		.items {
			display: flex;
			.item {
				margin-right: 20rpx;
				margin-bottom: 20rpx;
			}
		}
	}
</style>
```

### [设置边框](http://mid.chinatowercom.cn:18080/appGuide/ui/tag.html#设置边框)

- 通过`border`参数设置是否有边框
- 通过`border-color`设置边框颜色

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="边框">
             
      <view class="items">
        <view class="item">
          <ct-ui-tag text="无边框" type="primary" :border="false" />
        </view>
        <view class="item">
          <ct-ui-tag text="自定义边框" type="primary" borderColor="#0c457e" />
        </view>
      </view>
             
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'tag',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;
  .h2 {
    font-size: 16px;
    font-weight: 600;
    line-height: 40px;
    padding: 6px 0;
  }
  .items {
    display: flex;
    .item {
      margin-right: 20rpx;
      margin-bottom: 20rpx;
    }
  }
}
</style>
```

### [设置形状](http://mid.chinatowercom.cn:18080/appGuide/ui/tag.html#设置形状)

- 默认为`square` 方形， 可设置值`circle` 为圆形，类似胶囊形状
- 通过`shape`参数设置形状

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="圆形">
             
      <view class="items">
        <view class="item">
          <ct-ui-tag text="默认" type="default" shape="circle" />
        </view>
        <view class="item">
          <ct-ui-tag text="已完成" type="primary" shape="circle" />
        </view>
        <view class="item">
          <ct-ui-tag text="成功" type="success" shape="circle" />
        </view>
        <view class="item">
          <ct-ui-tag text="警告" type="warning" shape="circle" size="medium" />
        </view>
        <view class="item">
          <ct-ui-tag text="错误" type="danger" shape="circle" size="large" />
        </view>
      </view>
             
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'tag',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;
  .h2 {
    font-size: 16px;
    font-weight: 600;
    line-height: 40px;
    padding: 6px 0;
  }
  .items {
    display: flex;
    .item {
      margin-right: 20rpx;
      margin-bottom: 20rpx;
    }
  }
}
</style>
```

### [设置主题及大小](http://mid.chinatowercom.cn:18080/appGuide/ui/tag.html#设置主题及大小)

- 通过`type`设置主题，分别是`default`(主题主色),`primary`(蓝色)，`warning`(黄色-警告)， `error`(红色-错误)，`success`(绿色-成功)，`info`(灰色-信息)，默认为`default`
- 通过`size`参数标签大小，分别是`medium`(中), `large`(大)

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="类型&大小">
             
      <view class="items">
        <view class="item">
          <ct-ui-tag text="默认" type="default" />
        </view>
        <view class="item">
          <ct-ui-tag text="已完成" type="primary" />
        </view>
        <view class="item">
          <ct-ui-tag text="成功" type="success" />
        </view>
        <view class="item">
          <ct-ui-tag text="警告" type="warning" />
        </view>
        <view class="item">
          <ct-ui-tag text="错误" type="danger" />
        </view>
      </view>
      <view class="items">
        <view class="item">
          <ct-ui-tag text="默认" type="default" size="medium" />
        </view>
        <view class="item">
          <ct-ui-tag text="默认" type="default" size="large" />
        </view>
      </view>
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'tag',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;
  .h2 {
    font-size: 16px;
    font-weight: 600;
    line-height: 40px;
    padding: 6px 0;
  }
  .items {
    display: flex;
    .item {
      margin-right: 20rpx;
      margin-bottom: 20rpx;
    }
  }
}
</style>
```

### [空心效果](http://mid.chinatowercom.cn:18080/appGuide/ui/tag.html#空心效果)

通过`plain`参数设置，是否为空心效果，只有边框，没有背景色

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基本使用">
      <view class="items">
        <view class="item">
          <ct-ui-tag text="默认" type="default" plain />
        </view>
        <view class="item">
          <ct-ui-tag text="已完成" type="primary" plain />
        </view>
        <view class="item">
          <ct-ui-tag text="成功" type="success" plain />
        </view>
        <view class="item">
          <ct-ui-tag text="警告" type="warning" plain />
        </view>
        <view class="item">
          <ct-ui-tag text="错误" type="danger" plain />
        </view>
      </view>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'tag',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;
  .h2 {
    font-size: 16px;
    font-weight: 600;
    line-height: 40px;
    padding: 6px 0;
  }
  .items {
    display: flex;
    .item {
      margin-right: 20rpx;
      margin-bottom: 20rpx;
    }
  }
}
</style>
```

### [空心&填充背景色效果](http://mid.chinatowercom.cn:18080/appGuide/ui/tag.html#空心-填充背景色效果)

通过`plain-fill`参数设置空心并填充背景色，背景色为边框颜色加 20%透明度

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="空心&填充背景色效果">
             
      <view class="items">
        <view class="item">
          <ct-ui-tag text="默认" type="default" plain plainFill />
        </view>
        <view class="item">
          <ct-ui-tag text="已完成" type="primary" plain plainFill />
        </view>
        <view class="item">
          <ct-ui-tag text="成功" type="success" plain plainFill />
        </view>
        <view class="item">
          <ct-ui-tag text="警告" type="warning" plain plainFill />
        </view>
        <view class="item">
          <ct-ui-tag text="错误" type="danger" plain plainFill />
        </view>
      </view>
         
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'tag',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;
  .h2 {
    font-size: 16px;
    font-weight: 600;
    line-height: 40px;
    padding: 6px 0;
  }
  .items {
    display: flex;
    .item {
      margin-right: 20rpx;
      margin-bottom: 20rpx;
    }
  }
}
</style>
```

### [标记标签](http://mid.chinatowercom.cn:18080/appGuide/ui/tag.html#标记标签)

通过`mark`参数设置为标记样式(半圆角)。

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="标记标签">
      <view class="items">
        <view class="item">
          <ct-ui-tag text="默认" type="default" mark />
        </view>
        <view class="item">
          <ct-ui-tag text="已完成" type="primary" mark />
        </view>
        <view class="item">
          <ct-ui-tag text="成功" type="success" mark />
        </view>
        <view class="item">
          <ct-ui-tag text="警告" type="warning" mark size="medium" />
        </view>
        <view class="item">
          <ct-ui-tag text="错误" type="danger" mark size="large" />
        </view>
      </view>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'tag',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;
  .h2 {
    font-size: 16px;
    font-weight: 600;
    line-height: 40px;
    padding: 6px 0;
  }
  .items {
    display: flex;
    .item {
      margin-right: 20rpx;
      margin-bottom: 20rpx;
    }
  }
}
</style>
```

### [可关闭标签](http://mid.chinatowercom.cn:18080/appGuide/ui/tag.html#可关闭标签)

通过`closeable`参数设置为是否可以关闭。

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="可关闭标签">
      <view class="items">
        <view class="item">
          <ct-ui-tag text="默认" type="default" closeable />
        </view>
        <view class="item">
          <ct-ui-tag text="已完成" type="primary" closeable />
        </view>
        <view class="item">
          <ct-ui-tag text="成功" type="success" closeable />
        </view>
        <view class="item">
          <ct-ui-tag text="警告" type="warning" closeable />
        </view>
        <view class="item">
          <ct-ui-tag text="错误" type="danger" closeable />
        </view>
      </view>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'tag',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;
  .h2 {
    font-size: 16px;
    font-weight: 600;
    line-height: 40px;
    padding: 6px 0;
  }
  .items {
    display: flex;
    .item {
      margin-right: 20rpx;
      margin-bottom: 20rpx;
    }
  }
}
</style>
```

### [带 ICON 标签](http://mid.chinatowercom.cn:18080/appGuide/ui/tag.html#带-icon-标签)

通过`icon`参数设置图标，支持本地图标及网络图标，其他参数见[icon 组件](http://mid.chinatowercom.cn:18080/appGuide/ui/icon.html)

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="带ICON标签">
      <view class="items">
        <view class="item">
          <ct-ui-tag text="默认" type="default" icon="chat-dots" />
        </view>
        <view class="item">
          <ct-ui-tag text="已完成" type="primary" icon="eye-close" />
        </view>
        <view class="item">
          <ct-ui-tag text="成功" type="success" icon="checkbox-circle-fill" />
        </view>
        <view class="item">
          <ct-ui-tag text="警告" type="warning" icon="information-fill" />
        </view>
        <view class="item">
          <ct-ui-tag text="错误" type="danger" icon="close-circle" />
        </view>
      </view>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'tag',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;
  .h2 {
    font-size: 16px;
    font-weight: 600;
    line-height: 40px;
    padding: 6px 0;
  }
  .items {
    display: flex;
    .item {
      margin-right: 20rpx;
      margin-bottom: 20rpx;
    }
  }
}
</style>
```

### [自定义颜色](http://mid.chinatowercom.cn:18080/appGuide/ui/tag.html#自定义颜色)

- 通过`color`参数设置背景颜色及文字颜色
- 通过`textColor`参数设置文字颜色（优先级高于`color`）
- 通过`borderColor`参数设置边框颜色

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义颜色">
      <view class="items">
        <view class="item">
          <ct-ui-tag
            text="默认"
            color="#000"
            textColor="#fff"
            borderColor="#f00"
          />
        </view>
        <view class="item">
          <ct-ui-tag
            text="默认"
            color="#000"
            textColor="#fff"
            borderColor="#898080"
            plain
            plainFill
          />
        </view>
      </view>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'tag',
  data() {
    return {}
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;
  .h2 {
    font-size: 16px;
    font-weight: 600;
    line-height: 40px;
    padding: 6px 0;
  }
  .items {
    display: flex;
    .item {
      margin-right: 20rpx;
      margin-bottom: 20rpx;
    }
  }
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/tag.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/tag.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| name        | 标签名称或者索引                             | String｜Number | -       | -                                         |
| ----------- | -------------------------------------------- | -------------- | ------- | ----------------------------------------- |
| type        | 主题类型                                     | String         | default | default\|primary\|warning\|success\|error |
| size        | 大小                                         | String         | -       | medium\|large                             |
| disabled    | 不可用                                       | Boolean        | false   | true\|false                               |
| text        | 内容文本(必填)                               | String\|Number | -       | -                                         |
| color       | 颜色                                         | String         | -       | -                                         |
| textColor   | 内容文本颜色，优先级高于color                | String         | -       | -                                         |
| border      | 是否有border边框                             | Boolean        | true    | true\|false                               |
| borderColor | 边框颜色                                     | String         | -       | -                                         |
| shape       | 形状                                         | String         | square  | square\|circle                            |
| mark        | 是否为标记                                   | Boolean        | false   | true\|false                               |
| direction   | 标记方向                                     | String         | left    | left\|right                               |
| plain       | 是否空心样式                                 | Boolean        | false   | true\|false                               |
| plainFill   | 空心样式时，是否填充背景色                   | Boolean        | false   | true\|false                               |
| icon        | 图标，支持本地图标及网络图标地址             | String         | -       | -                                         |
| iconPrefix  | 本地图标前缀，只有在图标为本地icon时，才生效 | String         | cticon- | -                                         |
| iconColor   | 图标颜色，只有在icon为本地icon时有效         | String         | -       | -                                         |
| iconSize    | 图标大小                                     | String\|Number | -       | -                                         |
| closeable   | 是否可以关闭                                 | Boolean        | false   | true\|false                               |
| closeColor  | 关闭按钮图标的颜色                           | String         | -       | -                                         |
| customStyle | 外部自定义样式                               | Object         | -       | -                                         |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/tag.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

| icon | 自定义图标内容 | -    |
| ---- | -------------- | ---- |
|      |                |      |