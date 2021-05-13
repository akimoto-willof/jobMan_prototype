<template>
  <div id="app">
    <Sideber />
    <Table />
    <div class="calendar">
      <Calendar />
    </div>
  </div>
</template>

<script>
import Table from '@/components/Table.vue';
import Sideber from '@/components/Sideber.vue';
import Calendar from '@/components/Calendar.vue';


export default {
  name: 'App',
  components: {
    Table,
    Sideber,
    Calendar
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

.calendar {
  position: absolute;
  top: 50%;
  left: 50%;
}
</style>
