<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <CounterComponent title="contador numero 1" :superv="3" :defcounter="5"/>
  <CounterComponent title="contador numero 2" :superv="2" :defcounter="4"/>
</template>

<script>
import CounterComponent from './components/Counter.vue'

export default {
  name: 'App',
  components: {
    CounterComponent
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
