<template>
    <div class="navBox">
	<nav class="navbar">
		<a class="active" href="#home" @click="SendRequestToApp('home')">Home</a>
		<a href="#people" @click="SendRequestToApp('people')">People</a><!--Ändra till Sant/falskt-->
		<a href="#films" @click="SendRequestToApp('films')">Films</a>
	
	<div class="search">
		<input v-model="search" placeholder="Sök">
		<button class="people" @click="sendRequest">People</button>
		<button class="planet" @click="sendRequest2">planet</button>
	</div>
  </nav>
</div>
</template>

<script>
export default {
    data: () => ({
        requestPeople:'people',
        requestFilms: 'films',
        requestHome: 'home'
    }),

    methods: {
    SendRequestToApp(request){
    switch(request){
        case 'people':
        console.log('Emitting people request to parent');
		// emit ( namnet på funktionen, data som ska skickas )
		this.$emit('selectedList', this.requestPeople)
        break;
        case 'films':
        console.log('Emitting films request to parent');
		// emit ( namnet på funktionen, data som ska skickas )
		this.$emit('selectedList', this.requestFilms)
		break;
		case 'home':
			console.log('Emitting home request to parent');
			// emit ( namnet på funktionen, data som ska skickas )
			this.$emit('selectedList', this.requestFilms)
			}
		}
    }   
}
</script>
<style scoped>

.navBox{
  margin: 0px;
  border:dotted rgb(255, 251, 0);
}
.navbar a{
	float: left;
	display: block;
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