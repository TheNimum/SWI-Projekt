<template>
<div class="main-Container">
	<h2> Main </h2>
	<input id="temp-name" v-model="search" placeholder="Sök" >
	<button id="tryck" v-on:click="sendRequest">tryck här</button>
	<div>
		<ul id="exempel1">
		<li>{{apiReturn.name}}</li>
		
		</ul></div>

</div>

</template>

<script>
export default ({
	data: () => ( {
		search: '0',		
			apiReturn: {},
			searchQuery: null
	}),
	
	
	methods: {
		async sendRequest() {
			const url = `https://swapi.dev/api/people/?search=${this.search}`
			try {
				const response = await fetch(url)
				const data = await response.json()				
				console.log('api:', data);
				const x = Object.keys(data);
				console.log('x',x )
				const y =  Object.entries(data);
				console.log('y', y)
				this.apiReturn = data;
				
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
