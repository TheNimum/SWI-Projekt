<template>
<main>
	
<div class="main-Container">
	
	<div class="Result">
		<ul class="temp-list">
		<span on v-show="pressPeople">
		name: {{apiReturn.name}}<br></span>
		<div v-show="showPeople">
		born: {{apiReturn.birth_year}}<br>
		eye-color: {{apiReturn.eye_color}}<br></div>
		</ul>
	</div>

	<div class="displayList">
		<ul>
			<li v-for="item in list" :key="item.id" >
				{{item.title}}
				{{item.name}}
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
		//getAllchar:[],
		//getAllFilms: [],
		element: 0,
		search: '',
		pressPeople: false,
		showPeople: false,
		showFilms: false,
		Home: false,

	}),
	
	
	methods: {
		
		async sendRequest() { // Sök bland "people"
			const url = `https://swapi.dev/api/people/?search=${this.search}`
			try {
				const response = await fetch(url)
				const data = await response.json()
				console.log('api:', data);
				this.apiReturn = data.results[0];
				this.pressPeople = true;
				this.showPeople = true;
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
				this.showPeople = false;
			}
			catch{
				return null;
			}
		},
		
		/*sendInfo(infoList) // Emmit
		{
			console.log('Emitting list to parent');
			// emit ( namnet på funktionen, data som ska skickas )
			this.$emit('selectedList', infoList)
		}*/
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
