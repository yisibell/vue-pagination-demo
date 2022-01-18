# vue-pagination-demo

## Usage

``` html
<ai-pagination :totalPages="total" @jump="jumpTo"></ai-pagination>
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

| **属性** | **类型** | **可选值** | **是否必需** |
| :-----: | :-----: | :-----: | :-----: |
|showItem|Number|5 (默认)| 否 |
|totalPages|Number| 无 (默认) | 是 |
|first|String|首页 (默认)|否|
|prev|String|上一页 (默认)|否|
|next|String|下一页 (默认)|否|
|last|String|末页 (默认)|否|
|pageStyle|String|default (默认) </br> boot (bootstrap风格)|否|
|skin|String(任意css颜色值)|#0E90D2 (默认)|否|

## Events

**@jump**

点击分页时触发句柄

``` html
<ai-pagination :totalPages="total" :showItem="5" @jump="jumpTo"></ai-pagination>
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

## Logs

> 2018/9/2 

1. 新增 `pageStyle` 属性， 可选为 `boot` 即bootstrap风格分页条
2. 新增 `skin` 属性，可自行设置分页条的颜色。默认为 `#0E90D2`
