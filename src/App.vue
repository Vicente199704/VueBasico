<template>
  <div>

  <img alt="Vue logo" src="./assets/logo.png">
  <Cuenta />


  </div>
</template>

<script>

import Cuenta from './components/Cuenta' 

export default {

  name: 'App',
  components: {
    Cuenta
    
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
