<template>
<body>
  <Header></Header>
  <Navbar></Navbar>
  <Main 
  v-on:selectedList="selectedList"
  v-bind:list="listofInfo">
  </Main>
  <Footer></Footer>
</body>

</template>

<script>
import Header from './components/Header'
import Main from './components/Main'
import Footer from './components/Footer'
import Navbar from './components/Navbar'

export default {
  name: 'App',
  components: {
    Header,
    Main,
    Footer,
    Navbar
  },
    data: () => ({
      listofInfo: []
    }),
      methods: {
        selectedList(list) {
            console.log('Get list from child');
            this.listofInfo = list
        }
    },
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
