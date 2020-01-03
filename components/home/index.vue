<template>
  <div class="home center">
    <div class="banner">
      <mtmenu />
      <rightbanner />
    </div>
    <scenes />
  </div>
</template>

<script>
import mtmenu from './menu'
import rightbanner from './right-banner'
import scenes from './scenes'
export default {
  components: {
    mtmenu,
    rightbanner,
    scenes
  }
}
</script>

<style lang="scss" scoped>
.banner {
  display: flex;
  justify-content: space-between;
  background-color: #fff;
}
</style>
