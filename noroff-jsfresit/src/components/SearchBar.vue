<template>
    <div class="home__search-bar search-bar__container">
      <input 
        class="search-bar__input" type="text"
        @input="onSearchInput"
        @focus="onSearchInput"
        @blur="onLostFocus"
        >
      <div class="search-bar__btn-container">
        <button class="search-bar__btn"></button>
        <div class="search-bar__btn-text"> search </div>
        <img class="search-bar__btn-icon" src="@/assets/home/search-btn-icon.svg" alt="" >
        <a href="" class="search-bar__btn-click-area"></a>
      </div>

      <div class="search-bar__option-position-container">
        <div 
          class="search-bar__option-container"
          v-if="searchOptionItems.length > 0"
          >
          <div 
            class="search-bar__option-item"
            v-for="(item, index) in searchOptionItems" :key="index"
            >
            {{item}}
          </div>
        </div>
      </div>

    </div>
</template>

<script>
export default {
    name: 'SearchBar',

    props: ['allCardNames'],
    data() {
        return {
        searchOptionItems: [],
        }
    },
    methods: {
        onSearchInput(e){
            if(typeof(this.allCardNames) != "object"){
                console.log("test", typeof(this.allCardNames)) 
                return
            }
            this.searchOptionItems = []
            if(e.target.value == ""){
            return
            }
            let inputText = e.target.value
            this.sortMostRelavant(this.allCardNames, inputText)
                
            for (const item of this.allCardNames) {
            
            
            if(this.searchOptionItems.length <= 4){
                if(item[0].toUpperCase() == inputText[0].toUpperCase()){
                if(item.toUpperCase().includes(inputText.toUpperCase()) ){
                    this.searchOptionItems.push(item)
                }
                }
            }
            else{break}
            
            }
        },
        sortMostRelavant(array, string){
            array.sort( (name1, name2) => {
            let score1 = 0
            let score2 = 0
            for (let i = 0; i < string.length; i++) {
                if(i > name1.length - 1 || i > name2.length - 1){break}
                if(string[i].toUpperCase() == name1[i].toUpperCase()){score1 += 1}
                if(string[i].toUpperCase() == name2[i].toUpperCase()){score2 += 1}
            }
            if(score2 >= score1){ return 1}
            else {return -1}
            })
            return array
        },
        onLostFocus(){
            this.searchOptionItems = []
        }
    },
    
}
</script>

<style lang="stylus" scoped>

.search-bar

  &__container
    display grid
    grid-template-columns 1fr 1fr
    grid-template-rows 1fr auto
    margin-right 46px
    max-height 47px
    // border solid #0f0 4px

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
    font-size 1.2em

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

  &__option-position-container
    grid-column 2/3
    grid-row 1/2
    position relative
    display grid

  &__option-container
    width 90%
    min-height 40px
    position absolute
    justify-self center
    top 57px
    padding-bottom 18px

    background: #ddd;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    border-radius: 0px 0px 20px 20px;
  
  &__option-item
    padding 10px
    color #696969
    cursor pointer

    &:hover
      color #fff
      background: #696969;

</style>