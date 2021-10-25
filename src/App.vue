<template>
  <div id="app">
    <Panel cname="appVue" title="我是静态标题">
      <h1>一级内容</h1>
      <h2>二级内容</h2>
      <h3>三级内容</h3>
    </Panel>
  </div>
</template>

<script>
import Panel from './components/Panel.vue'
export default {
  components: {
    Panel
  },
  data(){
    return {
      panel:'app'
    }
  }
}
</script>

// <style lang="scss">
//   h3{
//     color: #ccc;
//   }
// </style>



<style lang="scss" scoped>
@import "./common/base.scss";
.appVue{
  @include panel;
  background-color: pink;
  ::v-deep .title{
    color: aqua;
    height: 40px;
  }
  h1{
    color: red;
  }
  h2{
    color: blue;
  }
  h3{
    color: #ccc;
  }
}
</style>
