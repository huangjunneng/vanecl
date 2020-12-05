<template>
  <div class="home">
    <Vheader class="vheader1">
      <img src="../assets/img/logo.png" alt="logo" width="300px">
    </Vheader>
    <Slider />
    <Vheader class="vheader2">
      <img src="../assets/img/v.png" alt="" height="52px;">
    </Vheader>
    <img src="../assets/img/img1.png" alt="" width="100%;">
    <img src="../assets/img/img2.png" alt="" width="100%;">
    <Vfooter />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import Vheader from '@/components/Vheader.vue'
import Vfooter from '@/components/Vfooter.vue'
import Slider from '@/components/Slider.vue'

export default {
  name: 'Home',
  components: {
    Slider,
    Vheader,
    Vfooter
  }
}
</script>

<style lang="less">
.vheader1 {
  position: fixed;
  top: 0;
  z-index: 666;
}
.vheader2 {
  height: 141px;
  background: #a5b7a9;
}
.home img {
  display: block;
  margin: auto;
}
</style>
