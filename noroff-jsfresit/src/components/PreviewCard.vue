<template>
      <div class="preview-card">
        <img class="preview-card__image" :src="card.imageUrl" alt="">
        <div class="preview-card__nav-container">
          <img class="preview-card__nav-graphic" src="@/assets/home/card/pokedex-button.svg" alt="">
          <div class="preview-card__nav-btn-container">
            <button class="preview-card__nav-btn">Expand</button>
            <img class="preview-card__nav-btn-icon" src="@/assets/home/card/expand-card-btn-icon.svg" alt="">
            <a href="" class="preview-card__nav-btn-click-area"></a>
          </div>
        </div>
      </div>
</template>

<script>
    export default {
        name: "PreviewCard",
        props:[
            'card'
        ],
        data() {
            return {
                name: ""
            }
        },
    }
</script>

<style lang="stylus" scoped>

.preview-card

  background: #2F2F2F;
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

  transform scale(1)
  opacity 1
  animation fadein 1s

  @keyframes fadein
    0%{
        transform scale(0.7)
        opacity 0
      }
    100%{ 
      transform scale(1)
      opacity 1
    }

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

    background #F6D301
    border-radius: 17.5px;
    // color #2F2F2F
    color #000
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

    &:hover ~ &__nav-btn
      background red

</style>