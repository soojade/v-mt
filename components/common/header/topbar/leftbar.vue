<template>
  <div class="leftbar">
    <span class="location">
      <i class="el-icon-location afont" />
      <span class="afont">济南</span>
      <nuxt-link class="changeCity" to="/changeCity">切换城市</nuxt-link>
      <span class="a">[</span>
      <nuxt-link to="/mentougou">长清区</nuxt-link>
      <nuxt-link to="/dachanghuizu">齐河</nuxt-link>
      <nuxt-link to="/langfang">章丘区</nuxt-link>
      <span class="a">]</span>
    </span>

    <span class="user-entry">
      <nuxt-link to="/login" class="active">立即登录</nuxt-link>&nbsp;&nbsp;
      <nuxt-link to="/register">注册</nuxt-link>
    </span>
  </div>
</template>

<script>
export default {}
</script>

<style>
.changeCity {
  color: #666;
  background-color: #f4f4f4;
  border: 1px solid #e5e5e5;
  padding: 2px 4px;
}
.user-entry {
  padding-left: 30px;
}
</style>
