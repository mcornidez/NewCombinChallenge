<template>
  <div>
    <div>
      <Form/>
    </div>
    <div>Table</div>
  </div>
</template>

<script>
import Form from './Form'
export default {
  name: "Body",
  components: {
    Form,
  }
}
</script>

<style scoped>
  template{
    background-color: white;
    height: 80%;
  }
  div {
    background-color: red;
    margin: 10px;
    overflow: hidden;
  }

  table {
    width: 100%;
    background-color: white;
    margin: 5px;
    table-layout: fixed ;
  }

  td {
    text-align: center;
  }
</style>