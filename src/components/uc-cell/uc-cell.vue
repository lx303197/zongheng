<template>
  <div class="uc-cell">
    <div @click="toDetail" class="box">
      <h2><img v-show="index != null" :src="data.img"/></h2>
	  <div class="right">
		  <span>{{data.title}}</span>
		  <p>{{data.des}}</p>
		  <a>作者:{{data.detail.auth}}</a>
	  </div>
	  
      <a class="cell__anchor" v-if="isAdd" href="javascript:;" @click.stop="$emit('add-item',$event)">+</a>
    </div>
  </div>
</template>

<script>
  export default {
    name:'uc-cell',
    props:{
      data:{//{_id:xx,title:xx,des:xx}
        type:Object,
        required:true
      },
      collectionName:{
        type:String,
        default:null
      },
      index:{
        type:Number,
        default:null
      },
	  img:{
		type:String,
		 default:null
	  },
      isAdd:{
        type:Boolean,
        default:false
      }
    },
    components:{},
    mounted(){},
    updated(){},
    methods:{
      toDetail(){
        if(this.collectionName){
          this.$router.push(`/detail/${this.data._id}?collectionName=${this.collectionName}`)
        }
      }
    }
  }
</script>

<style>
  .uc-cell{position: relative;}
  
  .uc-cell:active {background: #ccc;}
  .uc-cell div { color:#494d4d; padding:0.3rem 0; border-bottom:1px dashed #ccc;display: flex;}
  .uc-cell div h2{max-height:1.8rem;}
  .uc-cell .right{height: 1.5rem; display: flex;flex-direction: column;justify-content: space-between;margin-left: 0.125rem;border-bottom: none;}
  span{font-size: 0.3125rem;}
  .uc-cell div p{max-height:1.8rem;}
  .cell__anchor{position:absolute;right:0.3rem;top:0.4rem;}
</style>
