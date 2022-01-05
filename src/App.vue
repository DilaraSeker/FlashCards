<template>
  <div id="app">
    <Input
      v-on:add-card-event="addCardItem" 
    />
    <Cards
      v-bind:cards="cards"   
    />
  </div>
</template>

<script>
import Input from './components/Input.vue'
import Cards from './components/Cards.vue'
export default {
  name: 'App',
  components: {
    Input,
    Cards
  },
  data() {
    return {
      cards: [],
      editCard: {
        question:'',
        answer:'',
        id: '',
      }
    }
  },
  methods: {
    addCardItem(newCard){
        this.cards = [...this.cards, newCard];
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
