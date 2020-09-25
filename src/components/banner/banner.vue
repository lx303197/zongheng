<template>
  <div class="banner">
    <ul class="clearfix">
      <router-link
        tag="li"
        v-for="(item, index) of data" 
        :key="item._id"
        :to="{name:'detail',params:{_id:item._id},query:{collectionName}}"
      >
        <img :src="item.banner" alt="" />
      </router-link>
    </ul>
  </div>
</template>

<script>
  
import Swipe from './js/swipe.js';
// import $ from 'jquery';
import './js/jquery-1.7.2.js'; // src ~~~  window.$ | jQuery

export default {
  name: 'banner',
  props: {
    data: {
      //[{_id:xx,image:xx,title:xx,sub_title:xx}]
      type: Array,
      required: true
    },
    collectionName: {
      type: String,
      required: true
    }
  },
  components: {},
  mounted() {
    this.data.length !== 0 && this.initSwiper()
  },
  updated() {
    this.initSwiper()
  },
  methods: {
    initSwiper(){
      new Swipe($('.banner')[0], {
        auto: 2000,
        continuous: true,
        stopPropation: true,
        callback: function(index, element) {
          $('.banner ol li').removeClass('active');
          $('.banner ol li')
            .eq(index)
            .addClass('active');
        }
      });
    }
  }
};
</script>

<style scoped>
 .banner{overflow: hidden;}
.banner ul li {
  position: relative;
  overflow: hidden;
  z-index: 1;
  width: 6.4rem;
  float: left;
}
.banner ul li img {
  width: 100%;
  display: block;
}

.banner ol {
  position: absolute;
  right: 0.2rem;
  bottom: 0.2rem;
}
.banner ol li {
  width: 0.15rem;
  height: 0.15rem;
  background: #5477b2;
  float: left;
  border-radius: 50%;
  margin-right: 0.08rem;
}
.banner ol li.active {
  background: #fff;
}
</style>
