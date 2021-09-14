<template>
<div class="main-Container">
	<h2> Main </h2>
	<input id="temp-name" v-model="message" placeholder="Sök planet" >
	<button id="tryck här" v-on:click="sendRequest">tryck här</button>
	<div>{{apiReturn.name}} </div>
</div>

</template>

<script>
export default ({
	data: () => ( {
		message: '0',
		apiReturn: {}
		
	}),
	methods: {
		async sendRequest() {
			const url = `https://swapi.dev/api/people/${this.message}`
			try {
				const response = await fetch(url)
				const data = await response.json()
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
