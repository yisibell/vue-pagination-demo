# vue-pagination
> a pagination component for vue.js

## Useage

``` bash
# npm
npm install vue-pagination --save 

```

``` html

<pagination :totalPages="14" @jump="jumpTo"/>

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





