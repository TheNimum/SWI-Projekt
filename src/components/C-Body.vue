<template>
<div class="main-Container">
	<h2> Main </h2>
	<input id="temp-name" v-model="search" placeholder="Sök" >
	<button id="tryck" v-on:click="sendRequest">tryck här</button>
	<div>
		<ul id="exempel1">
		<li> name: {{apiReturn.name}}</li>
		<li> birth year: {{apiReturn.birth_year}}</li>
		<li> lenght: {{apiReturn.height}}</li>
		
		</ul></div>

</div>

</template>

<script>
export default ({
	data: () => ( {
		search: '0',		
			apiReturn: { },
			searchQuery: null
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
		}

	}
})
</script>

<style scoped>
.main-Container{
	background-color: black;
	border: dotted rgb(129, 199, 221);
}
</style>
