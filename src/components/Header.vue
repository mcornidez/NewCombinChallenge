<template>
  <div>
    <table>
      <tr>
        <td>Home</td>
        <td>Other page</td>
      </tr>
    </table>
  </div>
</template>


<script>
export default {
  name: "Header"
}
</script>

<style scoped>
div {
  background-color: #019345;
  border: 1px solid black;
  overflow: hidden
}

table {
  width: 100%;
  table-layout: fixed ;
  border: 1px solid black;
}

td {
  text-align: center;
}
</style>