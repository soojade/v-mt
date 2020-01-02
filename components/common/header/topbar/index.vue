<template>
  <el-row class="center">
    <el-col :span="10">
      <leftbar />
    </el-col>
    <el-col :span="8" :offset="6">
      <rightbar />
    </el-col>
  </el-row>
</template>

<script>
import leftbar from './leftbar'
import rightbar from './rightbar'
export default {
  components: {
    leftbar,
    rightbar
  }
}
</script>

<style>
</style>
