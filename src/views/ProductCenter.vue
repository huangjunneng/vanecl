<template>
  <div class="home">
    <Vheader class="vheader2">
      <img src="../assets/img/v.png" alt="" height="52px;">
    </Vheader>
    <div class="pbanner">
      <img src="../assets/img/productcenter/productcenter.png" alt="">
    </div>
    <ul class="plist">
      <li class="pitem" v-for="(item) in productData" :key="item.pproducid">
        <h6>{{item.category}}</h6>
        <img :src="item.img" alt="" @click="showDetail(item)" width="100%" height="500px;">
        <p class="pname">
          <span>{{item.productName}}</span>
          <i class="el-icon-star-off"></i>
        </p>
        <p>
          ￥<strong>{{item.price}}</strong>
        </p>
      </li>
    </ul>
    <Vfooter />
  </div>
</template>

<script>
// @ is an alias to /src
import img1 from '@/assets/img/productcenter/1-1.png'
import img2 from '@/assets/img/productcenter/1-2.png'
import img3 from '@/assets/img/productcenter/1-3.png'
import img4 from '@/assets/img/productcenter/2-1.png'
import img5 from '@/assets/img/productcenter/2-2.png'

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
      productData: [
        {
          category: '净肤控油',
          productid: '1001',
          productName: '梵蔻尔净肤控油洁面乳',
          img: img1,
          price: 168,
          capacity: '150ml',
          islike: false
        }, {
          category: '净肤控油',
          productid: '1002',
          productName: '梵蔻尔净肤控油洁面乳',
          img: img2,
          price: 268,
          capacity: '250ml',
          islike: false
        }, {
          category: '净肤控油',
          productid: '1003',
          productName: '梵蔻尔净肤控油洁面乳',
          img: img3,
          price: 168,
          capacity: '200ml',
          islike: false
        }, {
          category: '净肤控油',
          productid: '1004',
          productName: '梵蔻尔净肤控油洁面乳套装',
          img: img4,
          price: 368,
          capacity: '500ml',
          islike: false
        }, {
          category: '净肤控油',
          productid: '1005',
          productName: '梵蔻尔净肤控油洁面乳套装',
          img: img5,
          price: 368,
          capacity: '500ml',
          islike: false
        }
      ]
    }
  },
  methods: {
    showDetail (item) {
      console.log(item)
      localStorage.setItem('product', JSON.stringify(item))
      this.$router.push({ name: 'ProductDetail', params: { id: item.productid, oo: 123, item: item } })
      debugger
    }
  }
}
</script>

<style lang="less">
.vheader2 {
  height: 149px;
  background: #a5b7a9;
}
.pbanner {
  overflow: hidden;
  img {
    float: left;
    width: 100%;
  }
}
.plist {
  display: flex;
  flex-wrap: wrap;
  margin: 5% 10%;
  text-align: left;
  li {
    list-style-type: none;
    flex: 1;
    min-width: 30%;
    margin: 20px;
    img {
      cursor: pointer;
    }
    .pname {
      border: 1px solid #ccc;
      height: 30px;
      line-height: 30px;
      padding: 0 10px;
      i {
        line-height: 30px;
        float: right;
      }
    }
  }
}
</style>
