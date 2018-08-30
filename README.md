# vue-paginators
> a pagination component for vue.js

## Useage

``` bash
# npm
npm install vue-paginators --save 

```
``` js
// main.js
import vuePaginators from "vue-paginators"
Vue.use(vuePaginators)

```

``` html
<pagination :totalPages="14" @jump="jumpTo"></pagination>
```

``` js
export default {
  data(){
    return {}
  },
  methods: {
    jumpTo(curr){
      // do somethig when jump to foo pages...
    }
  }
}

```

## Properties

| **属性** | **类型** | **默认值** | **是否必需** |
| :----- | :-----: | :-----: | ----- |
|showItem|Number|5| 否 |
|totalPages|Number| 无 | 是 |
|first|String|首页|否|
|prev|String|上一页|否|
|next|String|下一页|否|
|last|String|末页|否|

## event
**@jump**
> 点击分页时触发句柄

``` html
<pagination :totalPages="14" :showItem="5" @jump="jumpTo"></pagination>
```

``` js
export default {
  data(){
    return {}
  },
  methods : {
    jumpTo(curr){
      // do something when click the pagination bar ...
    }
  }
}
```