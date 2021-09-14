<template>
<div>
  <Header></Header>
  <CBody></CBody>
  <CFooter></CFooter>
</div>
</template>

<script>
import Header from './components/Header.vue'
import CBody from './components/C-Body.vue'
import CFooter from './components/C-Footer.vue'


export default {
  name: 'App',
  components: {
    Header,
    CBody,
    CFooter
  
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #fbff00;
  
  background-color: black;
  
}
</style>
