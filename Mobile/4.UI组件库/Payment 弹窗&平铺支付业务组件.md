# [Payment 弹窗&平铺支付业务组件](http://mid.chinatowercom.cn:18080/appGuide/ui/payment.html#payment-弹窗-平铺支付业务组件)

该组件用于支付方式的选择，快速生成一个可选择列表。

> - WeChat 微信支付
> - Alipay 支付宝支付
> - Tiktok 抖音支付
> - JD 京东支付
> - UnionPay 银联支付
> - Apple Apple Pay

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/payment.html#基本使用)

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="基础使用">
      <ct-ui-button
        btnSize="small"
        type="primary"
        style="width: 80px"
        @click="click"
      >
        显示弹窗
      </ct-ui-button>
    </ct-demo-card>
    <ct-ui-payment
      ref="payment"
      @change="change"
      @submit="submit"
    ></ct-ui-payment>
  </view>
</template>

<script>
export default {
  name: 'Payment',
  data() {
    return {}
  },
  methods: {
    // 按钮点击显示弹窗
    click() {
      this.$refs.payment.show()
    },
    // 点击列表是的回调
    change(id) {
      console.log(id)
    },
    // 弹窗模式下，点击确定按钮
    submit(id) {
      console.log(id)
    }
  }
}
</script>

<style lang="scss" scoped></style>
```

### [平铺模式显示](http://mid.chinatowercom.cn:18080/appGuide/ui/payment.html#平铺模式显示)

- 通过`mode`参数设置展示方式
- 通过`title`参数自定义标题名称

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="列表模式显示">
      <ct-ui-payment mode="tile" title="" @change="change"></ct-ui-payment>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Payment',
  data() {
    return {}
  },
  methods: {
    // 点击列表是的回调
    change(id) {
      console.log(id)
    }
  }
}
</script>

<style lang="scss" scoped></style>
```

### [自定义列表显示项，默认选中项](http://mid.chinatowercom.cn:18080/appGuide/ui/payment.html#自定义列表显示项-默认选中项)

- 通过`options`参数设置显示的列表项
- 通过`customList`参数添加自定义的列表项
- 通过`defaultSelect`参数设置默认选中项
- 通过`listNumber`参数设置不滑动的情况下可显示列表数量，如果保证展示效果，该数据不能大于列表项的数组长度

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义列表数据">
      <ct-ui-payment
        mode="tile"
        title=""
        :options="['WeChat', 'Alipay', 'test']"
        :customList="customList"
        defaultSelect="test"
        :listNumber="3"
        @change="change"
      ></ct-ui-payment>
    </ct-demo-card>
  </view>
</template>

<script>
export default {
  name: 'Payment',
  data() {
    return {
      customList: [
        {
          id: 'test',
          image:
            'https://img2.baidu.com/it/u=1214999427,158703044&fm=253&app=120&size=w931&n=0&f=PNG&fmt=auto?sec=1713978000&t=5d2d0924dfe168a2420efeb78e05a510',
          label: '铁塔支付'
        }
      ]
    }
  },
  methods: {
    // 点击列表是的回调
    change(id) {
      console.log(id)
    }
  }
}
</script>

<style lang="scss" scoped></style>
```

### [自定义样式](http://mid.chinatowercom.cn:18080/appGuide/ui/payment.html#自定义样式)

- 通过`titleSize`设置标题文字大小
- 通过`titleBold`设置标题是否加粗
- 通过`titleColor`设置标题文字颜色
- 通过`listTestColor`设置列表内容文字颜色
- 通过`listTestSize`设置列表内容文字大小
- 通过`listBackground`设置列表背景色
- 通过`listHeight`设置列表高度
- 通过`showLine`设置是否显示分割线
- 通过`lineColor`设置分割线颜色
- 通过`lineLayer`设置分割线粗细
- 通过`confirmType`设置确定按钮类型（弹窗模式时生效）
- 通过`overLayOpacity`设置遮罩层透明度 （弹窗模式时生效）

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="自定义样式">
      <ct-ui-button
        btnSize="small"
        type="primary"
        style="width: 80px"
        @click="click1"
      >
        显示弹窗
      </ct-ui-button>
    </ct-demo-card>
    <ct-ui-payment
      ref="payment1"
      titleSize="36rpx"
      :titleBold="true"
      titleColor="#3164f6"
      listTestColor="#ccc"
      listTestSize="24rpx"
      listBackground="#fff"
      listHeight="120"
      :showLine="true"
      lineColor="red"
      :lineLayer="4"
      overLayOpacity="0.2"
      @change="change"
      @submit="submit"
    ></ct-ui-payment>
  </view>
</template>

<script>
export default {
  name: 'Payment',
  data() {
    return {}
  },
  methods: {
    // 按钮点击显示弹窗
    click1() {
      this.$refs.payment1.show()
    },
    // 点击列表是的回调
    change(id) {
      console.log(id)
    },
    // 弹窗模式下，点击确定按钮
    submit(id) {
      console.log(id)
    }
  }
}
</script>

<style lang="scss" scoped></style>
```

### [修改选中样式，不显示单选框](http://mid.chinatowercom.cn:18080/appGuide/ui/payment.html#修改选中样式-不显示单选框)

- 通过`showRadio`隐藏单选框
- 通过`selectListBackground`设置选中项背景颜色
- 通过`selectTextColor`设置选中项文字颜色

```vue
<template>
  <view class="demo-page">
    <ct-demo-card title="不显示单选框">
      <ct-ui-button
        btnSize="small"
        type="primary"
        style="width: 80px"
        @click="click2"
      >
        显示弹窗
      </ct-ui-button>
    </ct-demo-card>
    <ct-ui-payment
      ref="payment2"
      :showRadio="false"
      selectListBackground="#3164f6"
      selectTextColor="#fff"
      @change="change"
      @submit="submit"
    ></ct-ui-payment>
  </view>
</template>

<script>
export default {
  name: 'Payment',
  data() {
    return {}
  },
  methods: {
    // 按钮点击显示弹窗
    click2() {
      this.$refs.payment2.show()
    },
    // 点击列表是的回调
    change(id) {
      console.log(id)
    },
    // 弹窗模式下，点击确定按钮
    submit(id) {
      console.log(id)
    }
  }
}
</script>

<style lang="scss" scoped></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/payment.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/payment.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| mode                 | 展示方式(平铺  弹窗)                                         | String           | popup                                                     | popup \| tile                      |
| -------------------- | ------------------------------------------------------------ | ---------------- | --------------------------------------------------------- | ---------------------------------- |
| options              | 可使用的支付方式                                             | Array            | ['WeChat', 'Alipay', 'Tiktok', 'JD', 'UnionPay', 'Apple'] | 默认值中任意子项或者自定义数据的id |
| customList           | 自定义添加的列表内容(数据格式为[{id: '', image: '', label: ''}]) | Array            | []                                                        |                                    |
| defaultSelect        | 默认选中项的id                                               | String           |                                                           |                                    |
| title                | 标题                                                         | String           | 支付方式                                                  |                                    |
| titleSize            | 标题文字大小                                                 | [String, Number] | 36rpx                                                     |                                    |
| titleBold            | 标题是否加粗                                                 | Boolean          | false                                                     |                                    |
| titleColor           | 标题文字颜色                                                 | String           | #262f40                                                   |                                    |
| money                | 金额                                                         | String \| Number | 支付方式                                                  |                                    |
| moneySize            | 标题文字大小                                                 | [String, Number] | 36rpx                                                     |                                    |
| moneyBold            | 标题是否加粗                                                 | Boolean          | false                                                     |                                    |
| moneyColor           | 标题文字颜色                                                 | String           | #262f40                                                   |                                    |
| listTestColor        | 列表内容文字颜色                                             | String           | #262f40                                                   |                                    |
| listTestSize         | 列表内容文字大小                                             | [String, Number] | 28rpx                                                     |                                    |
| listBackground       | 列表内容文字大小                                             | String           | #fff                                                      |                                    |
| listHeight           | 列表高度                                                     | String           | 128                                                       |                                    |
| listNumber           | 不滑动时可显示的列表数量                                     | String \| Number | 6                                                         |                                    |
| showLine             | 是否显示分割线                                               | Boolean          | true                                                      |                                    |
| lineColor            | 分割线颜色                                                   | String           | #E4E8F0                                                   |                                    |
| lineLayer            | 分割线粗细                                                   | Number           | 2                                                         |                                    |
| confirmText          | 确定按钮文字                                                 | String           | 确定                                                      |                                    |
| confirmSize          | 确定按钮文字大小                                             | [String, Number] | 28rpx                                                     |                                    |
| confirmType          | 确定按钮类型（弹窗模式时生效并且按钮在底部）                 | String           | default                                                   |                                    |
| confirmColor         | 确定按钮颜色（弹窗模式时生效并且按钮在顶部）                 | String           | #3164f6                                                   |                                    |
| showCancel           | 是否显示取消按钮                                             | Boolean          | true                                                      |                                    |
| cancelText           | 取消按钮文字                                                 | String           | 取消                                                      |                                    |
| cancelSize           | 取消按钮文字大小                                             | [String, Number] | 28rpx                                                     |                                    |
| cancelType           | 取消按钮类型（弹窗模式时生效并且按钮在底部）                 | String           | default                                                   |                                    |
| cancelColor          | 取消按钮颜色（弹窗模式时生效并且按钮在顶部）                 | String           | #3164f6                                                   |                                    |
| operatePosition      | 按钮位置                                                     | String           | bottom                                                    | top \| bottom                      |
| overLayOpacity       | 遮罩层透明度 （弹窗模式时生效）                              | String           | 0.7                                                       |                                    |
| overlayClose         | 点击遮罩层时候关闭弹窗 （弹窗模式时生效）                    | Boolean          | true                                                      |                                    |
| showRadio            | 是否显示单选按钮                                             | Boolean          | true                                                      |                                    |
| selectListBackground | 选中项背景颜色（单选按钮不显示时生效）                       | String           |                                                           |                                    |
| selectTestBackground | 选中项文字颜色（单选按钮不显示时生效）                       | String           |                                                           |                                    |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/payment.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| change             | 点击列表数据时触发           | id   |
| ------------------ | ---------------------------- | ---- |
| submit             | 弹窗模式下，点击确定按钮触发 | id   |
| $refs.payment.show | 弹窗模式下，显示弹窗         |      |