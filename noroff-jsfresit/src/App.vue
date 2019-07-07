<template>
<div class="main-container">
  <div id="tag-top"></div>
  <Header />
  <router-view
    class="view"
  />
  <FooterElm class="footer-elm" />
</div>
</template>

<script>
import Header from './components/Header'
import FooterElm from './components/FooterElm'

  export default {
    name: 'App',
    components: {
      Header,
      FooterElm
    },
    created() {
      
    },
  }
</script>

<style lang="stylus" scoped>

.main-container
  // min-height 1000px

.view
  min-height 100vh

.footer-elm
  position relative
  bottom 0

</style>

<style lang="stylus">
// Global styles

body
  margin 0
  padding 0
  height calc(100% -50px)
  font-family: 'Sarabun', sans-serif;

a
  color #fff
  text-decoration none
  



</style>


