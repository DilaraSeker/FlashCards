<template>
  <div>
    <h1>Question List</h1>
    <div v-bind:key="card.id" v-for="card in cards">
      <Card  
        v-bind:card="card" 
      />        
    </div>
    <div v-if="!cards.length">
      <h1>No Cards!</h1>
    </div>
    <br>
  </div>
</template>

<script>
  import Card from "./Card";
  export default {
    name: "Cards",
    props: ["cards"],
    components: {
      Card
    },
    
  }
</script>