<template>
  <div id="app">
    <Input/>
    <Card/>
  </div>
</template>

<script>
import Input from './components/Input.vue'
import Card from './components/Card.vue'
export default {
  name: 'App',
  components: {
    Input,
    Card
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
