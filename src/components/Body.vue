<template>
  <div class="container">
    <div class="item">
      <Form/>
    </div>
    <div class="item">
      <Table/>
    </div>
  </div>
</template>

<script>
import Form from './Form'
import Table from './Table'

export default {
  name: "Body",
  components: {
    Form,
    Table
  }
}
</script>

<style scoped>
  template{
    background-color: white;
  }
  .container {
    background-color: red;
    margin: 35px;
    overflow: hidden;
    border: 2px solid black;
    display: flex;
    justify-content: space-around;
    font-family: Arial,serif;
  }

  .item {
    width: 100%;
    height: 100%;
    background-color: white;
    margin: 15px;
    border: 2px solid black;
  }
</style>