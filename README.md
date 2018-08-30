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

### showItem
> 设置中间页码显示个数

``` html
<pagination :totalPages="14" :showItem="5" @jump="jumpTo"></pagination>
```

### totalPages
> 设置分页总页数

``` html
<pagination :totalPages="14" :showItem="5" @jump="jumpTo"></pagination>
```

### first
> 首页文本
### prev
> 上一页文本
### next
> 下一页文本
### last
> 最后一页文本

## event

### @jump
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