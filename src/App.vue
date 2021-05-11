<template>
  <div id="app1">
    <Title></Title>
    <Table id="table1"></Table>
    <Button></Button>
  </div>
</template>

<script>
import Title from './components/Title.vue'
import Table from './components/Table.vue'
import Button from './components/Button.vue'

export default {
  name: 'App',
  components: {
    Title: Title,
    Table:Table,
    Button: Button
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
