<template>
  <div id="app">
    <layout/>
  </div>
</template>

<script>
import Layout from './components/index'

export default {
  name: 'app',
  components: {
    Layout
  }
}
</script>

<style lang="scss">
  @import "~styles/main";
</style>
