<template>
<body>
  <Header></Header>
  <Main 
  v-on:selectedList="selectedList"
  v-bind:list="listofInfo"></Main>
  <CFooter></CFooter>
</body>

</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import CFooter from './components/Footer.vue'


export default {
  name: 'App',
  components: {
    Header,
    Main,
    CFooter
  },
    data: () => ({
      listofInfo: []
    }),
      methods: {
        selectedList(list) {
            console.log('Get list from child');
            this.listofInfo = list
        }
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
