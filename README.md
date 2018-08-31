# vue-paginators
> a pagination component for vue.js

## Usage
``` bash
# using npm
npm install vue-paginators --save 
```
``` js
// In main.js
import vuePaginators from "vue-paginators"
Vue.use(vuePaginators)
```

``` html
<pagination :totalPages="total" @jump="jumpTo"></pagination>
```

``` js
export default {
  data(){
    return {
      total: 14  // get this from ajax data
    }
  },
  methods: {
    jumpTo(curr){
      // do something when you click the pagination bar ...
    }
  }
}

```

## Properties

| **属性** | **类型** | **默认值** | **是否必需** |
| :-----: | :-----: | :-----: | :-----: |
|showItem|Number|5| 否 |
|totalPages|Number| 无 | 是 |
|first|String|首页|否|
|prev|String|上一页|否|
|next|String|下一页|否|
|last|String|末页|否|

## Events
**@jump**
> 点击分页时触发句柄

``` html
<pagination :totalPages="total" :showItem="5" @jump="jumpTo"></pagination>
```

``` js
export default {
  data(){
    return {
      total: 14
    }
  },
  methods : {
    jumpTo(curr){
      // do something when you click the pagination bar ...
    }
  }
}
```