<template>
  <div class="home__container">
    
    
    <SearchBar 
      class="home__search-bar" 
      :allCardNames="allCardNames"
      @serachItemSelected="expandCard($event)"
      />

    <div 
      class="preview-cards__container"
    >
      <PreviewCard 
      v-for="(card, index) in cards"
      v-bind:key="index"
      :card="card"
      />


    </div>

  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

import PreviewCard from '@/components/PreviewCard.vue'
import SearchBar from '@/components/SearchBar.vue'
// import { async } from 'q';

export default {
  name: 'home',
  components: {
    PreviewCard,
    SearchBar,
  },
  data() {
    return {
      cards: [],
      allCardNames: [],
    }
  },
  methods: {
    expandCard(e){
      
    }
  },
  created() {
    fetch('https://api.pokemontcg.io/v1/cards?setCode=base1')
    .then( res => {
      return res.json()
    }).then( json => {
      this.cards = json.cards
      
      this.cards.forEach(card => {
        this.allCardNames.push(card.name)
      });
    })    
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

  &__search-bar
    position relative
    z-index 3


.preview-cards__container
  margin 0 5vw
  margin-top 24px
  display: flex
  flex-flow: row wrap
  align-content: space-between
  justify-content: space-around



</style>

