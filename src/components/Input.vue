<template>
  <div>
    <div>  
    <br>
    <div class="container bg-blue-200 w-80 mx-auto my-20 px-6 py-6 shadow">
      <div class="h-0.5 bg-gray-200 w-36 mx-auto mt-2.5"></div><br>
      <form >
        <input 
          class="shadow appearance-none borderrounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight rounded-sm bg-gray-100 focus:outline-none focus:shadow-outline"
          placeholder="Write question" 
        />
        <br>
        <input 
          class="shadow appearance-none borderrounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight rounded-sm bg-gray-100 focus:outline-none focus:shadow-outline"
          placeholder="Write answer"/>
        <button 
          type="submit" 
          class="px-7 py-2 mx-2 font-semibold text-white bg-pink-400 rounded ">Submit</button>
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
  }
</script>

<style >
  #app {
  text-align: center;
  background-color: #e1f2fc;

}

</style>