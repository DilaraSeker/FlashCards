<template>
  <div>
    <h1>Question List</h1>
    <v-row dense>
      <v-col
        v-for="card in cards"
        :key="card.title"
        :cols="card.flex"
      >
        <Card  
          v-bind:card="card" 
          v-on:edit-card-item="editCardMethod" 
          v-on:delete-card-item="deleteCardMethod" 
        />         
      </v-col>
    </v-row>
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
    methods: {
      editCardMethod(id){
        //send to parent (App.vue)
        this.$emit('edit-card-event', id)
      },
      deleteCardMethod(id){
        //send to parent
        this.$emit('delete-card-event', id);
      }
    }
  }
</script>