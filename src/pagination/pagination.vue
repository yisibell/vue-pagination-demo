<template>
 
  <ul :class="'pagination-' + pageStyle ">

    <li v-show="current != 1" @click="goto(1)"><a href="javascript:;" :style="silentStyle">{{first}}</a></li>
    <li v-show="current != 1" @click="current-- && goto(current)"><a href="javascript:;" :style="silentStyle">{{prev}}</a></li>
    <li v-for="index in pages" @click="goto(index)" :class="{'active':current == index}" :key="index">
      <a href="javascript:;" :style="current == index ? activeStyle : silentStyle">{{index}}</a>
    </li>
    <li v-show="totalPages != current && totalPages != 0 " @click="current++ && goto(current)"><a href="javascript:;" :style="silentStyle">{{next}}</a></li>
    <li v-show="totalPages != current && totalPages != 0 " @click="goto(totalPages)"><a href="javascript:;" :style="silentStyle">{{last}}</a></li>
      
  </ul>

</template>

<script>
export default {
    name: "pagination",
    data:function(){
      return{
        current: 1,  //当前页码
        silentStyle: {},  //非激活样式
        activeStyle: {}  //激活样式
      }
    },
    props : {
      showItem: {  // 中间页码显示个数
        type: Number,
        default: 5
      },  
      totalPages: {    //总页数（页码总数）
        type: Number,
        required: true
      },
      first: {
        type: String,
        default: "首页"
      },
      last: {
        type: String,
        default: "末页"
      },
      prev: {
        type: String,
        default: "上一页"
      },
      next: {
        type: String,
        default: "下一页"
      },
      pageStyle: {
        type: String,
        default: "default"
      },
      skin: {
        type: String,
        default: "#0E90D2"
      }    
    },
    created(){
      this.silentStyle = { background: "#fff" , color: this.skin };
      this.activeStyle = { background: this.skin , color: "#fff"};
    },
    computed:{
      //中间页码如何显示 计算属性
      pages:function(){
          var pag = [];
          if( this.current < this.showItem ){ //1.当前激活项页码值 小于 中间显示页码数时
        
            var i = Math.min(this.showItem,this.totalPages);  //取较小数，确保中间显示页码数不超过总页数 

            while(i){  // 向pag 数组 头部 依次推入 [1,2,3,4,5] // 假如 this.showItem == 5
                pag.unshift(i--);
            }

          }else{ //2.当前激活项页码值 大于 中间显示页码数时

            var start = this.current - Math.floor( this.showItem / 2 ),   //计算开始页码
                i = this.showItem;

            if( start >  (this.totalPages - this.showItem) ){  // 控制 开始页码 边界问题
                start = (this.totalPages - this.showItem) + 1
            }

            while(i--){  // 从开始页码，向数组添加页码数，添加 i （中间页码个数）个
                pag.push( start++ );
            }

          }

          return pag
      }
    },
    methods:{
      goto:function(index){
        if(index == this.current) return;
          this.current = index;

          // 向父组件传递 当前 页码值 （事件向上传值）
          this.$emit("jump" , this.current );

      }
    }
  
}
</script>


<style lang="scss" scoped>

  ul{
    overflow: hidden;
    font-family:"Segoe UI";
    li{
      list-style:none;
      float: left;
      display: block;
      a{
        text-decoration:none;
        display: block;
        padding:.5rem 1rem;
        border:1px solid #ddd;
        &:hover{
          background:#eee !important;
        }
      }
    }
  }
 
  //default's style pagination
  .pagination-default{
    li{
      margin:0 5px;
      // a{
      //   background:#fff;
      //   color:#0E90D2;
      // }
      // &.active{
      //   a{
      //     background:#0E90D2;
      //     color:#fff;
      //   }
      // }
    }
   
  }
 

  // bootstrap's style pagination
  .pagination-boot{
    li{
      margin-left: -1px;
      &:last-child{
         a:last-child{
          border-top-right-radius: 8px;
          border-bottom-right-radius: 8px;
        }
      }
       &:first-child{
         a:first-child{
          border-top-left-radius: 8px;
          border-bottom-left-radius: 8px;
        }
      }
      // a{
      //   background:#fff;
      //   color:#0E90D2;
      // }
      // &.active{
      //   a{
      //     background:#0E90D2;
      //     color:#fff;
      //   }
      // }

    }
  }


</style>
