<template>
  <div class="main-constainer">
    
    <div class="card-info__back-btn-container">
        <div class="card-info__back-btn">
            <img class="card-info__back-btn-icon" src="@/assets/card-info/back-btn-icon.svg" alt=""> 
            <div class="card-info__back-btn-text">Back</div>
            <a 
                class="card-info__back-btn-click-area"
                @click="goBack"
            ></a>
        </div>
    </div>
    
    <div class="card-info__info-container info">
        <h1 class="info__name">{{card.name}}</h1>
        <div class="info__read-more">Read More</div>

        <div class="read-more__item-container">
            <div 
                class="read-more__item"
                v-for="(value, key) in card" 
                v-bind:key="key"
                >
                <div class="read-more__item-key">
                    {{key}}
                </div>
                <div class="read-more__item-value">
                    {{value}}
                </div>
            </div>
        </div>
    </div>


    <div class="card-info__image-container">
      <img class="card-info__image" :src="card.imageUrlHiRes" alt />
      <div class="card-info__image-graphic-container">
        <img class="card-info__image-graphic" src="@/assets/home/card/pokedex-button.svg" alt />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardInfo",
  props: ["card"],

  created() {
    if (this.card === undefined) {
      this.$router.push("/");
      return
    }
    console.log("created", this.card);
  },
  methods: {
      goBack(){
          this.$router.push('/')
      }
  },
};
</script>

<style lang="stylus" scoped>
@import "../styles/variables.styl"

.main-constainer
    margin 0 auto
    max-width $desktop-width
    display grid
    grid-template-columns 2fr 1fr
    grid-template-rows 0.3fr 2fr

    margin-bottom 10em

.card-info
    
    &__back-btn-container
        grid-row 1/2
        grid-column 1/2
        align-self start

    &__back-btn
        width: 186.51px;
        height: 51px;
        background: #525252;
        border-radius: 25.5px;
        display grid
        cursor pointer

    &__back-btn-icon
        grid-row 1/2
        grid-column 1/2
        justify-self start
        align-self center
        position relative
        left 5%

    &__back-btn-text
        grid-row 1/2
        grid-column 1/2
        justify-self center
        align-self center

        font-family: Sarabun;
        font-weight: normal;
        font-size: 23.3143px;
        line-height: 30px;
        text-align: center;
        margin-bottom 0.2em

        color: #FFFFFF;
        width 100%

    &__back-btn-click-area
        grid-row 1/2
        grid-column 1/2
        display block
        width 100%
        height 100%
        z-index 1


    &__image-container
        grid-row 1/3
        grid-column 2/3
        justify-self center
        align-self start

        max-height 515px
        max-width 345px

        background: #2F2F2F;
        border: 2px solid #525252;
        box-sizing: border-box;
        box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
        border-radius: 10px;

        grid-template-columns 1fr
        grid-template-rows 5fr 1fr
        display grid
        padding 16px

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
        width 100%

        border: 2px solid #525252;
        border-radius: 3px;
        justify-self center
        grid-row 1/2
        grid-column 1/2


    &__image-graphic-container
        grid-row 2/3
        grid-column 1/2

        display grid
        margin-top 20px
    

    &__info-container
        grid-row 2/3
        grid-column 1/2
        align-self start
        justify-self center

.info

    &__name
        font-weight: bold;
        font-size: 3em
        line-height: 34px;
        letter-spacing: 0.045em;

        color: #000000;

    &__read-more
        font-style: italic;
        font-weight: normal;
        font-size: 16px;
        line-height: 21px;

        letter-spacing: 0.045em;
        text-decoration-line: underline;

        color: #3294DB;
        cursor pointer

.read-more

    &__item-container
        padding 20px
        padding-left 0

    &__item
        display flex
        justify-content space-between

        font-weight: normal;
        font-size: 1.2em;
        line-height: 21px;
        letter-spacing: 0.045em;

        color: #2F2F2F;
        text-transform: capitalize;

        // margin-top 0.3em
        padding 10px 10px

    &__item:nth-child(odd)
        background #F6D301

    &__item-key
       font-weight bold 

</style>