<template>
  <div class="foot-btn">
    <button class="read">立即阅读</button>
    <button>加入书架</button>
  </div>
</template>

<script>
  export default {
    name:'uc-toolbar',
    props:{},
    data(){
      return {
        
      }
    },
    components:{},
    mounted(){},
    updated(){},
    methods:{}
  }
</script>

<style scoped>
  .foot-btn{width:100%;height:0.8rem; background:#fff; border-top:1px solid #e8eaec; position:fixed; left:0;bottom:0;}
 button{width:50%;font-size: 0.3125rem;height:0.8rem;border: none;background: #CCCCCC;}
 .read{
	 border-right: 0.0625rem solid #aaa;
 }
</style>
