# [Form 表单](http://mid.chinatowercom.cn:18080/appGuide/ui/form.html#form-表单)

该组件主要提供表单功能

### [基本使用](http://mid.chinatowercom.cn:18080/appGuide/ui/form.html#基本使用)

- 通过`labelPosition`属性设置 label 的位置
- 通过`starPosition`属性设置必填星号在前还是在后
- 通过`labelAlign`属性设置 label 字体的对齐方式
- 通过`labelSplit`属性设置 label 后面的冒号，默认为：
- 通过`errorType`属性设置提示方式，message-提示信息，toast-进行 toast 提示，none-无提示, border-bottom-下边框呈现红色
- 通过`model`属性设置当前 form 的需要验证字段的集合
- 通过`rules`属性设置验证规则
- 通过`labelStyle`属性设置 label 的样式，对象形式
- 通过`errorColor`属性设置错误提示的颜色
- 通过`borderBottom`属性设置是否显示表单域的下划线边框
- 通过`borderColor`属性设置表单下划线边框颜色
- 通过`starColor`属性设置星号的颜色
- 通过`labelWidth`属性设置 label 的宽度，单位 rpx
- 通过`contentAlign`属性设置内容的位置

```vue
<template>
  <view class="demo">
    <ct-demo-card title="基础信息">
      <ct-ui-form
        labelPosition="left"
        starPosition="after"
        labelAlign="left"
        errorType="message"
        :model="model"
        :rules="rules"
        ref="form"
        :labelStyle="labelStyle"
        contentAlign="right"
      >
        <ct-ui-form-item
          label="活动名称"
          labelSplit="："
          borderBottom
          required
          prop="user.name"
          ref="item1"
          contentAlign="right"
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
    </ct-demo-card>
    <ct-demo-card title="成本信息">
      <ct-ui-form
        labelPosition="left"
        starPosition="after"
        labelAlign="left"
        labelSplit="："
        errorType="message"
        :model="cost"
        ref="forms"
        :labelStyle="labelStyle"
        contentAlign="right"
      >
        <ct-ui-form-item
          label="预计成本(元)"
          labelSplit=""
          borderBottom
          required
        >
          <ct-ui-input
            type="price"
            :customStyle="customStyle"
            inputAlign="right"
            v-model="cost.costPrice"
            border="none"
          ></ct-ui-input>
        </ct-ui-form-item>
        <ct-ui-form-item label="预计收入" labelSplit="" borderBottom>
          <ct-ui-input
            type="price"
            :customStyle="customStyle"
            inputAlign="right"
            v-model="cost.incomePrice"
            border="none"
          ></ct-ui-input>
        </ct-ui-form-item>
        <ct-ui-form-item label="实际成本" labelSplit="" borderBottom>
          <ct-ui-input
            type="price"
            :customStyle="customStyle"
            inputAlign="right"
            v-model="cost.actualCost"
            border="none"
          ></ct-ui-input>
        </ct-ui-form-item>
      </ct-ui-form>
    </ct-demo-card>
  </view>
</template>
<script>
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
      cost: {
        costPrice: 1100000,
        incomePrice: 1100000,
        actualCost: 1100000
      },
      rules: {
        'user.name': {
          type: 'string',
          required: true,
          message: '请填写活动名称',
          trigger: ['blur', 'change']
        },
        'user.number': {
          type: 'string',
          required: true,
          message: '请填写活动编号',
          trigger: ['blur', 'change']
        },
        'user.organization': {
          type: 'string',
          required: true,
          message: '请填写所属组织',
          trigger: ['blur', 'change']
        },
        'user.head': {
          type: 'string',
          required: true,
          message: '请填写负责人',
          trigger: ['blur', 'change']
        }
      },
      labelStyle: {
        color: '#000',
        fontSize: '16px'
      },
      customStyle: {
        color: '#a8a8a8'
      }
    }
  }
}
</script>
<style lang="scss"></style>
```

### [事件监听](http://mid.chinatowercom.cn:18080/appGuide/ui/form.html#事件监听)

- `validate` 校验全部数据
- `setRules` 手动设置校验的规则
- `resetFields` 重置表单

```vue
<template>
  <view class="demo">
    <ct-demo-card title="基础信息">
      <ct-ui-form
        labelPosition="left"
        starPosition="after"
        labelAlign="left"
        errorType="message"
        :model="model"
        :rules="rules"
        ref="form"
        :labelStyle="labelStyle"
        contentAlign="right"
      >
        <ct-ui-form-item
          label="活动名称"
          labelSplit="："
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
    </ct-demo-card>
    <ct-demo-card title="成本信息">
      <ct-ui-form
        labelPosition="left"
        starPosition="after"
        labelAlign="left"
        labelSplit="："
        errorType="message"
        :model="cost"
        ref="forms"
        :labelStyle="labelStyle"
        contentAlign="right"
      >
        <ct-ui-form-item
          label="预计成本(元)"
          labelSplit=""
          borderBottom
          required
        >
          <ct-ui-input
            type="price"
            :customStyle="customStyle"
            inputAlign="right"
            v-model="cost.costPrice"
            border="none"
          ></ct-ui-input>
        </ct-ui-form-item>
        <ct-ui-form-item label="预计收入" labelSplit="" borderBottom>
          <ct-ui-input
            type="price"
            :customStyle="customStyle"
            inputAlign="right"
            v-model="cost.incomePrice"
            border="none"
          ></ct-ui-input>
        </ct-ui-form-item>
        <ct-ui-form-item label="实际成本" labelSplit="" borderBottom>
          <ct-ui-input
            type="price"
            :customStyle="customStyle"
            inputAlign="right"
            v-model="cost.actualCost"
            border="none"
          ></ct-ui-input>
        </ct-ui-form-item>
      </ct-ui-form>
    </ct-demo-card>
  </view>
</template>
<script>
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
      cost: {
        costPrice: 1100000,
        incomePrice: 1100000,
        actualCost: 1100000
      },
      rules: {
        'user.name': {
          type: 'string',
          required: true,
          message: '请填写活动名称',
          trigger: ['blur', 'change']
        },
        'user.number': {
          type: 'string',
          required: true,
          message: '请填写活动编号',
          trigger: ['blur', 'change']
        },
        'user.organization': {
          type: 'string',
          required: true,
          message: '请填写所属组织',
          trigger: ['blur', 'change']
        },
        'user.head': {
          type: 'string',
          required: true,
          message: '请填写负责人',
          trigger: ['blur', 'change']
        }
      },
      labelStyle: {
        color: '#000',
        fontSize: '16px'
      },
      customStyle: {
        color: '#a8a8a8'
      }
    }
  },
  watch: {
    model: {
      deep: true,
      immediate: true,
      handler() {
        this.$nextTick(() => {
          this.$refs.form.validate()
        })
      }
    }
  },
  onReady() {
    this.$refs.form.setRules(this.rules)
  },
  methods: {
    resetFields() {
      this.$refs.form.resetFields()
    }
  }
}
</script>
<style lang="scss"></style>
```

### [API](http://mid.chinatowercom.cn:18080/appGuide/ui/form.html#api)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/form.html#props)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| model         | 当前form的需要验证字段的集合 | Object                      | {}      | -                                         |
| ------------- | ---------------------------- | --------------------------- | ------- | ----------------------------------------- |
| rules         | 验证规则                     | Object \| Function \| Array | {}      | -                                         |
| errorType     | 有错误时的提示方式           | String                      | message | message \| toast \| none \| border-bottom |
| errorColor    | 错误提示的颜色               | String                      | #eb4b4b | -                                         |
| borderBottom  | 是否显示表单域的下划线边框   | Boolean                     | true    | true \| false                             |
| borderColor   | 表单下划线边框颜色           | String                      | #8590A6 | -                                         |
| labelPosition | label的位置                  | String                      | left    | left \| top                               |
| labelWidth    | label的宽度，单位rpx         | String \| Number            | 200     | -                                         |
| labelAlign    | label字体的对齐方式          | String                      | left    | -                                         |
| labelStyle    | label 的样式，对象形式       | Object                      | {}      | -                                         |
| labelSplit    | label 后面的冒号，默认为：   | String                      | ：      | -                                         |
| starColor     | 星号的颜色                   | String                      | #eb4b4b | -                                         |
| starPosition  | 必填星号在前还是在后         | String                      | before  | before \| after                           |
| contentAlign  | 内容位置                     | String                      | left    | left \| center \| right                   |

#### [Events](http://mid.chinatowercom.cn:18080/appGuide/ui/form.html#events)

| 事件名 | 说明 | 返回值 |
| ------ | ---- | ------ |
|        |      |        |

| validate    | 校验全部数据       | -    |
| ----------- | ------------------ | ---- |
| setRules    | 手动设置校验的规则 | -    |
| resetFields | 重置表单           | -    |

#### [Slots](http://mid.chinatowercom.cn:18080/appGuide/ui/form.html#slots)

| name | 说明 | 作用域 |
| ---- | ---- | ------ |
|      |      |        |

|      | 表单内容 | -    |
| ---- | -------- | ---- |
|      |          |      |

### [Props-item](http://mid.chinatowercom.cn:18080/appGuide/ui/form.html#props-item)

#### [Props](http://mid.chinatowercom.cn:18080/appGuide/ui/form.html#props-1)

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| ---- | ---- | ---- | ------ | ------ |
|      |      |      |        |        |

| label          | input的label提示语                                           | String            |       | -                       |
| -------------- | ------------------------------------------------------------ | ----------------- | ----- | ----------------------- |
| prop           | 绑定的值                                                     | String            |       | -                       |
| borderBottom   | 是否显示表单域的下划线边框                                   | String \| Boolean |       | -                       |
| borderColor    | 表单下划线边框样式                                           | String            |       | -                       |
| labelPosition  | label的位置                                                  | String            |       | left \| top             |
| labelWidth     | label的宽度                                                  | String \| Number  |       | -                       |
| labelSplit     | label 后面的冒号                                             | String \| null    | null  | -                       |
| leftIcon       | 左侧icon                                                     | String            |       | -                       |
| leftIconStyle  | 左侧icon的样式                                               | String \| Object  |       | -                       |
| rightIcon      | 右侧图标                                                     | String            |       | -                       |
| rightIconStyle | 右侧icon的样式                                               | String \| Object  |       | -                       |
| required       | 是否显示左边的必填星号，只作显示用，具体校验必填的逻辑，请在rules中配置 | Boolean           | false | false \| true           |
| starColor      | 星号的颜色                                                   | String            |       | -                       |
| starPosition   | 必填星号在前还是在后                                         | String            |       | -                       |
| customStyle    | 自定义颜色                                                   | Object            | {}    | -                       |
| contentAlign   | 内容位置                                                     | String            |       | left \| center \| right |