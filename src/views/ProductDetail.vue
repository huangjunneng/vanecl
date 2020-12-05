<template>
  <div class="home">
    <Vheader class="vheader2">
      <img src="../assets/img/v.png" alt="" height="52px;">
    </Vheader>
    <p class="breadcrumb">
      <el-breadcrumb separator-class="el-icon-arrow-right">
        <el-breadcrumb-item :to="{ name: 'Product' }">产品中心</el-breadcrumb-item>
        <el-breadcrumb-item>产品详情页</el-breadcrumb-item>
      </el-breadcrumb>
    </p>
    <div class="detail-contianer">

      <div class="photo" :routes="routes">
        <el-carousel :interval="5000" arrow="always">
          <el-carousel-item v-for="a in 3" :key="a">
            <img :src="Product.img" alt="" width="100%" height="100%">
          </el-carousel-item>
        </el-carousel>
      </div>
      <div class="describe">
        <h2 style="margin:0;">
          <span>{{Product.productName}}</span>
          <i class="el-icon-star-off" style="float:right;"></i>
        </h2>
        <p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx,有效儿子痘痘再生</p>
        <p><span>￥{{Product.price}}</span>/<span>{{Product.capacity}}</span> </p>
        <p>
          <el-button>加入购物袋</el-button>
          <el-button type="primary">立即购买</el-button>
        </p>
        <div>
          <h4>使用方法</h4>
          <ul>
            <li>请在洗颜后使用本产品。</li>
            <li>每次取用的量</li>
          </ul>
          <h4>使用时请注意</h4>
          <ul>
            <li>请在洗颜后使用本产品。</li>
            <li>每次取用的量</li>
          </ul>
          <ul>
            <li>当皮肤出现以下豆状时请停止使用。
              <p>1、使用中皮肤变红、肿、痒、刺激。。。。。。。。</p>
              <p>2、使用中皮肤变红、肿、痒、刺激。。。。。。。。</p>
            </li>
            <li>每次取用的量</li>
          </ul>
        </div>
      </div>

    </div>

    <Vfooter />
  </div>
</template>

<script>
import img1 from '@/assets/img/productcenter/1-1.png'

import Vheader from '@/components/Vheader.vue'
import Vfooter from '@/components/Vfooter.vue'

export default {
  name: 'Home',
  components: {
    Vheader,
    Vfooter
  },
  data () {
    return {
      img: img1
    }
  },
  computed: {
    Product () {
      console.log(this.$router.currentRoute.params.item)
      let Product = {}
      if (this.$router.currentRoute.params.item) {
        Product = this.$router.currentRoute.params.item
      } else {
        const p = localStorage.getItem('product') || {}
        Product = JSON.parse(p)
      }
      return Product
    }
  },
  created () {
    console.log(this.$router)
  },
  methods: {
    showDetail (item) {
      console.log(item)
    }
  }
}
</script>

<style lang="less">
.vheader2 {
  height: 149px;
  background: #a5b7a9;
}
.breadcrumb {
  width: 80%;
  margin: 30px auto;
}
.detail-contianer {
  display: flex;
  overflow: hidden;
  min-height: 600px;
  width: 1200px;
  margin: auto;
  .photo {
    height: 500px;
    width: 400px;
    float: left;
    margin-left: 10%;
    .el-carousel__container {
      height: 500px;
      width: 400px;
    }
  }
  .describe {
    max-width: 60%;
    flex: 1;
    text-align: left;
    padding: 0 16% 0 5%;
  }
}
</style>
