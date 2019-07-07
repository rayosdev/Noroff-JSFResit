<template>
  <div class="green__main-container">
      
    <div class="green__container">
      
      
      <SearchBar 
        class="green__search-bar" 
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
        @cardSelected="expandCard($event)"
        />


      </div>
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
  name: 'grass',
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
      
      const card = this.cards.filter(c => c.name == e)
      this.$router.push({name: 'cardinfo', params:{card: card[0]}})
    }
  },
  created() {
    fetch('https://api.pokemontcg.io/v1/cards?setCode=base1')
    .then( res => {
      return res.json()
    }).then( json => {
      
      this.cards = json.cards.filter(c => {
        // console.log(typeof(c.types))
        if(typeof(c.types) == 'object'){
          return c.types.find(e => e == "Grass") 
        }  
      })

      // this.cards = json.cards
      
      this.cards.forEach(card => {
        this.allCardNames.push(card.name)
      });
    })    
    

  }


}
</script>

<style lang="stylus" scoped>
@import "../styles/variables.styl"

.green
  
  &__main-container
    background #9DEF9B
    padding-top 200px
    position relative
    top -200px

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
  margin-bottom 20vw


</style>

