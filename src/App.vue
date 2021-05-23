<template>
  <div id="app1">
    <Title></Title>
    <Table id="table1"></Table>
  </div>
</template>

<script>
import Title from './components/Title.vue'
import Table from './components/Table.vue'

export default {
  name: 'App',
  components: {
    Title: Title,
    Table:Table,
  }
}

let table = document.getElementById("table1");
console.log(table);


</script>

<style>
#app1 {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
