<template lang="html">
        <swiper ref="mySwiper" :options="swiperOptions" style='height:100vh;' >
            <swiper-slide >
              <div class='banner-text'>
                <h3>源于自然 / 归于本真</h3>
                 <p>源于大自然的护肤能量</p>
              </div>
              <img src='../assets/img/banner.png'/>
            </swiper-slide>
            <swiper-slide> <img src='../assets/img/banner.png'/></swiper-slide>
            <div class="swiper-pagination" slot="pagination"> </div>
        </swiper>
</template>

<script>
import { Swiper, SwiperSlide, directive } from 'vue-awesome-swiper'
import 'swiper/swiper-bundle.css'
export default {
  name: 'Slider',
  components: {
    Swiper,
    SwiperSlide
  },
  directives: {
    swiper: directive
  },
  data () {
    return {
      swiperOptions: {
        pagination: {
          el: '.swiper-pagination'
        },
        autoplay: {
          delay: 3000,
          stopOnLastSlide: false,
          disableOnInteraction: true
        }
        // Some Swiper option/callback...
      }
    }
  },
  computed: {
    swiper () {
      return this.$refs.mySwiper.$swiper
    }
  },
  mounted () {
    console.log('Current Swiper instance object', this.swiper)
    // this.swiper.slideTo(3, 1000, true)
  }
}
</script>

<style lang="css" scope>
.swiper-wrapper img {
  width: 100%;
  height: 100%;
}
.banner-text {
  position: absolute;
  top: 0;
  bottom: 0;
  margin: auto;
  width: 100%;
  height: 150px;
  color: white;
  font-family: monospace;
  font-size: 20px;
}
.banner-text h3 {
  font-size: 40px;
}
/* @import "~swiper/dist/css/swiper.css"; */
</style>
