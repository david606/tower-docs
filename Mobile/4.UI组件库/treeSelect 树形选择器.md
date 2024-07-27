# 

该组件主要对多层数据进行展示，并提供选择功能 **`(v1.0.24+支持)`**

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/treeSelect.html#基本使用)

- 通过`options`参数设置显示内容(每一项数据可添加`diasble`禁用属性)
- 通过`idKey`参数设置数据唯一的 id 的 key（默认值为`id`）
- 通过`rangeKey`参数设置选项文字的 key（默认值为`label`）
- 通过`title`参数设置标题内容

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="树形结构使用" class="mb">
      <ct-ui-button btnType="confirm" @click="showTree" foneSize="14"
        >显示树形选择器</ct-ui-button
      >
    </ct-demo-card>

    <ct-ui-tree-select
      ref="tkitree"
      :options="options"
      :title="title"
      rangeKey="name"
      @confirm="treeConfirm"
    ></ct-ui-tree-select>
  </view>
</template>

<script>
let testList = [
  {
    id: 1,
    name: '北京市',
    children: [
      {
        id: 11,
        name: '市辖区',
        children: [
          {
            id: 111,
            name: '西城区',
            children: [
              {
                id: 1111,
                name: '南河沿大街',
                children: [
                  {
                    id: 11111,
                    name: '紫金宫饭店',
                    disable: true
                  }
                ]
              }
            ]
          },
          {
            id: 112,
            name: '东城区'
          },
          {
            id: 113,
            name: '朝阳区'
          },
          {
            id: 114,
            name: '丰台区'
          }
        ]
      }
    ]
  },
  {
    id: 4,
    name: '河南省'
  },
  {
    id: 5,
    name: '湖北省'
  },
  {
    id: 6,
    name: '湖南省'
  }
]
export default {
  data() {
    return {
      options: [],
      title: '标题 '
    }
  },
  onLoad() {
    setTimeout(() => {
      this.options = testList
    }, 300)
  },
  methods: {
    // 按钮点击回调事件
    treeConfirm(type, e) {
      console.log(type, e)
    },
    // 显示树形选择器
    showTree() {
      this.$refs.tkitree.show()
    }
  }
}
</script>
<style scoped>
.mb .ct-btn {
  margin-top: 15rpx;
}
</style>
```

### [树形结构功能项配置](http://mid.chinatowercom.cn:18080/appGuide/ui/treeSelect.html#树形结构功能项配置)

- 通过`level`参数设置树结构可显示的层级
- 通过`multiple`参数设置数据是否可以多选
- 通过`value`参数设置默认选中项
- 通过`selectParent`参数设置是否可以选中父级
- 通过`foldAll`参数设置折叠后再次打开是否关闭所有已经打开的子集

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="树形结构使用" class="mb">
      <ct-ui-button btnType="confirm" @click="showTree" foneSize="14"
        >显示树形选择器</ct-ui-button
      >
    </ct-demo-card>

    <ct-ui-tree-select
      ref="tkitree"
      :options="options"
      :title="title"
      rangeKey="name"
      @confirm="treeConfirm"
    ></ct-ui-tree-select>
  </view>
</template>

<script>
let testList = [
  {
    id: 1,
    name: '北京市',
    children: [
      {
        id: 11,
        name: '市辖区',
        children: [
          {
            id: 111,
            name: '西城区',
            children: [
              {
                id: 1111,
                name: '南河沿大街',
                children: [
                  {
                    id: 11111,
                    name: '紫金宫饭店',
                    disable: true
                  }
                ]
              }
            ]
          },
          {
            id: 112,
            name: '东城区'
          },
          {
            id: 113,
            name: '朝阳区'
          },
          {
            id: 114,
            name: '丰台区'
          }
        ]
      }
    ]
  },
  {
    id: 4,
    name: '河南省'
  },
  {
    id: 5,
    name: '湖北省'
  },
  {
    id: 6,
    name: '湖南省'
  }
]
export default {
  data() {
    return {
      options: [],
      title: '标题 '
    }
  },
  onLoad() {
    setTimeout(() => {
      this.options = testList
    }, 300)
  },
  methods: {
    // 按钮点击回调事件
    treeConfirm(type, e) {
      console.log(type, e)
    },
    // 显示树形选择器
    showTree() {
      this.$refs.tkitree.show()
    }
  }
}
</script>
<style scoped>
.mb .ct-btn {
  margin-top: 15rpx;
}
</style>
```

### [选项禁用功能配置](http://mid.chinatowercom.cn:18080/appGuide/ui/treeSelect.html#选项禁用功能配置)

- 通过`disable`参数设置所有选项是否禁用（优先级低于`options`数据项中的`disable`属性）

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="树形结构使用" class="mb">
      <ct-ui-button btnType="confirm" @click="showTree" foneSize="14"
        >显示树形选择器</ct-ui-button
      >
    </ct-demo-card>

    <ct-ui-tree-select
      ref="tkitree"
      :options="options"
      :title="title"
      :value="value"
      :disable="disable"
      rangeKey="name"
      @confirm="treeConfirm"
    ></ct-ui-tree-select>
  </view>
</template>

<script>
let testList = [
  {
    id: 1,
    name: '北京市',
    children: [
      {
        id: 11,
        name: '市辖区',
        children: [
          {
            id: 111,
            name: '西城区',
            children: [
              {
                id: 1111,
                name: '南河沿大街',
                children: [
                  {
                    id: 11111,
                    name: '紫金宫饭店'
                  }
                ]
              }
            ]
          },
          {
            id: 112,
            name: '东城区',
            disable: false
          },
          {
            id: 113,
            name: '朝阳区',
            disable: false
          },
          {
            id: 114,
            name: '丰台区',
            disable: false
          }
        ]
      }
    ]
  },
  {
    id: 2,
    name: '河北省',
    children: [
      {
        id: 21,
        name: '石家庄市'
      },
      {
        id: 22,
        name: '唐山市'
      },
      {
        id: 23,
        name: '秦皇岛市'
      }
    ]
  }
]
export default {
  data() {
    return {
      options: [],
      multiple: true,
      value: [112, 114],
      title: '标题',
      disable: true
    }
  },
  onLoad() {
    setTimeout(() => {
      this.options = testList
    }, 300)
  },
  methods: {
    // 按钮点击回调事件
    treeConfirm(type, e) {
      console.log(type, e)
    },
    // 显示树形选择器
    showTree() {
      this.$refs.tkitree.show()
    }
  }
}
</script>
<style scoped>
.mb .ct-btn {
  margin-top: 15rpx;
}
</style>
```

### [显示样式配置](http://mid.chinatowercom.cn:18080/appGuide/ui/treeSelect.html#显示样式配置)

- 通过`openIcon`参数设置展开项的图标 icon
- 通过`closeIcon`参数设置折叠项的图标 icon
- 通过`color`参数设置默认选项的文字颜色
- 通过`activeColor`参数设置选中项的文字颜色
- 通过`size`参数设置选项文字以及左侧 icon 大小
- 通过`activeSize`参数设置选中项文字以及左侧 icon 大小
- 通过`bold`参数设置选中项文字以及左侧 icon 是否加粗
- 通过`height`参数设置内容区域的高度
- 通过`titleColor`参数设置标题颜色
- 通过`customTitleStyle`参数设置标题的样式（样式优先级高于颜色属性）
- 通过`itemHeight`参数设置每一项的高度
- 通过`lastIcon`参数设置没有子集的 icon
- 通过`optionBoxColor`参数设置选项框的颜色

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="树形结构使用" class="mb">
      <ct-ui-button btnType="confirm" @click="showTree" foneSize="14"
        >显示树形选择器</ct-ui-button
      >
    </ct-demo-card>

    <ct-ui-tree-select
      ref="tkitree"
      :options="options"
      :title="title"
      :openIcon="openIcon"
      :color="color"
      :closeIcon="closeIcon"
      :activeColor="activeColor"
      :size="size"
      :activeSize="activeSize"
      :bold="bold"
      :height="height"
      :titleColor="titleColor"
      :itemHeight="itemHeight"
      :lastIcon="lastIcon"
      rangeKey="name"
      @confirm="treeConfirm"
      :optionBoxColor="optionBoxColor"
    ></ct-ui-tree-select>
  </view>
</template>

<script>
let testList = [
  {
    id: 1,
    name: '北京市',
    children: [
      {
        id: 11,
        name: '市辖区',
        children: [
          {
            id: 111,
            name: '西城区',
            children: [
              {
                id: 1111,
                name: '南河沿大街',
                children: [
                  {
                    id: 11111,
                    name: '紫金宫饭店',
                    disable: true
                  }
                ]
              }
            ]
          },
          {
            id: 112,
            name: '东城区'
          },
          {
            id: 113,
            name: '朝阳区'
          },
          {
            id: 114,
            name: '丰台区'
          }
        ]
      }
    ]
  },
  {
    id: 4,
    name: '河南省'
  },
  {
    id: 5,
    name: '湖北省'
  },
  {
    id: 6,
    name: '湖南省'
  }
]
export default {
  data() {
    return {
      options: [],
      title: '标题 ',
      openIcon: 'minus-square',
      closeIcon: 'plus-square',
      color: '#3164f6',
      activeColor: '#eb4b4b',
      size: '28',
      activeSize: '48',
      bold: true,
      height: 900,
      titleColor: 'red',
      itemHeight: 100,
      lastIcon: 'info-fill',
      optionBoxColor: 'red'
    }
  },
  onLoad() {
    setTimeout(() => {
      this.options = testList
    }, 300)
  },
  methods: {
    // 按钮点击回调事件
    treeConfirm(type, e) {
      console.log(type, e)
    },
    // 显示树形选择器
    showTree() {
      this.$refs.tkitree.show()
    }
  }
}
</script>
<style scoped>
.mb .ct-btn {
  margin-top: 15rpx;
}
</style>
```

### [按钮样式配置功能项](http://mid.chinatowercom.cn:18080/appGuide/ui/treeSelect.html#按钮样式配置功能项)

- 通过`showConfirmButton`参数设置是否显示右侧按钮
- 通过`showCancelButton`参数设置是否显示左侧按钮
- 通过`confirmText`参数设置右侧按钮的文本
- 通过`cancelText`参数设置左侧按钮的文本
- 通过`confirmTextSize`参数设置右侧按钮的文字大小
- 通过`cancelTextSize`参数设置左侧按钮的文字大小
- 通过`confirmColor`参数设置右侧按钮颜色（在`operatePosition`为`top`时生效）
- 通过`cancelColor`参数设置左侧按钮颜色（在`operatePosition`为`top`时生效）
- 通过`operatePosition`参数这是按钮位置

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="树形结构使用" class="mb">
      <ct-ui-button btnType="confirm" @click="showTree" foneSize="14"
        >显示树形选择器</ct-ui-button
      >
    </ct-demo-card>

    <ct-ui-tree-select
      ref="tkitree"
      :options="options"
      :title="title"
      :showConfirmButton="showConfirmButton"
      :showCancelButton="showCancelButton"
      :confirmText="confirmText"
      :cancelText="cancelText"
      :confirmTextSize="confirmTextSize"
      :cancelTextSize="cancelTextSize"
      :confirmColor="confirmColor"
      :cancelColor="cancelColor"
      :operatePosition="operatePosition"
      rangeKey="name"
      @confirm="treeConfirm"
    ></ct-ui-tree-select>
  </view>
</template>

<script>
let testList = [
  {
    id: 1,
    name: '北京市',
    children: [
      {
        id: 11,
        name: '市辖区',
        children: [
          {
            id: 111,
            name: '西城区',
            children: [
              {
                id: 1111,
                name: '南河沿大街',
                children: [
                  {
                    id: 11111,
                    name: '紫金宫饭店',
                    disable: true
                  }
                ]
              }
            ]
          },
          {
            id: 112,
            name: '东城区'
          },
          {
            id: 113,
            name: '朝阳区'
          },
          {
            id: 114,
            name: '丰台区'
          }
        ]
      }
    ]
  },
  {
    id: 4,
    name: '河南省'
  },
  {
    id: 5,
    name: '湖北省'
  },
  {
    id: 6,
    name: '湖南省'
  }
]
export default {
  data() {
    return {
      options: [],
      title: '标题 ',
      showConfirmButton: true,
      showCancelButton: true,
      confirmText: '右侧',
      cancelText: '左侧',
      confirmTextSize: '48',
      cancelTextSize: 48,
      confirmColor: 'red',
      cancelColor: 'red',
      operatePosition: 'top'
    }
  },
  onLoad() {
    setTimeout(() => {
      this.options = testList
    }, 300)
  },
  methods: {
    // 按钮点击回调事件
    treeConfirm(type, e) {
      console.log(type, e)
    },
    // 显示树形选择器
    showTree() {
      this.$refs.tkitree.show()
    }
  }
}
</script>
<style scoped>
.mb .ct-btn {
  margin-top: 15rpx;
}
</style>
```

### [按钮样式配置功能项(底部)](http://mid.chinatowercom.cn:18080/appGuide/ui/treeSelect.html#按钮样式配置功能项-底部)

- 通过`btnShape`参数设置按钮形状
- 通过`btnHeight`参数设置按钮高度
- 通过`confirmButtonWidth`参数设置确定按钮的宽度
- 通过`cancelButtonWidth`参数设置取消按钮的宽度
- 通过`btnReverse`参数设置按钮是否反转

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="树形结构使用" class="mb">
      <ct-ui-button btnType="confirm" @click="showTree" foneSize="14"
        >显示树形选择器</ct-ui-button
      >
    </ct-demo-card>

    <ct-ui-tree-select
      ref="tkitree"
      :options="options"
      :title="title"
      :operatePosition="operatePosition"
      :btnShape="btnShape"
      :btnHeight="btnHeight"
      :confirmButtonWidth="confirmButtonWidth"
      :cancelButtonWidth="cancelButtonWidth"
      :btnReverse="btnReverse"
      rangeKey="name"
      @confirm="treeConfirm"
    ></ct-ui-tree-select>
  </view>
</template>

<script>
let testList = [
  {
    id: 1,
    name: '北京市',
    children: [
      {
        id: 11,
        name: '市辖区',
        children: [
          {
            id: 111,
            name: '西城区',
            children: [
              {
                id: 1111,
                name: '南河沿大街',
                children: [
                  {
                    id: 11111,
                    name: '紫金宫饭店',
                    disable: true
                  }
                ]
              }
            ]
          },
          {
            id: 112,
            name: '东城区'
          },
          {
            id: 113,
            name: '朝阳区'
          },
          {
            id: 114,
            name: '丰台区'
          }
        ]
      }
    ]
  },
  {
    id: 4,
    name: '河南省'
  },
  {
    id: 5,
    name: '湖北省'
  },
  {
    id: 6,
    name: '湖南省'
  }
]
export default {
  data() {
    return {
      options: [],
      title: '标题 ',
      operatePosition: 'bottom',
      btnShape: '20rpx',
      btnHeight: '40',
      confirmButtonWidth: '20%',
      cancelButtonWidth: '80',
      btnReverse: true
    }
  },
  onLoad() {
    setTimeout(() => {
      this.options = testList
    }, 300)
  },
  methods: {
    // 按钮点击回调事件
    treeConfirm(type, e) {
      console.log(type, e)
    },
    // 显示树形选择器
    showTree() {
      this.$refs.tkitree.show()
    }
  }
}
</script>
<style scoped>
.mb .ct-btn {
  margin-top: 15rpx;
}
</style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/treeSelect.html#事件监听)

`confirm`事件可以监听按钮点击事件，`confirm`会传出两个数据（`type`， `value`）,`type`表示按钮的类型（`left` 或者 `right`），`value`表示当前选中项

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="树形结构使用" class="mb">
      <ct-ui-button btnType="confirm" @click="showTree" foneSize="14"
        >显示树形选择器</ct-ui-button
      >
    </ct-demo-card>

    <ct-ui-tree-select
      ref="tkitree"
      :options="options"
      :title="title"
      rangeKey="name"
      @confirm="treeConfirm"
    ></ct-ui-tree-select>
  </view>
</template>

<script>
let testList = [
  {
    id: 1,
    name: '北京市',
    children: [
      {
        id: 11,
        name: '市辖区',
        children: [
          {
            id: 111,
            name: '西城区',
            children: [
              {
                id: 1111,
                name: '南河沿大街',
                children: [
                  {
                    id: 11111,
                    name: '紫金宫饭店',
                    disable: true
                  }
                ]
              }
            ]
          },
          {
            id: 112,
            name: '东城区'
          },
          {
            id: 113,
            name: '朝阳区'
          },
          {
            id: 114,
            name: '丰台区'
          }
        ]
      }
    ]
  },
  {
    id: 4,
    name: '河南省'
  },
  {
    id: 5,
    name: '湖北省'
  },
  {
    id: 6,
    name: '湖南省'
  }
]
export default {
  data() {
    return {
      options: [],
      title: '标题 '
    }
  },
  onLoad() {
    setTimeout(() => {
      this.options = testList
    }, 300)
  },
  methods: {
    // 按钮点击回调事件
    treeConfirm(type, e) {
      console.log(type, e)
    },
    // 显示树形选择器
    showTree() {
      this.$refs.tkitree.show()
    }
  }
}
</script>
<style scoped>
.mb .ct-btn {
  margin-top: 15rpx;
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/treeSelect.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/treeSelect.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 可用版本 |
| ---- | ---- | ---- | ------ | ------ | -------- |
|      |      |      |        |        |          |

| options            | 数据内容                                 | Array            | []               | -             | v1.0.24+ |
| ------------------ | ---------------------------------------- | ---------------- | ---------------- | ------------- | -------- |
| level              | 层级                                     | [Number, String] | Number.MAX_VALUE | -             | v1.0.24+ |
| multiple           | 是否可以多选                             | Boolean          | true             | true \| false | v1.0.24+ |
| disable            | 是否禁用                                 | Boolean          | false            | true \| false | v1.0.24+ |
| openIcon           | 展开时候的icon                           | String           | rrow-drop-down   | -             | v1.0.24+ |
| closeIcon          | 折叠时候的icon                           | String           | arrow-right-fill | -             | v1.0.24+ |
| value              | 默认选中项的数据                         | Array            | []               | -             | v1.0.24+ |
| selectParent       | 是否可以选择父级                         | Boolean          | false            | true \| false | v1.0.24+ |
| color              | 默认选项的文字颜色                       | String           | #262f40          | -             | v1.0.24+ |
| activeColor        | 选中项的文字颜色                         | String           | #3164f6          | -             | v1.0.24+ |
| size               | 选项文字以及左侧icon大小                 | [Number, String] | 14               | -             | v1.0.24+ |
| activeSize         | 选中项文字以及左侧icon大小               | [Number, String] | 14               | -             | v1.0.24+ |
| bold               | 选中项文字是否加粗                       | Boolean          | false            | true \| false | v1.0.24+ |
| foldAll            | 折叠时是否关闭所有已经打开的子集         | Boolean          | false            | true \| false | v1.0.24+ |
| height             | 内容区域的高度                           | [Number, String] | 800              | -             | v1.0.24+ |
| idKey              | 数据唯一的id的key                        | String           | id               | -             | v1.0.24+ |
| rangeKey           | 数据唯一的id的key                        | String           | label            | -             | v1.0.24+ |
| title              | 标题内容                                 | String           |                  | -             | v1.0.24+ |
| titleColor         | 标题颜色                                 | String           | #262f40          | -             | v1.0.24+ |
| customTitleStyle   | 自定义标题的样式，样式优先级高于颜色属性 | Object           | {}               | -             | v1.0.24+ |
| itemHeight         | 每一项的高度                             | [Number, String] | 80               | -             | v1.0.24+ |
| showConfirmButton  | 是否显示右侧按钮                         | Boolean          | true             | true \| false | v1.0.24+ |
| showCancelButton   | 是否显示左侧按钮                         | Boolean          | true             | true \| false | v1.0.24+ |
| confirmText        | 右侧按钮的文本                           | String           | 确定             | -             | v1.0.24+ |
| cancelText         | 左侧按钮的文本                           | String           | 取消             | -             | v1.0.24+ |
| confirmTextSize    | 右侧按钮文字大小                         | [Number, String] | 14               | -             | v1.0.24+ |
| cancelTextSize     | 左侧按钮文字大小                         | [Number, String] | 14               | -             | v1.0.24+ |
| confirmColor       | 右侧按钮颜色                             | String           | #3164f6          | -             | v1.0.24+ |
| cancelColor        | 左侧按钮颜色                             | String           | #3164f6          | -             | v1.0.24+ |
| lastIcon           | 没有子集的ic                             | String           |                  | -             | v1.0.24+ |
| optionBoxColor     | 选项框选中的颜色                         | String           | #3164f6          | -             | v1.0.24+ |
| operatePosition    | 按钮的位置                               | String           | top              | top \| bottom | v1.0.24+ |
| btnReverse         | 按钮反转                                 | Boolean          | false            | false \| true | v1.0.24+ |
| btnShape           | 按钮形状                                 | [Number, String] | 4rpx             | -             | v1.0.24+ |
| btnHeight          | 按钮高度                                 | [Number, String] | 36               | -             | v1.0.24+ |
| confirmButtonWidth | 确定按钮宽度                             | [Number, String] | 65               | -             | v1.0.24+ |
| cancelButtonWidth  | 取消按钮宽度                             | [Number, String] | 35               | -             | v1.0.24+ |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/treeSelect.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| confirm | 点击确定按钮时触发 | 选中的数据 |
| ------- | ------------------ | ---------- |
| cancel  | 点击取消按钮时触发 | 选中的数据 |