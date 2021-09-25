<template>
<div>
  <Header></Header>

  <Navbar
    v-on:SelectedList="SelectedList"
    v-model="filterText">
  </Navbar>
  <Main
  v-bind:list="listToSend"
  v-bind:searchInput="filterText">
  </Main>
  <Footer></Footer></div>
</template>

<script>
import {ref} from "vue"
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
  setup() {
    const filterText = ref("");
    return { filterText };
	},

  data: () => ({
    listToSend:[],
    getAllchar:[],
		getAllFilms:[],
    listofAllData:[],
    isHidden: false
    }),

  methods: {

    SelectedList(request) {
      console.log('Get list from child');
      switch (request){
        case 'people':
          this.listToSend=this.getAllchar
          break;
        case 'films':
          this.listToSend=this.getAllFilms
          break;
        case 'home':
          this.MergeLists();
          this.listToSend=this.listofAllData
          break;
      }
    },

    async GetPeople() // hämta
		{
			const url = `https://swapi.dev/api/people/`
			const response = await fetch(url)
			const data = await response.json()
			this.getAllchar = data.results;
      this.listToSend=this.getAllchar
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

    MergeLists()
    {
      console.log('Merge lists')
      this.listofAllData= this.getAllchar.concat(this.getAllFilms);
    }

  },
    mounted(){
    this.MergeLists();
		this.GetPeople();
		this.GetFilms();
    }
}
</script>

<style>

</style>