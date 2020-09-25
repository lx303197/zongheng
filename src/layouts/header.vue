<template>
  <div class="nav">
	  <div class="top-log">
	  		 <div class="log">
	  			 <img src="/images/bc.png"/>
	  		 </div>
			 <div><u class="down">客户端</u></div>	 
	  </div>
    <ul>
      <router-link to="/home" tag="li" active-class="active"><a href="javascript:;" >首页</a></router-link>
      <router-link to="/follow" tag="li" active-class="active"><a href="javascript:;" >全部</a></router-link>
    </ul>
  </div>
</template>

<script>
  export default {
    name:'Header',
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
	.top-log{display: flex;justify-content: space-between;}
	.down{font-size: 16px;color: #5477B2;}
	.nav{width:100%; position:relative; top:0;left:0; z-index:2; background:#fff;}
	.nav ul{display: flex;justify-content: space-around;}
	.nav ul li{background: #CCCCCC;color: #333333;width: 50%;}
	.nav ul li a{ display:block;width:100%;height:0.6rem; line-height:0.6rem; text-align:center; font-size:0.3rem;}
	.nav ul li.active{height:0.5rem; border-bottom:0.1rem solid #000;background:#333333 ; color:#ccc;}
</style>
