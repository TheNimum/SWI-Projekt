<template>


<div class="main-Container">
	<div class="display-Item">	
		<span v-for="item in filteredList" :key="item.id" >
		
				<h2>{{item.title}}</h2>
				<p v-show="isFilmsList">Episode: {{item.episode_id}}</p>
				<p v-show="isFilmsList">Release: {{item.release_date}}</p>
				{{item.opening_crawl}}
	
				<h2>{{item.name}}</h2>
				<p v-show="isPeopleList">Birth year: {{item.birth_year}}</p>
				<p v-show="isPeopleList">Eye color: {{item.eye_color}}</p>
		</span>
				
	</div>
</div>

</template>

<script>
export default ({
	
	props: {
		list: Array,
		searchInput: String,
		isFilmsList: Boolean,
		isPeopleList: Boolean
	},
	
	data: () => ( {
		pressPeople: false,
		showPeople: false,
		showFilms: false,
		Home: false,

	}),
	computed: {
		filteredList: function() {
			if (!this.searchInput.length) {return this.list}
			return this.list.filter((item)=>{
				return item.name.toLowerCase().includes(this.searchInput.toLowerCase())
			});
		}
	},

	methods: {


	}
})
</script>

<style scoped>

.main-Container{

	background-color: black;
	border: dotted rgb(129, 199, 221);
	overflow-x:hidden;
}
.display-Item {
	display: grid;
	grid-template-columns: 2fr 2fr 2fr ;
	border: dotted darkorange;
	margin: 1em;
}

.display-Item span{
	display: inline-grid;
	margin: 1em;
	color:yellow;
}


</style>
