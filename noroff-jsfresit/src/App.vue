<template>
<div class="main-container">
  <Header />
  <router-view/>

</div>
</template>

<script>
import Header from './components/Header'

  export default {
    name: 'App',
    components: {
      Header
    }
  }
</script>

<style lang="stylus" scoped>


</style>

<style lang="stylus">
// Global styles

body
  margin 0
  padding 0
  height calc(100% -50px)

a
  color #fff
  text-decoration none
  

</style>


