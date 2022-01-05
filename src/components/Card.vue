<template>
  <div>  
    <v-card class="mx-auto" max-width="344">
      <v-card-title>
        {{card.question}}
      </v-card-title>

      <v-card-actions>
        <v-btn color="orange lighten-2" text >
          Explore
        </v-btn>
        <v-spacer></v-spacer>
  
        <v-btn icon @click="show = !show">
          <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
        </v-btn>
      </v-card-actions>
  
      <v-expand-transition>
        <div v-show="show">
          <v-divider/>
          <v-card-text>
            {{card.answer}}
          </v-card-text>
        </div>
      </v-expand-transition>

      <v-btn class="btn" variant="primary">Edit</v-btn >
      <v-btn variant="primary">Delete</v-btn >
       <v-icon>fas fa-edit</v-icon>
  
    </v-card>
    <br>
 </div>
</template>

<script>
  export default {
    name:'Card',
    props: ["card"],
    data(){
      return{
        show: false,
      }
    }
  }
</script>

<style>
  .btn {
    margin-right: 80px;
  }
</style>