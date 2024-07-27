# [Picker-Model 双向绑定选择器](http://mid.chinatowercom.cn:18080/appGuide/ui/pickerModel.html#picker-model-双向绑定选择器)

该组件用于单列选择场景下双向数据绑定。基本使用和`picker`组件一样,请参考`picker`组件使用，该文档主要说明双向绑定的使用

### [基本使用 value 为数字](http://mid.chinatowercom.cn:18080/appGuide/ui/pickerModel.html#基本使用-value-为数字)

- 通过`value`实现双向数据绑定，使用时请配合`.sync`修饰符使用，`value`为数字，并且`options`数组中的数据也是数字或者字符串时，`value`代表的是数组的索引

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基础使用 value为数字">
      <ct-ui-picker-model
        title="选择数字"
        operatePosition="top"
        :options="options2"
        :value.sync="defaultValue2"
        label-key="text"
        value-key="id"
        confirmButtonWidth="65"
        cancelButtonWidth="35"
        @change="change"
        @confirm="confirm"
        closeIconPos="top-left"
        cancelTextSize="30rpx"
        confirmTextSize="30rpx"
        :closeable="false"
      >
        <view class="border">{{ defaultValue2 }} </view>
        <view class="border1">value: {{ defaultValue2 }} </view>
      </ct-ui-picker-model>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      defaultValue2: 3,
      options2: [1, 2, 3, 4, 5]
    }
  },
  methods: {
    change(value) {
      console.log('change value::', value.value)
    },
    confirm(value) {
      console.log('confirm value::', value.value)
    },
    changeValue() {
      this.defaultValue = 1001
    }
  }
}
</script>

<style lang="scss">
.border {
  border: 1px solid #ccc;
  width: 600rpx;
  height: 60rpx;
  text-align: center;
  line-height: 60rpx;
  margin-top: 10rpx;
}
.border1 {
  width: 600rpx;
  height: 60rpx;
  line-height: 60rpx;
  margin-top: 10rpx;
}
</style>
```

### [基本使用 value 为字符串](http://mid.chinatowercom.cn:18080/appGuide/ui/pickerModel.html#基本使用-value-为字符串)

- 通过`value`实现双向数据绑定，使用时请配合`.sync`修饰符使用，`value`为字符串，并且`options`数组中的数据为字符串时，`value`就是选中项的字符串
- 通过`value`实现双向数据绑定，使用时请配合`.sync`修饰符使用，`value`为字符串，并且`options`数组中的数据为对象，`value`就是选中项的[valueKey]

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基础使用 value为字符串">
      <ct-ui-picker-model
        title="选择区"
        :options="options"
        :value.sync="defaultValue1"
        label-key="text"
        value-key="id"
        confirmButtonWidth="65"
        cancelButtonWidth="35"
        @change="change"
        @confirm="confirm"
        closeable
      >
        <view class="border">{{ defaultValue1 }} </view>
        <view class="border1">value: {{ defaultValue1 }} </view>
      </ct-ui-picker-model>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      defaultValue1: '1002',
      options: [
        {
          id: 1001,
          text: '北京/1'
        },
        {
          id: '1002',
          text: '广东/2'
        },
        {
          id: '1003',
          text: '四川/3'
        },
        {
          id: 1004,
          text: '江西/4'
        },
        {
          id: 1005,
          text: '武汉/5'
        }
      ]
    }
  },
  methods: {
    change(value) {
      console.log('change value::', value.value)
    },
    confirm(value) {
      console.log('confirm value::', value.value)
    },
    changeValue() {
      this.defaultValue = 1001
    }
  }
}
</script>

<style lang="scss">
.border {
  border: 1px solid #ccc;
  width: 600rpx;
  height: 60rpx;
  text-align: center;
  line-height: 60rpx;
  margin-top: 10rpx;
}
.border1 {
  width: 600rpx;
  height: 60rpx;
  line-height: 60rpx;
  margin-top: 10rpx;
}
</style>
```

### [基本使用 value 为对象时](http://mid.chinatowercom.cn:18080/appGuide/ui/pickerModel.html#基本使用-value-为对象时)

- 通过`value`实现双向数据绑定，使用时请配合`.sync`修饰符使用，`value`为对象，并且`options`数组中的数据为对象，`value`就是选中项的对象值

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基础使用 value为对象">
      <ct-ui-picker-model
        ref="ref1"
        title="选择区2"
        :options="options"
        :value.sync="defaultValue"
        label-key="text"
        value-key="id"
        @change="change"
        @confirm="confirm"
        closeable
      >
        <view class="border">{{ defaultValue.text }} </view>
        <view class="border1">value: {{ defaultValue }} </view>
      </ct-ui-picker-model>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  data() {
    return {
      defaultValue: {
        id: 1003,
        text: '四川/3'
      },
      options: [
        {
          id: 1001,
          text: '北京/1'
        },
        {
          id: '1002',
          text: '广东/2'
        },
        {
          id: '1003',
          text: '四川/3'
        },
        {
          id: 1004,
          text: '江西/4'
        },
        {
          id: 1005,
          text: '武汉/5'
        }
      ]
    }
  },
  methods: {
    change(value) {
      console.log('change value::', value.value)
    },
    confirm(value) {
      console.log('confirm value::', value.value)
    },
    changeValue() {
      this.defaultValue = 1001
    }
  }
}
</script>

<style lang="scss">
.border {
  border: 1px solid #ccc;
  width: 600rpx;
  height: 60rpx;
  text-align: center;
  line-height: 60rpx;
  margin-top: 10rpx;
}
.border1 {
  width: 600rpx;
  height: 60rpx;
  line-height: 60rpx;
  margin-top: 10rpx;
}
</style>
```