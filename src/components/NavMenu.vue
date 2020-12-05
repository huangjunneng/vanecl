<template>
  <div class="nav-menu">
    <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect" background-color="transparent" text-color="#fff" active-text-color="#fff">
      <el-menu-item index="1">
        <router-link :to="{ name: 'Home'}">
          首页
        </router-link>
      </el-menu-item>
      <el-submenu index="2">
        <template slot="title">关于品牌</template>
        <el-menu-item index="2-1">选项1</el-menu-item>
        <el-menu-item index="2-2">选项2</el-menu-item>
        <el-menu-item index="2-3">选项3</el-menu-item>
      </el-submenu>
      <el-menu-item index="3" key="ssss">
        <router-link :to="{ name: 'Product'}">
          产品中心
        </router-link>
      </el-menu-item>
      <el-menu-item index="4">口碑心得</el-menu-item>
      <el-menu-item index="5">品牌动态</el-menu-item>
    </el-menu>
  </div>
</template>

<script>

export default {
  data () {
    return {
      activeIndex: '1'
    }
  },
  methods: {
    handleSelect (key, keyPath) {
      console.log(key, keyPath)
      debugger
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
.nav-menu {
  width: 520px;
  margin: auto;
  background: transparent;
  ul {
    border-bottom: none;
    color: white;
    li {
      color: white !important;
      padding: 0 20px;
    }
    li:hover {
      background: transparent !important;
      transition: none;
    }
  }
}
.el-menu {
  background-color: transparent;
}
.el-menu-item {
  transition: none;
}
</style>
