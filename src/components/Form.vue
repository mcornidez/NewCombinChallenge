<template>
  <form>
    <input type="text" name="FirstName" placeholder="First Name">
    <input type="text" name="LastName" placeholder="Last Name">
    <input type="text" name="Address" placeholder="Address">
    <input type="text" name="SSN" placeholder="SSN">
  </form>
  <button class="btn">Reset</button>
  <button class="btn">Save</button>
</template>

<script>
export default {
  name: "Form"
}
</script>

<style scoped>
::placeholder {
  color: black;
}

input{
  border: 1px solid black;
}

.btn {
  display:block;
  border-radius: 50%;
  border: 1px solid black;
  width: 50px;
  height: 50px;
}
</style>