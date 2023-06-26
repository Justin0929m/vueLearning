<template>
  <Nav/>
  <Header/>
  <router-view/>
</template>

<script>
import Header from '@/components/HeaderSection.vue'
import Nav from '@/components/Nav.vue'

export default {
    components: {
      Header,
      Nav
    }
}
</script>

<style>
  body{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
    font-family: sans-serif;
  }
</style>