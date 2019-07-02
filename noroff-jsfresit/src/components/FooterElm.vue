<template>
    <div class="footer__container">
        <div class="footer__content-container">

            <img class="footer__mistary-images" src="@/assets/footer-mistary-pokemon.svg" alt="">
            <div class="footer__nav-link-container">
                <router-link 
                    class="
                    footer__nav-link 
                    footer__nav-link--home" 
                    to="/"
                    >Home
                </router-link>
                <router-link 
                    class="
                    footer__nav-link 
                    footer__nav-link--grass" 
                    to="/grass"
                    >Grass Only
                </router-link>
                <router-link 
                    class="
                    footer__nav-link 
                    footer__nav-link--contact" 
                    to="/contact"
                    >Contact
                </router-link>
            </div>
            <img class="footer__logo" src="@/assets/footer-pokemon-logo.svg" alt="">
        </div>
    </div>
</template>

<script>
    export default {
        name: 'footerElm'
    }
</script>

<style lang="stylus" scoped>
@import "../styles/variables.styl"

.footer

    &__container
        height 155px
        width 100%
        background #525252
        // position absolute
        // bottom 0
    
    &__content-container
        margin 0 auto
        max-width $desktop-width
        display flex

    &__mistary-images
        position relative
        top -40px
        margin-left -100px
        margin-right 60px
    
    &__nav-link-container
        font-family: Rosario;
        font-style: normal;
        font-weight: bold;
        font-size: 20.1655px;
        line-height: 24px;
        text-align: center;
        
        margin-top 20px
        white-space nowrap

    &__nav-link
        color: #F6D301;
        padding 20px 10px

        &--grass
            color: #9DEF9B;

    &__logo
        margin-right -100px
        margin-left 40px

</style>