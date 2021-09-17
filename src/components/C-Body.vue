<template>
<div class="main-Container">
	<h2> Main </h2>
	<input id="temp-name" v-model="search" placeholder="Sök" >
	<button class="people" v-on:click="sendRequest">People</button>
	<button class="planet" v-on:click="sendRequest2">planet</button>
	
	<div>
		<ul class="temp-list">
		<span on v-show="pressPeople">
		name: {{apiReturn.name}}<br></span>
		<div v-show="peopleinfo"> {{apiReturn.birth_year}}<br>
		eye-color: {{apiReturn.eye_color}}<br></div>
		</ul>
	</div>
	<div class="listOfChars">
		<ul v-for="item in getAllchar" :key="item.name" >
		{{item.name}}
		</ul>
	</div>
</div>

</template>

<script>
export default ({
	data: () => ( {
		search: '',		
		apiReturn: '',
		getAllchar:[],
		element: 0,
		pressPeople: false,
		peopleinfo: false		
	}),
	mounted(){this.$nextTick(function(){
		this.getRequest();
	})},
	
	
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
.listOfChars
{
	border: dotted darkorange;
	margin-left: 15em;
	margin-right: 15em;
	margin-bottom: 10px;
}
.main-Container{
	background-color: black;
	border: dotted rgb(129, 199, 221);
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
