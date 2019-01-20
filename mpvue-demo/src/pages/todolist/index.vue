<template>
  <div>
    <h1>Vuejs is good</h1>
    <Todolist />
  </div>
</template>

<script>
import Todolist from '@/components/Todolist'

export default {
  components: {
    Todolist
  }
}
</script>

<style scoped>
h1 {
  color: red;
}
</style>
