<script>
import Header from "@/components/Header.vue";
import Body from "@/components/Body.vue";
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    Body,
    Footer,
  },
}
</script>

<template class="app">
  <Header/>
  <Body/>
  <Footer/>
</template>

<style>
</style>
