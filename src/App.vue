<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <p>TODO LIST</p>
    <form_input />
  </div>
</template>

<script>
import form_input from './components/form_input.vue'
export default {
  name: 'App', 
  components: {
    form_input
  },
  data(){
    return{
      
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
