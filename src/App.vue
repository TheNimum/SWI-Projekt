<template>
<body>
  <Header></Header>
  <Navbar v-on:SelectedList="SelectedList"></Navbar>
  <Main 
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
      dataLength: 0,
    listofInfo:[],
    getAllchar:[],
		getAllFilms:[],
    listofAllData: []
    }),  
    methods: {
    
    SelectedList(request) {
      console.log('Get list from child');
      switch (request){
        case 'people':
          this.listofInfo=this.getAllchar
          break;
        case 'films':
          this.listofInfo=this.getAllFilms
          break;
        case 'home':
          break;
      }
    },

    FilterData(keyword)
    {
      
    },

    async GetPeople() // hämta
		{
			const url = `https://swapi.dev/api/people/`
			const response = await fetch(url)
			const data = await response.json()
			this.getAllchar = data.results;
			console.log('Get request People from api ', data)
		},

		async GetFilms() // hämta
		{
			const url = `https://swapi.dev/api/films/`
			const response = await fetch(url)
			const data = await response.json()
			this.getAllFilms = data.results;			
			console.log('Get request Films from api ', data)
		},

  },
    mounted(){
		this.GetPeople();
		this.GetFilms();
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
