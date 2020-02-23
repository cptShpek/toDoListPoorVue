<template>
  <div id="app">
    <h1>Welcome to Your ToDo List!</h1>
    <ListCreating style="border: 5px double black; display: flex; justify-content: space-between;"/>
  </div>
</template>

<script>
import ListCreating from './components/ListCreating.vue'

export default {
  name: 'App',
  components: {
    ListCreating,
  }
}
</script>

<style>
  h1{
    text-align: center;
  };
</style>
