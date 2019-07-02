<template>
  <div class="home__container">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'home',
  components: {
    
  }
}
</script>

<style lang="stylus">
@import "../styles/variables.styl"

.home

  &__container
    // background $test
    margin 0 auto
    max-width $desktop-width


</style>

