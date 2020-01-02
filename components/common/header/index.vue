<template>
  <div class="header">
    <div class="topbar">
      <topbar />
    </div>
  </div>
</template>

<script>
import topbar from './topbar'
export default {
  components: {
    topbar
  }
}
</script>

<style>
.topbar {
  background-color: #f8f8f8;
  line-height: 40px;
}
</style>
