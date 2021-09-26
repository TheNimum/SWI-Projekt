<template>


<div class="main-Container">
	<div class="display-Item" v-if="isFilmsList">	
		<span v-for="item in filteredList" :key="item.id" >
		
				<h2>{{item.title}}</h2>
				<p>Episode: {{item.episode_id}}</p>
				<p>Release: {{item.release_date}}</p>
				{{item.opening_crawl}}
		</span>			
	</div>
	<div class="display-Item" v-else>
		<span v-for="item in filteredList" :key="item.id" >
				<h2>{{item.name}}</h2>
				<p>Birth year: {{item.birth_year}}</p>
				<p>Eye color: {{item.eye_color}}</p>
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
})
</script>

<style scoped>

.main-Container{

	background-image: linear-gradient(rgb(0, 0, 0), rgb(20, 22, 21), rgb(0, 0, 0), rgb(20, 22, 21), rgb(0, 0, 0));
	border: dotted yellow;
	overflow-x:hidden;
}
.display-Item {
	display: grid;
	grid-template-columns: 1fr 1fr 1fr;
	border: dotted yellow;
	margin: 1em;
}

.display-Item span{
	border: dotted white;
	display: inline-grid;
	margin: 1em;
	color:yellow;
}


</style>
