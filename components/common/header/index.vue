<template>
  <div class="header">
    <div class="topbar">
      <topbar />
    </div>
    <search />
  </div>
</template>

<script>
import topbar from './topbar'
import search from './search'
export default {
  components: {
    topbar,
    search
  }
}
</script>

<style>
.topbar {
  background-color: #f8f8f8;
  line-height: 40px;
}
.header {
  height: 197px;
  background-color: #fff;
  box-shadow: 0 2px 27px 0 rgba(0, 0, 0, 0.1);
}
</style>
