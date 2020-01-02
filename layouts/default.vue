<template>
  <el-container>
    <el-header>
      <mtheader />
    </el-header>
    <el-main>
      <nuxt />
    </el-main>
    <el-footer>Footer</el-footer>
  </el-container>
</template>

<script>
import mtheader from '@/components/common/header'
export default {
  components: {
    mtheader
  }
}
</script>
<style>
</style>
