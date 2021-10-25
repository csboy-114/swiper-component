<template>
  <div class="panel" :class="[cname]">
    <div class="title">{{title}}</div>
    <slot></slot>
  </div>
</template>

<script>
export default {
  name:"Panel",
  props:{
    title:{
      type:String,
      default:""
    },
    cname:{
      type:String,
      default:""
    }
  }
}

</script>
<style lang='scss'>
@import "../common/base.scss";
.panel{
  @include panel;
}
</style>