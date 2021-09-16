<template>
<div class="main-Container">
	<h2> Main </h2>
	<input id="temp-name" v-model="search" placeholder="Sök" >
	<button class="tryck" v-on:click="sendRequest">tryck här</button>
	<button class="getall" v-on:click="getRequest">hämta lista</button>
	<div>
		<ul class="temp-list">
		<li> name: {{apiReturn.name}}</li>
		<li> birth year: {{apiReturn.birth_year}}</li>
		<li> lenght: {{apiReturn.height}}</li>
		</ul></div>
	<div class="listOfChar">
		{{characters}}
	</div>
</div>

</template>

<script>
export default ({
	data: () => ( {
		search: '0',		
		apiReturn: {},
		characters: {},
		
			
	}),
	
	
	methods: {
		async sendRequest() {
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
		async getRequest()
		{
			const url = `https://swapi.dev/api/people/?search=${this.search}`
			
			const response = await fetch(url)
			const data = await response.json()
			
			for (let i = 0; i < data.length; i++) {
				
				const x = data.results[i];
				this.characters = x;
			}
			console.log('data', data)
				
			
			
		}
	} 
})
</script>

<style scoped>
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
