<template>

<div class="main-Container">
	<div>
		<ul class="temp-list">
		<span on v-show="pressPeople">
		name: {{apiReturn.name}}<br></span>
		<div v-show="peopleinfo">
		born: {{apiReturn.birth_year}}<br>
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
	props: {
		property: String
	},

	data: () => ( {
				
		apiReturn: '',
		getAllchar:[],
		element: 0,
		pressPeople: false,
		peopleinfo: false,	
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
