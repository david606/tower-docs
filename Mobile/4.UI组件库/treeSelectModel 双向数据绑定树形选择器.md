# [treeSelectModel 双向数据绑定树形选择器](http://mid.chinatowercom.cn:18080/appGuide/ui/treeSelectModel.html#treeselectmodel-双向数据绑定树形选择器)

该组件主要对多层数据进行展示提供选择功能并双向绑定

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/treeSelectModel.html#基本使用)

- 参数使用完全可参考`treeSelect`组件，使用方式一样
- 添加`tagProps`字段，可控制`tag`的样式，`tagProps`字段为对象，可在其中添加`multiTag`组件可使用的所有参数

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="树形结构使用" class="mb">
      <ct-ui-tree-select-model
        ref="tkitree"
        :selectParent="selectParent"
        :multiple="multiple"
        :options="options"
        :foldAll="flod"
        :value.sync="value"
        rangeKey="name"
        :level="level"
        :title="title"
        :operatePosition="operatePosition"
        :tagProps="{color: '#ffffff', bgColor: '#eb4b4b'}"
        @confirm="treeConfirm"
      ></ct-ui-tree-select-model>
    </ct-demo-card>

    <ct-demo-card title="配置参数" class="mb">
      value的值{{ value }}
      <ct-ui-button
        btnType="confirm"
        @click="multiple = !multiple"
        foneSize="14"
        >切换单、多选：{{ multiple ? '多选' : '单选' }}</ct-ui-button
      >
      <ct-ui-button btnType="confirm" @click="flod = !flod" foneSize="14"
        >折叠已打开的子集：{{ flod ? '折叠' : '不折叠' }}</ct-ui-button
      >
      <ct-ui-button
        btnType="confirm"
        @click="selectParent = !selectParent"
        foneSize="14"
        >切换父级可选：{{ selectParent ? '可选' : '不可选' }}</ct-ui-button
      >
      <ct-ui-button btnType="confirm" @click="level++" foneSize="14"
        >切换当前显示层级：{{ level }}</ct-ui-button
      >
      <ct-ui-button
        btnType="confirm"
        @click="operatePosition = operatePosition === 'top' ? 'bottom' : 'top'"
        >切换按钮位置：{{ operatePosition }}</ct-ui-button
      >
    </ct-demo-card>
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
  },
  {
    id: 3,
    name: '山东省',
    children: [
      {
        id: 31,
        name: '济南市',
        children: [
          {
            id: 311,
            name: '历下区',
            children: [
              {
                id: 3131,
                name: '解放路街道办事处'
              }
            ]
          },
          {
            id: 312,
            name: '槐荫区'
          },
          {
            id: 313,
            name: '天桥区'
          },
          {
            id: 314,
            name: '历城区'
          },
          {
            id: 315,
            name: '长清区'
          }
        ]
      },
      {
        id: 32,
        name: '青岛市'
      },
      {
        id: 33,
        name: '临沂市',
        children: [
          {
            id: 331,
            name: '兰山区',
            children: [
              {
                id: 3331,
                name: '金雀山街道'
              }
            ]
          },
          {
            id: 332,
            name: '河东区'
          },
          {
            id: 333,
            name: '罗庄区',
            children: [
              {
                id: 3331,
                name: '盛庄街道'
              }
            ]
          }
        ]
      },
      {
        id: 34,
        name: '日照市'
      },
      {
        id: 35,
        name: '淄博市'
      },
      {
        id: 36,
        name: '枣庄市'
      },
      {
        id: 37,
        name: '东营市'
      },
      {
        id: 38,
        name: '潍坊市'
      },
      {
        id: 39,
        name: '烟台市'
      },
      {
        id: 40,
        name: '济宁市'
      },
      {
        id: 41,
        name: '泰安市'
      },
      {
        id: 42,
        name: '威海市'
      },
      {
        id: 43,
        name: '滨州市'
      },
      {
        id: 44,
        name: '菏泽市'
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
      multiple: true,
      selectParent: false,
      flod: false,
      level: 1,
      value: [1, 2],
      operatePosition: 'top',
      title: 'biaoti '
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