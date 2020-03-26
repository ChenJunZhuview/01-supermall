<template>
  <div class="tab-bar-item" @click="itemClick">
    <div v-if="!isActive "> <slot name="item-icon"></slot></div>
    <div v-else> <slot name="item-icon-active"></slot></div>

    <div :style="activeStyle"><slot name="item-text"></slot></div>


    <!--插槽方法:动态增加或者减少-->
    <!--普通写法:写死,四个都一样-->
    <!--<img src="../../assets/img/tabbar/home.svg" alt="">-->
    <!--<div>首页</div>-->
  </div>
</template>

<script>
export default {
    name: "TabBarItem",
    props:{
      path:String,
      activeColor:{
        type:String,
        default:'pink'
      }
    },
    data(){
      return {
        // isActive:true
      //  写死,true都是活跃,  false都不活跃  ,要动态监听是否处于活跃状态
      }
    },
    computed:{
      isActive(){
        //当前活跃的path->/home 是否等于item1(/home) =true
        //当前活跃的path->/home 是否等于item1(/category) =false
        //当前活跃的path->/home 是否等于item1(/cart) = false
        //当前活跃的path->/home 是否等于item1(/profile) = false
        return this.$route.path.indexOf(this.path) !== -1
      },
      activeStyle(){
        return this.isActive ? {color: this.activeColor} : {}
      }
    },
    methods:{
      itemClick(){
        this.$router.replace(this.path)
        // console.log('aaaa')
      }
    }

  }
</script>

<style scoped>
  .tab-bar-item{
    flex: 1;
    text-align: center;
    height: 49px;
    font-size: 14px;
  }
  .tab-bar-item img{
    width: 24px;
    height: 24px;
    margin-top: 3px;
    vertical-align: middle;
    margin-bottom: 2px;
  }
  /*.active{*/
    /*!*活跃状态的颜色写死,希望可以动态修改活跃状态的文字颜色*!*/
    /*color:hotpink;*/
  /*}*/
</style>

