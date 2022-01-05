<template>
  <div id="app">
    <Input
      v-bind:editCard="editCard" 
      v-on:add-card-event="addCardItemEvent"
      v-on:edit-card-event="editCardItemEvent"  
    />
    <Cards
      v-bind:cards="cards" 
      v-on:edit-card-event="editCardItem" 
      v-on:delete-card-event="deleteCardItem"   
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
    addCardItemEvent(newCard){
        this.cards = [...this.cards, newCard];
    },
    editCardItemEvent(cardItem){
      //find the index of this id's object
      let objIndex = this.cards.findIndex(obj => obj.id === cardItem.id)
      //update the item
      this.cards[objIndex].question = cardItem.question;
      this.cards[objIndex].answer = cardItem.answer;
    },
    editCardItem(id){
      //find the index of the question's id
      let objIndex = this.cards.findIndex(obj=> obj.id === id);
      this.editCard.question = this.cards[objIndex].question;
      this.editCard.answer = this.cards[objIndex].answer;
      this.editCard.id = id;
    },
    deleteCardItem(id){
      this.cards = this.cards.filter(card => card.id !== id);
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
}
</style>
