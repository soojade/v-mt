<template>
  <h3>login</h3>
</template>

<script>
export default {
  layout: 'blank',
  beforeRouteEnter(to, from, next) {
    document.body.style.backgroundColor = '#fff'
    next()
  },
  beforeRouteLeave(to, from, next) {
    document.body.style.backgroundColor = ''
    next()
  }
}
</script>

<style>
</style>
