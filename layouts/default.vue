<template>
  <el-container>
    <el-header style="height: 197px">
      <mtheader />
    </el-header>
    <el-main>
      <nuxt />
    </el-main>
    <el-footer>
      <mtfooter />
    </el-footer>
  </el-container>
</template>

<script>
import mtheader from '@/components/common/header'
import mtfooter from '@/components/common/footer'
export default {
  components: {
    mtheader,
    mtfooter
  }
}
</script>
<style scoped>
</style>
