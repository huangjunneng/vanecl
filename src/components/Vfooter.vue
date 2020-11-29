<template>
  <div class="vfooter">
    <img src="../assets/img/logo2.png" alt="logo" width="30%;">
    <ul class="info">
      <li>
        <P>积分商城</P>
        <P>专柜查询</P>
        <P>防伪查询</P>
      </li>
      <li>
        <P>联系我们</P>
        <P>总机：
          <span>021-622220000</span>
        </P>
        <P>客服热线：
          <span>021-622220000</span>
        </P>
      </li>
      <li>
        <P>关注我们</P>
        <P>深圳融创致远实业有限公司
        </P>
        <P>地址：xxxxxx
        </P>
      </li>
    </ul>
  </div>
</template>

<script>

export default {
  name: 'vfooter',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
.vfooter {
  width: 100%;
  height: 500px;
  background: #99ab9d;
  .info {
    list-style-type: none;
    display: flex;
    padding: 100px 20% 0 20%;
    margin: auto;
    li {
      flex: 1;
      height: 200px;
      margin: 0 50px;
      color: #e7d6ce;
      text-align: left;
    }
  }
}
</style>
