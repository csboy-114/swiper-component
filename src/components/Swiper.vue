<template>
  <div class="swiper-container">
    <div class="swiper-wrapper">
      <div class="swiper-slide" v-for="(item,index) in img" :key="index">
        <img :src=item alt="" />
      </div>
    </div>
    <div class="swiper-pagination" v-if="isPagShow"></div>
  </div>
</template>

<script>
export default {
  props:{
    img:{
      type:Array,
      required:true  
    },
    isBtnShow:{
      type:Boolean,
      require:true,
      default:false
    },
    isPagShow:{
       type:Boolean,
      require:true,
      default:false
    }
  },
  mounted() {
    new Swiper(".swiper-container", {
      autoplay: 2000, //可选选项，自动滑动,
      speed: 300,
      loop: true,
      pagination: ".swiper-pagination",
      effect: "fade",
    });
  },
};
</script>
<style lang="scss" scoped>
.swiper-slide {
  width: 100vw;
  height: 150px;
  img{
    width: 100%;
    height: 100%;
  }
}
</style>
