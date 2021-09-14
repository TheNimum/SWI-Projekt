<template>
<div class="main-Container">
	<h2> Main </h2>
	<input id="temp-name" v-model="search" placeholder="Sök" >
	<button id="tryck här" v-on:click="sendRequest">tryck här</button>
	<div><p>name: {{apiReturn.name}}</p></div>

</div>

</template>

<script>
export default ({
	data: () => ( {
		search: '0',
		apiReturn: {} 	
	}),
	methods: {
		async sendRequest() {
			const url = `https://swapi.dev/api/people/?search=${this.search}`
			try {
				const resP = await fetch(url)
				const data = await resP.json()
				this.apiReturn = data;
				console.log('data from api:', data);
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
