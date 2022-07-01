<template>
  <table>
    <thead>
      <tr>
        <td>First Name</td>
        <td>Last Name</td>
        <td>Address</td>
        <td>SSN</td>
      </tr>
    </thead>
    <tbody>
    <tr
        v-for="item in list"
        v-bind:key="item.ssn"
    >
      <td>{{ item.firstName }}</td>
      <td>{{ item.lastName }}</td>
      <td>{{ item.address }}</td>
      <td>{{ item.ssn }}</td>
    </tr>
    </tbody>
  </table>
</template>

<script>

export default {
  name: "Table",
  data() {
    return { list: [] }
  },
  mounted() {
    fetch("http://localhost:8081/api/members")
        .then(res => res.json())
        .then(data => this.list = data)
        .catch(err => console.log(err.message))
  }
}
</script>

<style scoped>

table {
  width: 100%;
  border-spacing: 0;
}

td{
  padding: 3px 3px 3px 3px;
  outline: 1px solid black;
  text-align: center;
}


</style>