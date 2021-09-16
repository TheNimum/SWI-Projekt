<template>
<div class="main-Container">
	<h2> Main </h2>
	<input id="temp-name" v-model="search" placeholder="Sök" >
	<button class="tryck" v-on:click="sendRequest">tryck här</button>
	<button class="getall" v-on:click="getRequest">hämta lista</button>
	<div>
		<ul class="temp-list">
		<li> name: {{apiReturn.name}}</li>
		<li> born: {{apiReturn.birth_year}}</li>
		<li> lenght: {{apiReturn.height}} cm </li>
		</ul></div>
	<div v-for="item in getAllchar" :key="item.name">
		{{item.name}}
	</div>
</div>

</template>

<script>
export default ({
	data: () => ( {
		search: '',		
		apiReturn: '',
		getAllchar:[],
		element: 0			
	}),
	
	
	
	methods: {
		async sendRequest() { // tryck här knappen.
			const url = `https://swapi.dev/api/people/?search=${this.search}`
			try {				
				const response = await fetch(url)
				const data = await response.json()				
				console.log('api:', data);
				this.apiReturn = data.results[0];				
			}
			catch{
				return null;
			}
		},
		async getRequest() // hämta
		{
			const url = `https://swapi.dev/api/people/`
			
			const response = await fetch(url)
			const data = await response.json()
			this.getAllchar = data.results;
			console.log('Get request from api ', data)

		}
	} 
})
</script>

<style scoped>
.listOfChar
{
	border: dotted darkorange;
}
.main-Container{
	background-color: black;
	border: dotted rgb(129, 199, 221);
}
.temp-list{
	border: dotted hotpink;
	transition: 0,5s;
	margin-left: 15em;
	margin-right: 15em;
	align-content: center;
}
</style>
