<template>
  <div id="app">
    <Todolist />
  </div>
</template>

<script>
import Todolist from './components/Todolist'

export default {
  name: 'App',
  components: {
    Todolist
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
}
</style>
