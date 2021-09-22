<template>
    <div class="navBox">
	<nav class="navbar">
		<a class="active" href="#home" @click="SendRequestToApp('home')">Home</a>
		<a href="#people" @click="SendRequestToApp('people')">People</a><!--Ändra till Sant/falskt-->
		<a href="#films" @click="SendRequestToApp('films')">Films</a>
	
	<div class="search">
		<input v-model="search" placeholder="Sök">
		<button class="people" @click="SendSearchRequest">People</button>
		<button class="film" @click="SendSearchRequest">Film</button>
	</div>
  </nav>
</div>
</template>

<script>
export default {
    data: () => ({
        request:'',
		search:''
    }),

    methods: {
		SendRequestToApp(request){
			console.log('Emitting  listrequest to parent');
			// emit ( namnet på funktionen, data som ska skickas )
			this.$emit('SelectedList', request)
		},

		SendSearchRequest()
		{
			console.log('Emitting search request to parent');
			this.$emit('FilterData', this.search)
		}
    }   
}
</script>
<style scoped>

.navBox{
  margin: 0;
  border:dotted rgb(255, 251, 0);
  background-color: black;
}
.navbar a{
	float: left;
	display: flex;
	color: #ffe6ff;
	text-align: center;
	padding:1em;
	text-decoration: none;
	}

/* Change the link color to (yellow)   on hover */
.navbar a:hover {
	background-image: linear-gradient(rgb(105, 95, 0), rgb(255, 238, 0));
	color: black;
	}
.search {
	padding: 1em;
	float: right;
}
.navBox:after {
    content: "";
    display: table;
    clear: both;
}
</style>