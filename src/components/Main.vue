<template>


<div class="main-Container">
	<div class="displayList">
		<ul>
			<li v-for="item in filteredList" :key="item.id" >
				{{item.title}}
				{{item.name}}
			</li>
		</ul>
	</div>
</div>

</template>

<script>
export default ({

	props: {
		list: Array,
		searchInput: String
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

</style>
