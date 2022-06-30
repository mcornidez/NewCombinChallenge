<template>
  <div>
      <p class="copyright">copyright</p>
      <p class="allRights">All rights reserved</p>
  </div>
</template>

<script>
export default {
  name: "Footer"
}
</script>

<style scoped>

div {
  background-color: #0171bd;
  border: 1px solid black;
  overflow: hidden
}

.copyright{
  margin-left: 5%;
  float: left;
}

.allRights{
  margin-right: 5%;
  float: right;
}


</style>