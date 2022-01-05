<template>
  <div>
    <div>  
    <br>
    <div class="container bg-blue-200 w-80 mx-auto my-20 px-6 py-6 shadow">
      <div class="h-0.5 bg-gray-200 w-36 mx-auto mt-2.5"></div><br>
      <form @submit="addCard" >
        <input 
          class="shadow appearance-none borderrounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight rounded-sm bg-gray-100 focus:outline-none focus:shadow-outline" 
          placeholder="Write question" 
          v-model="question"
        />
        <br>
        <input 
          class="shadow appearance-none borderrounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight rounded-sm bg-gray-100 focus:outline-none focus:shadow-outline"
          placeholder="Write answer"
          v-model="answer" />
        <button 
          class="px-7 py-2 mx-2 font-semibold text-white bg-pink-400 rounded "
          type="submit" >Submit</button>
      </form>
      <div class="h-0.5 bg-gray-200 w-36 mx-auto mt-2.5"></div>
    </div>
    <br>  
  </div>
  </div>
</template>

<script>
  export default {
    name:'Input',
    props: ['editCard'],
    data(){
      return{
        question:'',
        answer:'',
        id: '',
        edit: false
      }
    },
    methods: {
      addCard(e){
        e.preventDefault();
        if (this.edit === false){
          const newCard = {
            question: this.question,
            answer: this.answer,
            id: Math.floor(Math.random() * 100)
          };
          if (newCard.question !== '' && newCard.answer !== ''){
            this.$emit('add-card-event', newCard);
          }
          this.question = ''
          this.answer = ''
        }else{
          //edit card
          const cardItem = {
            question: this.question,
            answer: this.answer,
            id: this.id
          };
          //send to parent 
          this.$emit('edit-card-event', cardItem);
          //clear input field
          this.question = '';
          this.answer= '',
          this.edit = false;
        }
      }
    },
    watch: {
      editCard:{
        handler() {
          this.question = this.editCard.question;
          this.answer = this.editCard.answer;
          this.id = this.editCard.id;
          this.edit = true
        },
        deep: true
      },
      question:{
        handler(){
          if(this.question === ''){
            this.edit = false;
          }
        }
      },
      answer:{
        handler(){
          if(this.answer === ''){
            this.edit = false;
          }
        }
      }
    } 
 
  }
</script>

<style >
  #app {
  text-align: center;
  background-color: #e1f2fc;

}

</style>