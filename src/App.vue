<template>
  <div id="app">
    <Sideber />
    <Table />
  </div>
</template>

<script>
import Table from '@/components/Table.vue';
import Sideber from '@/components/Sideber.vue';


export default {
  name: 'App',
  components: {
    Table,
    Sideber
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
}
</style>
