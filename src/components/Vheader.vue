<template>
  <div class="vheader">
    <h1>
      <span style="display:inline-block;"></span>
      <slot />
      <NavMenu />
    </h1>

  </div>
</template>

<script>
import NavMenu from '@/components/NavMenu.vue'
export default {
  name: 'logo',
  components: {
    NavMenu
  },
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
.vheader {
  width: 100%;
  h1 {
    margin: 0;
  }
}
</style>
