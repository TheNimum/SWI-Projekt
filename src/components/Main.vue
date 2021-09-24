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

.main-Container{
	background-color: black;
	border: dotted rgb(129, 199, 221);
	margin:0;
	overflow-x:hidden;
}
.displayList{
	display: grid;
	border: dotted darkorange;
	margin-left: 15em;
	margin-right: 15em;
	margin-bottom: 10px;
}

.displayList li{
	color:yellow;
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
