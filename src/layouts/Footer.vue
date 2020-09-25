<template>
  <div class="foot-btn" >
    <div class="hu">
      <router-link class="home" to="/home" tag="li" active-class="active"><a href="javascript:;" >主页</a></router-link>
      <router-link class="my" to="/user" tag="li" active-class="active"><a href="javascript:;" >用户</a></router-link>
    </div>
  </div>
</template>

<script>
  export default {
    name:'Footer',
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
.foot-btn{width:100%; height:0.8rem; background:#fff; position:fixed; left:0; bottom:0; border-top:1px solid #9e9a95;}
.hu{width: 100%;display: flex;height: 0.8rem;}
.hu li{width: 50%;background: #CCCCCC;display: flex;justify-content: center;align-items: center;font-size: 0.3125rem;}
</style>
