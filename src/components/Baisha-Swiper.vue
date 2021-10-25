<template>
  <div id="app">
   <swiper ref="mySwiper" :options="options">
    <swiper-slide class="item" v-for="item in info" :key="item.id">
        <img :src="item.img" @click="goOut(item.href)">
    </swiper-slide>
    <div class="swiper-pagination" slot="pagination"></div>
  </swiper>
  </div>
</template>

<script>
import { Swiper, SwiperSlide} from 'vue-awesome-swiper'
import 'swiper/css/swiper.css'
export default {
  name:'baisha-swiper',
  components: {
    Swiper,
    SwiperSlide
  },
  methods:{
    goOut(url){
      window.location.href=url
    }
  },
  props:{
    options:{
      type:Object,
      required:false,
      default(){
        return {
          pagination: {
            el: '.swiper-pagination'
          },
          autoplay:true,
          delay:1000
        }
      }
    },
    info:{
      type:Array,
      required:true,
      default(){
        return [{id:1},{id:2},{id:3},{id:5},{id:6}]
      }
    }
  },
   name: 'carrousel',
    data() {
      return {
        swiperOptions: {
          pagination: {
            el: '.swiper-pagination'
          },
          autoplay:true,
          delay:1000
          // Some Swiper option/callback...
        }
      }
    },
    computed: {
      swiper() {
        return this.$refs.mySwiper.$swiper
      }
    },
    mounted() {
      console.log('Current Swiper instance object', this.swiper)
      this.swiper.slideTo(0, 1000, false)
    }
}
</script>


<style lang="scss">
.item{
  box-sizing: border-box;
  width: 100px;
  line-height:100px;
  background-color: skyblue;
  text-align: center;
}
img{
  width: 304px;
  height: 144px;
}
</style>
