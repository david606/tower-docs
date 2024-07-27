# 

该组件主要用于对列表进行单项选择或多项选择。组件暂不支持多选列表半选中状态。

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/checkbox.html#基本使用)

- 通过`list`参数传入单选、多选列表对象数组，默认为`[]`
- 通过`defaultSelected`参数设置多选列表是否默认全选
- 通过`choice`参数设置列表的样式为单选或多选
- 通过`defaultCheck`参数设置默认选中项

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="多选列表">
      <ct-ui-checkbox
        :list="multipleList"
        :defaultSelected="true"
        :defaultCheck="defaultCheck"
        :choice="multiple"
      ></ct-ui-checkbox>
    </ct-demo-card>
    <ct-demo-card title="单选列表">
      <ct-ui-checkbox
        :list="singleList"
        :defaultSelected="false"
        :defaultCheck="defaultCheck"
        :choice="single"
      ></ct-ui-checkbox>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'checkbox',
  data() {
    return {
      singleList: [
        {
          id: '1',
          title: '标题1'
        },
        {
          id: '2',
          title: '标题2'
        }
      ],
      multipleList: [
        {
          id: '1',
          title: '标题1'
        },
        {
          id: '2',
          title: '标题2'
        }
      ],
      single: false, // 单选列表
      multiple: true, // 多选列表
      defaultCheck: [0] // 默认选中项
    }
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;

  .title {
    margin: 20px 0;
  }
}
</style>
```

### [手动控制全选](http://mid.chinatowercom.cn:18080/appGuide/ui/checkbox.html#手动控制全选)

通过绑定`ref`进行手动控制多选列表的全选

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="手动控制">
      <ct-ui-checkbox :list="list" ref="checkbox"></ct-ui-checkbox>
      <ct-ui-button @click="Select">点击全选</ct-ui-button>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'checkbox',
  data() {
    return {
      list: [
        {
          id: '1',
          title: '标题1'
        },
        {
          id: '2',
          title: '标题2'
        }
      ]
    }
  },
  methods: {
    Select() {
      this.$refs.checkbox.isAllSelected = true
    }
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;

  .title {
    margin: 20px 0;
  }
}
</style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/checkbox.html#事件监听)

`click`事件监听列表内容点击时触发，`checkboxClick`事件可以监听单选/多选选中或取消时触发，`checkedList`事件监听选中的数组发生变化时触发

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="事件监听">
      <ct-ui-checkbox
        :list="list"
        :defaultSelected="true"
        :choice="true"
        @click="click"
        @checkboxClick="checkboxClick"
        @checkedList="checkedList"
      ></ct-ui-checkbox>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'checkbox',
  data() {
    return {
      list: [
        {
          id: '1',
          title: '标题1'
        },
        {
          id: '2',
          title: '标题2'
        }
      ]
    }
  },
  methods: {
    checkboxClick(item) {
      console.log(item)
    },
    click(item) {
      console.log(item)
    },
    checkedList(newList, oldList) {
      console.log(newList, oldList) // 选中前的数组，选中后的数组
    }
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;

  .title {
    margin: 20px 0;
  }
}
</style>
```

### [使用插槽](http://mid.chinatowercom.cn:18080/appGuide/ui/checkbox.html#使用插槽)

通过设置插槽内容自行进行使用

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="使用插槽">
      <ct-ui-checkbox :list="list" :defaultSelected="false" :choice="true">
        <template v-slot:top>
          <text class="select-all">插槽自定义多选</text>
        </template>
        <template v-slot:center="{item}">
          <ct-ui-list :title="item.title" :content="item.content"></ct-ui-list>
        </template>
      </ct-ui-checkbox>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'checkbox',
  data() {
    return {
      list: [
        {
          id: '1',
          title: '标题1',
          content: '2021.10.14 11:26:33'
        },
        {
          id: '2',
          title: '标题2',
          content: '2021.10.14 11:26:33'
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss">
.demo-page {
  padding: 20px;

  .title {
    margin: 20px 0;
  }
}
</style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/checkbox.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/checkbox.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 | 版本 |
| ---- | ---- | ---- | ------ | ------ | ---- |
|      |      |      |        |        |      |

| *(必填)list     | 单选、多选列表                                               | Array   | []    | -                  |          |
| --------------- | ------------------------------------------------------------ | ------- | ----- | ------------------ | -------- |
| choice          | 单选或多选                                                   | Boolean | true  | true ｜ false      |          |
| showCheckAllBtn | 是否显示全选按钮（choice = true 起效）                       | Boolean | true  | true ｜ false      | V1.0.26+ |
| defaultSelected | 是否默认全选                                                 | Boolean | false | true ｜ false      |          |
| defaultCheck    | 默认选中项                                                   | Array   | []    | [0,1]              |          |
| mode            | 默认选中值的类型（列表的索引，对应数据的id）默认为列表的索引 | string  | index | ['index', 'value'] |          |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/checkbox.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| click         | 列表内容点击时触发        | 点击的列表对象             |
| ------------- | ------------------------- | -------------------------- |
| checkboxClick | 单选/多选选中或取消时触发 | 点击的列表对象             |
| checkedList   | 选中的数组发生变化时触发  | 选中前的数组，选中后的数组 |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/checkbox.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

| top    | 自定义全选按钮       | -    |
| ------ | -------------------- | ---- |
| center | 自定义单选、多选内容 | item |