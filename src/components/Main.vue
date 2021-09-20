<template>
<main>
<div class="navBox">
	<nav class="navbar">
		<a class="active" href="#home">Home</a>
		<a href="#people" @click="sendInfo(getAllchar)">People</a><!--Ändra till Sant/falskt-->
		<a href="#films" @click="sendInfo(getAllFilms)">Films</a>
	
	<div class="search">
		<input v-model="search" placeholder="Sök">
		<button class="people" @click="sendRequest">People</button>
		<button class="planet" @click="sendRequest2">planet</button>
	</div>
  </nav>
</div>
<div class="main-Container">
	
	<div class="Result">
		<ul class="temp-list">
		<span on v-show="pressPeople">
		name: {{apiReturn.name}}<br></span>
		<div v-show="peopleinfo">
		born: {{apiReturn.birth_year}}<br>
		eye-color: {{apiReturn.eye_color}}<br></div>
		</ul>
	</div>
	
	<div class="listOfChars">
		<ul>
		<li v-for="item in getAllchar" :key="item.name" >
		{{item.name}}
		</li>
		</ul>
		<ul v-for="item in getAllFilms" :key="item.id" >
		{{item.title}}
		</ul>
	</div>

	<div class="displayList">
		<ul>
		<li v-for="item in list" :key="item.title" >
		{{item.title}}
		</li>
		</ul>
	</div>

</div>
</main>
</template>

<script>

export default ({

	props: ['list'],
	
	data: () => ( {
		apiReturn: '',
		getAllchar:[],
		getAllFilms: [],
		element: 0,
		search: '',
		pressPeople: false,
		peopleinfo: false,
	}),

	mounted(){
		this.getPeople();
		this.getFilms();
	},
	
	
	methods: {
		async sendRequest() { // tryck här knappen.
			const url = `https://swapi.dev/api/people/?search=${this.search}`
			try {
				const response = await fetch(url)
				const data = await response.json()
				console.log('api:', data);
				this.apiReturn = data.results[0];
				this.pressPeople = true;
				this.peopleinfo = true;
			}
			catch{
				return null;
			}
		},
		async sendRequest2() {
			const url = `https://swapi.dev/api/planets/?search=${this.search}`
			try {
				const response = await fetch(url)
				const data = await response.json()
				console.log('api:', data);
				this.apiReturn = data.results[0];
				this.pressPeople = true;
				this.peopleinfo = false;
			}
			catch{
				return null;
			}
		},
		async getPeople() // hämta
		{
			const url = `https://swapi.dev/api/people/`

			const response = await fetch(url)
			const data = await response.json()
			this.getAllchar = data.results;
			console.log('Get request from api ', data)

		},

		async getFilms() // hämta
		{
			const url = `https://swapi.dev/api/films/`
			
			const response = await fetch(url)
			const data = await response.json()
			this.getAllFilms = data.results;
			console.log('Get request from api ', data)
		},
		
		sendInfo(infoList) {
			console.log('Emitting list to parent');
			// emit ( namnet på funktionen, data som ska skickas )
			this.$emit('selectedList', infoList)
		}
	}
})
</script>

<style scoped>
.navBox{
  margin: 0px;
  border:dotted rgb(255, 251, 0);
}
.navbar a{
	float: left;
	display: block;
	color: #ffe6ff;
	text-align: center;
	padding:1em;
	text-decoration: none;
	}

/* Change the link color to (yellow)   on hover */
.navbar a:hover {
	background-image: linear-gradient(rgb(105, 95, 0), rgb(255, 238, 0));
	color: black;
	}
.search {
	padding: 1em;
	float: right;
}
.navBox:after {
    content: "";
    display: table;
    clear: both;
}
.main-Container{
	background-color: black;
	border: dotted rgb(129, 199, 221);
}
.listOfChars
{
	border: dotted darkorange;
	margin-left: 15em;
	margin-right: 15em;
	margin-bottom: 10px;
}

.temp-list{
	padding: 5px;
	padding-left: 2em;

	border: dotted hotpink;
	transition: 0,5s;
	margin-left: 15em;
	margin-right: 15em;
	text-align: left;
	align-content: center;
}
</style>
