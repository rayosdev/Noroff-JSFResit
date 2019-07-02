<template>
  <div class="home__container">
    
    <div class="home__search-bar search-bar__container">
      <input class="search-bar__input" type="text">
      <div class="search-bar__btn-container">
        <button class="search-bar__btn"></button>
        <div class="search-bar__btn-text"> search </div>
        <img class="search-bar__btn-icon" src="@/assets/home/search-btn-icon.svg" alt="" >
        <a href="" class="search-bar__btn-click-area"></a>
      </div>
    </div>

    <div class="preview-cards__container">

      <div class="preview-card">
        <img class="preview-card__image" src="https://images.pokemontcg.io/base1/14_hires.png" alt="">
        <div class="preview-card__nav-container">
          <img class="preview-card__nav-graphic" src="@/assets/home/card/pokedex-button.svg" alt="">
          <div class="preview-card__nav-btn-container">
            <button class="preview-card__nav-btn">Expand</button>
            <img class="preview-card__nav-btn-icon" src="@/assets/home/card/expand-card-btn-icon.svg" alt="">
            <a href="" class="preview-card__nav-btn-click-area"></a>
          </div>
        </div>
      </div>

      <div class="preview-card">
        <img class="preview-card__image" src="https://images.pokemontcg.io/base1/14_hires.png" alt="">
        <div class="preview-card__nav-container">
          <img class="preview-card__nav-graphic" src="@/assets/home/card/pokedex-button.svg" alt="">
          <div class="preview-card__nav-btn-container">
            <button class="preview-card__nav-btn">Expand</button>
            <img class="preview-card__nav-btn-icon" src="@/assets/home/card/expand-card-btn-icon.svg" alt="">
            <a href="" class="preview-card__nav-btn-click-area"></a>
          </div>
        </div>
      </div>
      
      <div class="preview-card">
        <img class="preview-card__image" src="https://images.pokemontcg.io/base1/14_hires.png" alt="">
        <div class="preview-card__nav-container">
          <img class="preview-card__nav-graphic" src="@/assets/home/card/pokedex-button.svg" alt="">
          <div class="preview-card__nav-btn-container">
            <button class="preview-card__nav-btn">Expand</button>
            <img class="preview-card__nav-btn-icon" src="@/assets/home/card/expand-card-btn-icon.svg" alt="">
            <a href="" class="preview-card__nav-btn-click-area"></a>
          </div>
        </div>
      </div>

      <div class="preview-card">
        <img class="preview-card__image" src="https://images.pokemontcg.io/base1/14_hires.png" alt="">
        <div class="preview-card__nav-container">
          <img class="preview-card__nav-graphic" src="@/assets/home/card/pokedex-button.svg" alt="">
          <div class="preview-card__nav-btn-container">
            <button class="preview-card__nav-btn">Expand</button>
            <img class="preview-card__nav-btn-icon" src="@/assets/home/card/expand-card-btn-icon.svg" alt="">
            <a href="" class="preview-card__nav-btn-click-area"></a>
          </div>
        </div>
      </div>
      
      <div class="preview-card">
        <img class="preview-card__image" src="https://images.pokemontcg.io/base1/14_hires.png" alt="">
        <div class="preview-card__nav-container">
          <img class="preview-card__nav-graphic" src="@/assets/home/card/pokedex-button.svg" alt="">
          <div class="preview-card__nav-btn-container">
            <button class="preview-card__nav-btn">Expand</button>
            <img class="preview-card__nav-btn-icon" src="@/assets/home/card/expand-card-btn-icon.svg" alt="">
            <a href="" class="preview-card__nav-btn-click-area"></a>
          </div>
        </div>
      </div>
      
    </div>

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
    display grid

.search-bar

  &__container
    display grid
    grid-template-columns 1fr 1fr
    grid-template-rows 1fr auto
    margin-right 46px

  &__input
    background: #DDDDDD;
    box-shadow: inset 0px 4px 4px rgba(0, 0, 0, 0.25);
    border-radius: 56px;
    grid-column 2/3
    grid-row 1/2
    height 45px
    z-index 1
    padding-left 20px
    border none

  &__btn-container
    grid-column 2/3
    grid-row 1/2
    justify-self end
    align-self center
    margin-right 10px
    grid-template-columns 1fr
    grid-template-rows 1fr
    display grid
    z-index 1
    
  &__btn
    background: #525252;
    border-radius: 17.5px;
    width 128px
    height 35px
    border none
    grid-column 1/2
    grid-row 1/2
    cursor pointer
     
  &__btn-text
    color #fff
    grid-column 1/2
    grid-row 1/2
    justify-self center
    align-self center
    margin-bottom 4px
    user-select none


  &__btn-icon
    grid-column 1/2
    grid-row 1/2
    justify-self end
    align-self center
    margin-right 10px
    user-select none

  &__btn-click-area
    grid-column 1/2
    grid-row 1/2
    width 100%
    height 100%
    z-index 2


.preview-cards__container
  margin-top 24px
  display: flex
  flex-flow: row wrap
  align-content: space-between
  justify-content: space-between

  .preview-card

    background: #FFFFFF;
    border: 2px solid #525252;
    box-sizing: border-box;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    border-radius: 10px;

    grid-template-columns 1fr
    grid-template-rows 5fr 1fr
    display grid
    padding 16px
    margin 10px
    margin-top 5em

    &__image
      width: 175px;

      border: 2px solid #525252;
      border-radius: 3px;
      justify-self center
      grid-row 1/2
      grid-column 1/2

    &__nav-container
      grid-row 2/3
      grid-column 1/2

      display grid
      margin-top 10px

    &__nav-btn-container
      grid-row 1/2
      grid-column 2/3
      justify-self end
      display grid

    &__nav-btn
      width: 128px;
      height: 35px;

      background: #525252;
      border-radius: 17.5px;
      color #fff
      border none
      grid-row 1/2
      grid-column 1/2
      align-self center

    &__nav-btn-icon
      grid-row 1/2
      grid-column 1/2
      justify-self end
      align-self center
      margin-right 15px

    &__nav-btn-click-area
      grid-row 1/2
      grid-column 1/2
      justify-self end
      width 100%
      position relative
      z-index 1
      display block


            


</style>

