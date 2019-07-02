<template>
    <div id="app" class="header__container">
        <div class="header__content_container">
            <img alt="" src="@/assets/header-logo.png">
        
            <div class="header__nav-container">
                <img class="header__nav-bg-image" alt="" src="@/assets/header-nav-card-graphics.svg">
                <div id="nav" class="header__nav-link-container">
                    <router-link 
                        class="
                        header__nav-link 
                        header__nav-link--home" 
                        to="/"
                        >Home
                    </router-link>
                    <router-link 
                        class="
                        header__nav-link 
                        header__nav-link--grass" 
                        to="/grass"
                        >Grass Only
                    </router-link>
                    <router-link 
                        class="
                        header__nav-link 
                        header__nav-link--contact" 
                        to="/contact"
                        >Contact
                    </router-link>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Header'
        
    }
</script>

<style lang="stylus" scoped>
@import "../styles/variables.styl"

.header

  &__container
    background #525252
    max-height 155px
    margin-bottom 60px
  
  &__content_container
    max-width $desktop-width
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
    font-size: 24px;
    line-height: 33px;
    text-align: center;
    // text-decoration-line: underline;
    color: #F6D301;

    align-self center
    margin-bottom 1em
    position relative

    // &:after
    //   content ""
    //   position absolute
    //   display inline-block
    //   height 3px
    //   background #F6D301
    //   justify-self center
    //   bottom -8px
    //   width 50%
    //   left 25%
  
    &--home
      left 20%
    &--grass
      right 2%
      color: #9DEF9B;
    &--contact
      right 16%


</style>