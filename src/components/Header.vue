<template>
  <div class="container">
    <span class="heading">Home</span>
    <span class="heading">Other page</span>
  </div>
</template>


<script>
export default {
  name: "Header"
}
</script>

<style scoped>

.container{
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #019345;
  overflow: hidden;
  height: 50px;
  font-family: Arial,serif;
}

.heading{
  border: 2px solid black;
  width: 100%;
  text-align: center;
  height: 95%;
  font-size: x-large;

}
</style>