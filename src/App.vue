<template>
<body>
  <Header></Header>
  <CBody></CBody>
  <CFooter></CFooter>
</body>

</template>

<script>
import Header from './components/Header.vue'
import CBody from './components/Main.vue'
import CFooter from './components/Footer.vue'


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
body {
	background-color: black;
}
</style>
