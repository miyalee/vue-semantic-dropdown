# vue-semantic-dropdown

> 更支持vue的semantic风格下拉菜单

主要为了解决semantic的dropdown无法直接进行数据绑定，为正常使用也扩展了其他功能，保证使用过程的灵活顺滑～

## 安装

``` bash
npm install vue-semantic-dropdown --save
```

## 使用

#### 引入组件
``` javascript
// in your main.js
import Dropdown from 'vue-semantic-dropdown'

Vue.use(Dropdown)
```

#### 在.vue中使用
``` javascript
<Dropdown addClass="selection" name="selection" defaultText="请选择"
          v-model="selectedValue" :options="options"
          textFiled="value" valueFiled="id"
          @dropdown-selected="(text) => { selectedText = text}"
></Dropdown>
<span>id: {{ selectedValue }} name：{{ selectedText }} </span>
...
data() {
    return {
        options: [
            {
                id: 'litteRed',
                value: '小红'
            },
            {
                id: 'litteBlue',
                value: '小蓝'
            }
        ],
        selectedValue: null,
        selectedText: null
   }
}

```

## 参数说明

#### Attributes

| 参数  | 说明 | 类型    | 默认值  | 必填
|--------------|----------------------------------|--------|------|----------|
| options      | 下拉内容，数组内部可以是string或json | Array  | null | required |
| name         | input的name                      | String | null | required |
| value        | 选中值                            | -      | null | required |
| defaultText  | 默认显示内容                       | String | null | required |
| textFiled    | 显示值的字段名，可修改，如'value'    | String | text |          |
| valueFiled   | 选中值的字段名，可修改，如'id'       | String | value |         |
| addClass     | 需要增加的class，默认class只有'ui dropdown' | String | null |  |
| action       | 同semantic中的action              | String | activate |          |
| setting      | dropdown(setting)                | Object | -   | required |

默认初始化下拉菜单时dropdown()中带action和onchange两个参数属性

#### Events

| 参数               | 说明                                   |  类型   | 默认值 | 必填
|-------------------|----------------------------------------|--------|------|--|
| dropdown-selected | 当同时存在value和text时可以获取到选中的text | String | null | - |

## 查看example
``` bash
cd 此目录
npm i
npm run dev
```

For more information，checkout the [github](https://github.com/miyalee/vue-semantic-dropdown)
