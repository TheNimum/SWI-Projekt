<template>
<body>
  <Header></Header>
<<<<<<< HEAD
  <Main></Main>
  <Footer></Footer>
=======
  <Main 
  v-on:selectedList="selectedList"
  v-bind:list="listofInfo"></Main>
  <CFooter></CFooter>
>>>>>>> 18c6a1dfc485dd3c071026a4ffabbc147505c9e3
</body>

</template>

<script>
import Header from './components/Header.vue'
<<<<<<< HEAD
import Footer from './components/Footer.vue'
import Main from './components/Main.vue'
=======
import Main from './components/Main.vue'
import CFooter from './components/Footer.vue'
>>>>>>> 18c6a1dfc485dd3c071026a4ffabbc147505c9e3


export default {
  name: 'App',
  components: {
    Header,
    Main,
<<<<<<< HEAD
    Footer,

  }
=======
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
>>>>>>> 18c6a1dfc485dd3c071026a4ffabbc147505c9e3
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
