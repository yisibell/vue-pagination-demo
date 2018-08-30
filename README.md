# vuePagination
> a pagination component for vue.js

## Useage

``` bash
# npm
npm install vue-pagination --save 

```
``` js
// main.js
import vuePagination from "vuePagination"
Vue.use(vuePagination)

```


``` html

<pagination :totalPages="14" @jump="jumpTo"> </pagination>

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





