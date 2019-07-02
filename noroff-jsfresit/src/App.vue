<template>
<div class="main-container">

  <div id="app" class="header__container">
    <div class="header__content_container">
      <img alt="" src="./assets/header-logo.png">
      
      <div class="header__nav-container">
        <img class="header__nav-bg-image" alt="" src="./assets/header-nav-card-graphics.svg">
        <div id="nav" class="header__nav-link-container">
          <router-link class="header__nav-link" to="/">Home</router-link>
          <router-link class="header__nav-link" to="/grass">Grass Only</router-link>
          <router-link class="header__nav-link" to="/contact">Contact</router-link>
        </div>
      </div>
    </div>
  </div>
  <router-view/>
</div>
</template>
<style lang="stylus" scoped>


.header

  &__container
    background #525252
    max-height 155px
  
  &__content_container
    max-width 1152px
    margin 0 auto
    width 100%
    display flex
    justify-content space-between

  &__nav-container
    display grid

  &__nav-bg-image
    grid-row 1/2
    grid-column 1/2

  &__nav-link-container
    grid-row 1/2
    grid-column 1/2
    display grid
    grid-template-columns 1fr 1fr 1fr

  &__nav-link
    font-family: Rosario;
    font-style: normal;
    font-weight: bold;
    font-size: 27px;
    line-height: 33px;
    text-align: center;
    text-decoration-line: underline;
    color: #F6D301;

    align-self center
    margin-bottom 1em

// #app
//   font-family 'Avenir', Helvetica, Arial, sans-serif
//   -webkit-font-smoothing antialiased
//   -moz-osx-font-smoothing grayscale
//   text-align center
//   color #2c3e50

// #nav
//   padding 30px
//   a
//     font-weight bold
//     color #2c3e50
//     &.router-link-exact-active
      // color #42b983
</style>

<style lang="stylus">
// Global styles

body
  margin 0
  padding 0

a
  color #fff
  

</style>


