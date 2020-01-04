<template>
  <home />
</template>
<script>
import home from '@/components/home'
export default {
  components: {
    home
  },
  beforeRouteEnter(to, from, next) {
    if (process.client) {
      document.body.style.backgroundColor = '#f8f8f8'
    }
    next()
  },
  beforeRouteLeave(to, from, next) {
    if (process.client) {
      document.body.style.backgroundColor = ''
    }
    next()
  }
}
</script>

<style lang='scss' scoped>
</style>
