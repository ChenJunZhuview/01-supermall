<template>
  <div id="tab-bar">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    name: "TabBar"
  }
</script>

<style scoped>
  #tab-bar{
    display: flex;
    background-color: #DADADA;
    /*定位*/
    position: fixed;
    left: 0;
    right: 0;
    bottom: 0;
    /*阴影
    box-shadow: h-shadow v-shadow  blur     spread	 color     inset
           水平偏移 垂直偏移  模糊距离  阴影尺寸  阴影颜色   将外阴影转换为内阴影*/
    box-shadow: 0 -2px 2px 2px skyblue ;
  }
</style>
